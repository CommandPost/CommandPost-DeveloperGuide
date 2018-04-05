# [docs](index.md) » cp.prop
---

This is a utility library for helping keep track of single-value property states. Each property provides access to a single value. Must be readable, but may be read-only. It works by creating a table which has a `get` and (optionally) a `set` function which are called when changing the state.

## Features
### 1. Callable
A `prop` can be called like a function once created. Eg:

```lua
local value = true
local propValue = prop.new(function() return value end, function(newValue) value = newValue end)
propValue() == true     -- `value` is still true
propValue(false) == false   -- now `value` is false
```

### 2. Togglable
A `prop` comes with toggling built in - as long as the it has a `set` function. Continuing from the last example:

```lua
propValue:toggle()  -- `value` went from `false` to `true`.
```

 **Note:** Toggling a non-boolean value will flip it to `nil` and a subsequent toggle will make it `true`. See the [toggle method](#toggle) for more details.

### 3. Watchable
Interested parties can 'watch' the `prop` value to be notified of changes. Again, continuing on:

```lua
propValue:watch(function(newValue) print "New Value: "...newValue) end) -- prints "New Value: true" immediately
propValue(false)    -- prints "New Value: false"
```

This will also work on [AND](#and) and [OR][#or] properties. Any changes from component properties will trigger a notification.

### 4. Combinable
We can combine or modify properties with AND/OR and NOT operations. The resulting values will be a live combination of the underlying `prop` values. They can also be watched, and will be notified when the underlying `prop` values change. For example:

```lua
local watered   = prop.TRUE()               -- a simple `prop` which stores the current value internally, defaults to `true`
local fed       = prop.FALSE()              -- same as above, defautls to `false`
local rested    = prop.FALSE()              -- as above.
local satisfied = watered:AND(fed)        -- will be true if both `watered` and `fed` are true.
local happy     = satisfied:AND(rested)   -- will be true if both `satisfied` and `happy`.
local sleepy    = fed:AND(prop.NOT(rested)) -- will be sleepy if `fed`, but not `rested`.

-- These statements all evaluate to `true`
satisfied()     == false
happy()         == false
sleepy()        == false

-- Get fed
fed(true)       == true
satisfied()     == true
happy()         == false
sleepy()        == true

-- Get rest
rested:toggle() == true
satisfied()     == true
happy()         == true
sleepy()        == false

-- These will produce an error, because you can't modify an AND or OR:
happy(true)
happy:toggle()
```

You can also use non-boolean properties. Any non-`nil` value is considered to be `true`.

## 5. Immutable
If appropriate, a `prop` may be immutable. Any `prop` with no `set` function defined is immutable. Examples are the `prop.AND` and `prop.OR` instances, since modifying combinations of values doesn't really make sense.

Additionally, an immutable wrapper can be made from any `prop` value via either `prop.IMMUTABLE(...)` or calling the `myValue:IMMUTABLE()` method.

Note that the underlying `prop` value(s) are still potentially modifiable, and any watchers on the immutable wrapper will be notified of changes. You just can't make any changes directly to the immutable property instance.

For example:

```lua
local isImmutable = propValue:IMMUTABLE()
isImmutable:toggle()    -- results in an `error` being thrown
isImmutable:watch(function(newValue) print "isImmutable changed to "..newValue end)
propValue:toggle()      -- prints "isImmutable changed to false"
```

## 6. Bindable
A property can be bound to an 'owning' table. This table will be passed into the `get` and `set` functions for the property if present. This is mostly useful if your property depends on internal instance values of a table. For example, you might want to make a property work as a method instead of a function:

```lua
local owner = {
   _value = true
}
owner.value = prop(function() return owner._value end)
owner:isMethod() -- error!
```

To use a `prop` as a method, you need to `attach` it to the owning table, like so:

```lua
local owner = {
    _value = true
}
owner.isMethod = prop(function(self) return self._value end, function(value, self) self._value = value end):bind(owner)
owner:isMethod()                -- success!
owner.isMethod()                -- also works - will still pass in the bound owner.
owner.isMethod:owner() == owner -- is true~
```

The bound `owner` is passed in as the last parameter of the `get` and `set` functions.

## 7. Extendable
A common use case is using metatables to provide shared fields and methods across multiple instances. A typical example might be:

```lua
local person = {}
function person:name(newValue)
    if newValue then
        self._name = newValue
    end
    return self._name
end

function person.new(name)
    local o = { _name = name }
    return setmetatable(o, { __index = person })
end

local johnDoe = person.new("John Doe")
johnDoe:name() == "John Doe"
```

If we want to make the `name` a property, we might try creating a bound property like this:

```lua
person.name = prop(function(self) return self._name end, function(value, self) self._name = value end):bind(person)
```
Unfortunately, this doesn't work as expected:

```lua
johnDoe:name()          -- Throws an error because `person` is the owner, not `johnDoe`.
johnDoe.name() == nil   -- Works, but will return `nil` because "John Doe" is applied to the new table, not `person`
```

The fix is to use `prop.extend` when creating the new person. Rewrite `person.new` like so:

```lua
person.new(name)
    local o = { _name = name }
    return prop.extend(o, person)
end
```

Now, this will work as expected:

```lua
johnDoe:name() == "John Doe"
johnDoe.name() == "John Doe"
```

The `prop.extend` function will set the `source` table as a metatable of the `target`, as well as binding any bound props that are in the `source` to `target`.

# Tables

Because tables are copied by reference rather than by value, changes made inside a table will not necessarily trigger an update when setting a value with an updated table value. By default, tables are simply passed in and out without modification. You can nominate for a property to make copies of tables (not userdata) when getting or setting, which effectively isolates the value being stored from outside modification. This can be done with the [deepTable](#deepTable) and[shallowTable](#shallowTable) methods. Below is an example of them in action:

```lua
local value = { a = 1, b = { c = 1 } }
local valueProp = prop.THIS(value)
local deepProp = prop.THIS(value):deepTable()
local shallowProp = prop.THIS(value):shallowTable()

-- print a message when the prop value is updated
valueProp:watch(function(v) print("value: a = " .. v.a ..", b.c = ".. v.b.c ) end)
deepProp:watch(function(v) print("deep: a = " .. v.a ..", b.c = ".. v.b.c ) end)
shallowProp:watch(function(v) print("shallow: a = " .. v.a ..", b.c = ".. v.b.c ) end)

-- change the original table:
value.a             = 2
value.b.c           = 2

valueProp().a       == 2    -- modified
valueProp().b.c     == 2    -- modified
shallowProp().a     == 1    -- top level is copied
shallowProp().b.c   == 2    -- child tables are referenced
deepProp().a        == 1    -- top level is copied
deepProp().b.c      == 1    -- child tables are copied as well

-- get the 'value' property
value = valueProp()         -- returns the original value table

value.a             = 3     -- updates the original value table `a` value
value.b.c           = 3     -- updates the original `b` table's `c` value

valueProp(value)            -- nothing is printed, since it's still the same table

valueProp().a       == 3    -- still referencing the original table
valueProp().b.c     == 3    -- the child is still referenced too
shallowProp().a     == 1    -- still unmodified after the initial copy
shallowProp().b.c   == 3    -- still updated, since `b` was copied by reference
deepProp().a        == 1    -- still unmodified after initial copy
deepProp().b.c      == 1    -- still unmodified after initial copy

-- get the 'deep copy' property
value = deepProp()          -- returns a new table, with all child tables also copied.

value.a             = 4     -- updates the new table's `a` value
value.b.c           = 4     -- updates the new `b` table's `c` value

deepProp(value)             -- prints "deep: a = 4, b.c = 4"

valueProp().a       == 3    -- still referencing the original table
valueProp().b.c     == 3    -- the child is still referenced too
shallowProp().a     == 1    -- still unmodified after the initial copy
shallowProp().b.c   == 3    -- still referencing the original `b` table.
deepProp().a        == 4    -- updated to the new value
deepProp().b.c      == 4    -- updated to the new value

-- get the 'shallow' property
value = shallowProp()       -- returns a new table with top-level keys copied.

value.a             = 5     -- updates the new table's `a` value
value.b.c           = 5     -- updates the original `b` table's `c` value.

shallowProp(value)          -- prints "shallow: a = 5, b.c = 5"

valueProp().a       == 3    -- still referencing the original table
valueProp().b.c     == 5    -- still referencing the original `b` table
shallowProp().a     == 5    -- updated to the new value
shallowProp().b.c   == 5    -- referencing the original `b` table, which was updated
deepProp().a        == 4    -- unmodified after the last update
deepProp().b.c      == 4    -- unmodified after the last update
```

So, a little bit tricky. The general rule of thumb is:
1. If working with immutable objects, use the default 'value' value copy, which preserves the original.
2. If working with an array of immutible objects, use the 'shallow' table copy.
3. In most other cases, use a 'deep' table copy.

## API Overview
* Constants - Useful values which cannot be changed
 * [NIL](#nil)
* Functions - API calls offered directly by the extension
 * [AND](#and)
 * [bind](#bind)
 * [extend](#extend)
 * [FALSE](#false)
 * [IMMUTABLE](#immutable)
 * [is](#is)
 * [NOT](#not)
 * [OR](#or)
 * [THIS](#this)
 * [TRUE](#true)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [ABOVE](#above)
 * [AND](#and)
 * [ATLEAST](#atleast)
 * [ATMOST](#atmost)
 * [BELOW](#below)
 * [bind](#bind)
 * [cached](#cached)
 * [clear](#clear)
 * [clone](#clone)
 * [deepTable](#deeptable)
 * [EQ](#eq)
 * [get](#get)
 * [hasWatchers](#haswatchers)
 * [id](#id)
 * [IMMUTABLE](#immutable)
 * [IS](#is)
 * [ISNOT](#isnot)
 * [label](#label)
 * [mirror](#mirror)
 * [monitor](#monitor)
 * [mutable](#mutable)
 * [mutate](#mutate)
 * [NEQ](#neq)
 * [NOT](#not)
 * [OR](#or)
 * [owner](#owner)
 * [preWatch](#prewatch)
 * [set](#set)
 * [shallowTable](#shallowtable)
 * [toggle](#toggle)
 * [unwatch](#unwatch)
 * [update](#update)
 * [value](#value)
 * [watch](#watch)
 * [wrap](#wrap)

## API Documentation

### Constants

#### [NIL](#nil)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.NIL -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns a `cp.prop` which will always be `nil`.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a new `cp.prop` instance with a value of `nil`.</li></ul>          |

### Functions

#### [AND](#and)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.AND(...) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a new `cp.prop` which will be `true` if all `cp.prop` instances passed into the function return a `truthy` value.                                                                                         |
| **Parameters**                                       | <ul><li>`...`        - The list of `cp.prop` instances to 'AND' together.</li></ul> |
| **Returns**                                          | <ul><li>a `cp.prop` instance.</li></ul>          |
| **Notes**                                            | <ul><li>The value of this instance will resolve by lazily checking the `value` of the contained `cp.prop` instances in the order provided. The first `falsy` value will be returned. Otherwise the last `truthy` value is returned.</li><li>The instance is **immutable**.</li><li>Once you have created an 'AND', you cannot 'OR' as a method. Eg, this will fail: `prop.TRUE():AND(prop:FALSE()):OR(prop.TRUE())`. This is to avoid ambiguity as to whether the 'AND' or 'OR' takes precedence. Is it `(true and false) or true` or `true and (false or true)`?.</li><li>To combine 'AND' and 'OR' values, group them together when combining. Eg:</li><li> ** `(true and false) or true`: `prop.OR( prop.TRUE():AND(prop.FALSE()), prop.TRUE() )`</li><li> ** `true and (false or true)`: `prop.TRUE():AND( prop.FALSE():OR(prop.TRUE()) )`</li></ul>                |

#### [bind](#bind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.bind(owner[, relaxed]) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This provides a utility function for binding multiple properties to a single owner in                                                                                         |
| **Parameters**                                       | <ul><li>* owner     - The owner table to bind the properties to.</li><li>* relaxed   - If `true`, then non-`cp.prop` fields will be ignored. Otherwise they generate an error.</li></ul> |
| **Returns**                                          | <ul><li>* A function which should be called, passing in a table of key/value pairs which are `string`/`cp.prop` value.</li></ul>          |
| **Notes**                                            | <ul><li>* If you are binding multiple `cp.prop` values that are dependent on other `cp.prop` values on the same owner (e.g. via `mutate` or a boolean join), you</li><li>  will have to break it up into multiple `prop.bind(...) {...}` calls, so that the dependent property can access the bound property.</li><li>* If a `cp.prop` provided as bindings already has a bound owner, it will be wrapped instead of bound directly.</li></ul>                |

#### [extend](#extend)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.extend(target, source) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Makes the `target` extend the `source`. It will copy all bound properties on the source table into the target, rebinding it to the target table. Other keys are inherited via the metatable.                                                                                         |
| **Parameters**                                       | <ul><li>`target` - The target to extend</li><li>`source` - The source to extend from</li></ul> |
| **Returns**                                          | <ul><li>The `target`, now extending the `source`.</li></ul>          |

#### [FALSE](#false)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.FALSE() -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a new `cp.prop` which will cache internally, initially set to `false`.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a `cp.prop` instance defaulting to `false`.</li></ul>          |

#### [IMMUTABLE](#immutable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.IMMUTABLE(propValue) -- cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a new `cp.prop` instance which will not allow the wrapped value to be modified.                                                                                         |
| **Parameters**                                       | <ul><li>`propValue`      - The `cp.prop` value to wrap.</li></ul> |
| **Returns**                                          | <ul><li>a new `cp.prop` instance which cannot be modified.</li></ul>          |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.is(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `value` is an instance of a `cp.prop`.                                                                                         |
| **Parameters**                                       | <ul><li>`value`  - The value to check.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the value is an instance of `cp.prop`.</li></ul>          |

#### [NOT](#not)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.NOT(propValue) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a new `cp.prop` which negates the provided `propValue`. Values are negated as follows:                                                                                         |
| **Parameters**                                       | <ul><li>`propValue`      - Another `cp.prop` instance.</li></ul> |
| **Returns**                                          | <ul><li>a `cp.prop` instance negating the `propValue`.</li></ul>          |
| **Notes**                                            | <ul><li>If the `propValue` is mutable, you can set the `NOT` property value and the underlying value will be set to the negated value. Be aware that the same negation rules apply when setting as when getting.</li></ul>                |

#### [OR](#or)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.OR(...) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a new `cp.prop` which will return the first 'truthy' value provided by one of the provided properties. Otherwise, returns the last 'falsy' value.                                                                                         |
| **Parameters**                                       | <ul><li>`...`        - The list of `cp.prop` instances to 'OR' together.</li></ul> |
| **Returns**                                          | <ul><li>a `cp.prop` instance.</li></ul>          |
| **Notes**                                            | <ul><li>The value of this instance will resolve by lazily checking the `value` of the contained `cp.prop` instances in the order provided. If any return `true`, no further instances will be checked.</li><li>The instance is immutable, since there is no realy way to flip the component values of an 'OR' in a way that makes sense.</li><li>Once you have created an 'OR', you cannot 'AND' as a method. Eg, this will fail: `prop.TRUE():OR(prop:FALSE()):AND(prop.TRUE())`. This is to avoid ambiguity as to whether the 'OR' or 'AND' takes precedence. Is it `(true or false) and true` or `true or (false and true)`?.</li><li>To combine 'AND' and 'OR' values, group them together when combining. Eg:</li><li> ** `(true or false) and true`: `prop.AND( prop.TRUE():OR(prop.FALSE()), prop.TRUE() )`</li><li> ** `true or (false and true)`: `prop.TRUE():OR( prop.FALSE():AND(prop.TRUE()) )`</li></ul>                |

#### [THIS](#this)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.THIS([initialValue]) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a new `cp.prop` instance which will cache a value internally. It will default to the value of the `initialValue`, if provided.                                                                                         |
| **Parameters**                                       | <ul><li>`initialValue`   - The initial value to set it to (optional).</li></ul> |
| **Returns**                                          | <ul><li>a new `cp.prop` instance.</li></ul>          |

#### [TRUE](#true)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.TRUE() -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a new `cp.prop` which will cache internally, initially set to `true`.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a `cp.prop` instance defaulting to `true`.</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop.new(getFn, setFn, cloneFn) --> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `prop` value, with the provided `get` and `set` functions.                                                                                         |
| **Parameters**                                       | <ul><li>`getFn`      - The function that will get called to retrieve the current value.</li><li>`setFn`      - (optional) The function that will get called to set the new value.</li><li>`cloneFn`        - (optional) The function that will get called when cloning the property.</li></ul> |
| **Returns**                                          | <ul><li>The new `cp.prop` instance.</li></ul>          |
| **Notes**                                            | <ul><li>`getFn` signature: `function([owner]) -> anything`</li><li> ** `owner`     - If this is attached as a method, the owner table is passed in.</li><li>`setFn` signature: `function(newValue[, owner])`</li><li> ** `newValue`  - The new value to store.</li><li> ** `owner`     - If this is attached as a method, the owner table is passed in.</li><li>`cloneFn` signature: `function(prop) -> new cp.prop`</li><li>This can also be executed by calling the module directly. E.g. `require('cp.prop')(myGetFunction)`</li></ul>                |

### Methods

#### [ABOVE](#above)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:ABOVE() -> cp.prop <boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new property comparing this property to `something`.                                                                                         |
| **Parameters**                                       | <ul><li>`something`  - A value, a function or a `cp.prop` to compare to.</li></ul> |
| **Returns**                                          | <ul><li>New, read-only `cp.prop` which will be `true` if this property is greater than `something`.</li></ul>          |

#### [AND](#and)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:AND(...) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new `cp.prop` which will be `true` if this and all other `cp.prop` instances passed into the function return `true`.                                                                                         |
| **Parameters**                                       | <ul><li>`...`        - The list of `cp.prop` instances to 'AND' together.</li></ul> |
| **Returns**                                          | <ul><li>a `cp.prop` instance.</li></ul>          |
| **Notes**                                            | <ul><li>See the [AND Function](#and) for more details</li></ul>                |

#### [ATLEAST](#atleast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:ATLEAST() -> cp.prop <boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new property comparing this property to `something`.                                                                                         |
| **Parameters**                                       | <ul><li>`something`  - A value, a function or a `cp.prop` to compare to.</li></ul> |
| **Returns**                                          | <ul><li>New, read-only `cp.prop` which will be `true` if this property is less than or equal to `something`.</li></ul>          |

#### [ATMOST](#atmost)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:ATMOST() -> cp.prop <boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new property comparing this property to `something`.                                                                                         |
| **Parameters**                                       | <ul><li>`something`  - A value, a function or a `cp.prop` to compare to.</li></ul> |
| **Returns**                                          | <ul><li>New, read-only `cp.prop` which will be `true` if this property is less than or equal to `something`.</li></ul>          |

#### [BELOW](#below)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:BELOW() -> cp.prop <boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new property comparing this property to `something`.                                                                                         |
| **Parameters**                                       | <ul><li>`something`  - A value, a function or a `cp.prop` to compare to.</li></ul> |
| **Returns**                                          | <ul><li>New, read-only `cp.prop` which will be `true` if this property is less than `something`.</li></ul>          |

#### [bind](#bind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:bind(owner, [key]) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Binds the property to the specified owner. Once bound, it cannot be changed.                                                                                         |
| **Parameters**                                       | <ul><li>`owner`  - The owner to attach to.</li><li>`key`    - If provided, the property will be bound to the specified key.</li></ul> |
| **Returns**                                          | <ul><li>the `cp.prop`</li></ul>          |
| **Notes**                                            | <ul><li>Throws an `error` if the new owner is `nil`.</li><li>Throws an `error` if the owner already has a property with the name provided in `key`.</li><li>Throws an `error` if the `key` is not a string value.</li></ul>                |

#### [cached](#cached)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:cached() -> prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | This can be called once to enable caching of the result inside the `prop`.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `cp.prop` instance.</li></ul>          |

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:clear() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Clears the property. Watchers will be notified if the value has changed.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>nil</li></ul>          |

#### [clone](#clone)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:clone() -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new copy of the property.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>New `cp.prop`.</li></ul>          |

#### [deepTable](#deeptable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:deepTable([skipMetatable]) -> prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | This can be called once to enable deep copying of `table` values. By default,                                                                                         |
| **Parameters**                                       | <ul><li>`skipMetatable`  - If set to `true`, copies will _not_ copy the metatable into the new tables.</li></ul> |
| **Returns**                                          | <ul><li>The `cp.prop` instance.</li></ul>          |
| **Notes**                                            | <ul><li>See [shallowTable](#shallowTable).</li></ul>                |

#### [EQ](#eq)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:EQ(something) -> cp.prop <boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Synonym for [IS](#is).                                                                                         |
| **Parameters**                                       | <ul><li>`something`  - A value, a function or a `cp.prop` to compare to.</li></ul> |
| **Returns**                                          | <ul><li>New, read-only `cp.prop` which will be `true` if this property is equal to `something`.</li></ul>          |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:get() -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current value of the property.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |

#### [hasWatchers](#haswatchers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:hasWatchers() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if the property has any watchers.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if any watchers have been registered.</li></ul>          |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:id() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current ID.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The ID value.</li></ul>          |

#### [IMMUTABLE](#immutable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:IMMUTABLE() -- cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new `cp.prop` instance wrapping this property which will not allow it to be modified.                                                                                         |
| **Parameters**                                       | <ul><li>`propValue`      - The `cp.prop` value to wrap.</li></ul> |
| **Returns**                                          | <ul><li>a new `cp.prop` instance which cannot be modified.</li></ul>          |

#### [IS](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:IS(something) -> cp.prop <boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new property returning `true` if the value is equal to `something`.                                                                                         |
| **Parameters**                                       | <ul><li>`something`  - A value, a function or a `cp.prop` to compare to.</li></ul> |
| **Returns**                                          | <ul><li>New, read-only `cp.prop` which will be `true` if this property is equal to `something`.</li></ul>          |

#### [ISNOT](#isnot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:ISNOT(something) -> cp.prop <boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new property returning `true` when this property is not equal to `something`.                                                                                         |
| **Parameters**                                       | <ul><li>`something`  - A value, a function or a `cp.prop` to compare to.</li></ul> |
| **Returns**                                          | <ul><li>New, read-only `cp.prop` which will be `true` if this property is NOT equal to `something`.</li></ul>          |

#### [label](#label)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:label([newLabel]) -> string | cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets and sets the property label. This is human-readable text describing the `cp.prop`.                                                                                         |
| **Parameters**                                       | <ul><li>* newLabel      - (optional) if provided, this will be the new label.</li></ul> |
| **Returns**                                          | <ul><li>* Either the existing label, or the `cp.prop` itself if a new label was provided.</li></ul>          |

#### [mirror](#mirror)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:mirror(otherProp) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Configures this prop and the other prop to mirror each other's values.                                                                                         |
| **Parameters**                                       | <ul><li>* `otherProp`   - The other prop to mirror.</li></ul> |
| **Returns**                                          | <ul><li>The same property.</li></ul>          |

#### [monitor](#monitor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:monitor(...) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an uncloned watch to the `otherProp` which will trigger an [update](#update) check in this property.                                                                                         |
| **Parameters**                                       | <ul><li>`...`  - a list of other `cp.prop` values to monitor.</li></ul> |
| **Returns**                                          | <ul><li>`cp.prop`    - This prop value.</li></ul>          |

#### [mutable](#mutable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:mutable() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the `cp.prop` can be modified.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if the value can be modified.</li></ul>          |

#### [mutate](#mutate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:mutate(getFn[, setFn]) -> cp.prop <anything; read-only>, function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new property that is a mutation of the current one.                                                                                         |
| **Parameters**                                       | <ul><li>`mutateFn`   - The function which will mutate the value of the current property.</li></ul> |
| **Returns**                                          | <ul><li>A new `cp.prop` which will return a mutation of the property value.</li></ul>          |

#### [NEQ](#neq)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:NEQ(something) -> cp.prop <boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | A synonym for [ISNOT](#isnot)                                                                                         |
| **Parameters**                                       | <ul><li>`something`  - A value, a function or a `cp.prop` to compare to.</li></ul> |
| **Returns**                                          | <ul><li>New, read-only `cp.prop` which will be `true` if this property is NOT equal to `something`.</li></ul>          |

#### [NOT](#not)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:NOT() -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new `cp.prop` which negates the current value. Values are negated as follows:                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a `cp.prop` instance negating the current instance.</li></ul>          |
| **Notes**                                            | <ul><li>If this property is mutable, you can set the `NOT` property value and this property will be set to the negated value. Be aware that the same negation rules apply when setting as when getting.</li></ul>                |

#### [OR](#or)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:OR(...) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new `cp.prop` which will be `true` if this or any `cp.prop` instance passed into the function returns `true`.                                                                                         |
| **Parameters**                                       | <ul><li>`...`        - The list of `cp.prop` instances to 'OR' together.</li></ul> |
| **Returns**                                          | <ul><li>a `cp.prop` instance.</li></ul>          |
| **Notes**                                            | <ul><li>See [OR Function](#or) for more details.</li></ul>                |

#### [owner](#owner)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:owner() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | If this is a 'method', return the table instance the method is attached to.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The owner table, or `nil`.</li></ul>          |

#### [preWatch](#prewatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:preWatch(preWatchFn) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a function which will be called once if any watchers are added to this prop.                                                                                         |
| **Parameters**                                       | <ul><li>`preWatchFn`     - The function to call once when the prop is watched. Has the signature `function(owner, prop)`.</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul>          |

#### [set](#set)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:set(newValue) -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the property to the specified value. Watchers will be notified if the value has changed.                                                                                         |
| **Parameters**                                       | <ul><li>`newValue`   - The new value to set. May be `nil`.</li></ul> |
| **Returns**                                          | <ul><li>The current value of the prop. May not be the same as `newValue`.</li></ul>          |

#### [shallowTable](#shallowtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:shallowTable(skipMetatable) -> prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | This can be called once to enable shallow cloning of `table` values. By default,                                                                                         |
| **Parameters**                                       | <ul><li>`skipMetatable`  - If set to `true`, the metatable will _not_ be copied to the new table.</li></ul> |
| **Returns**                                          | <ul><li>The `cp.prop` instance.</li></ul>          |
| **Notes**                                            | <ul><li>See [deepTable](#deepTable).</li></ul>                |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:toggle() -> boolean | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggles the current value. Values are modified as follows:                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The new value.</li></ul>          |
| **Notes**                                            | <ul><li>If the value is immutable, an error will be thrown.</li><li>If you toggle a non-boolean parameter twice, it will end up set to `true`.</li></ul>                |

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:unwatch(watchFn) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Removes the specified watch method as a watcher, if present. An example of adding and removing a watch:                                                                                         |
| **Parameters**                                       | <ul><li>`watchFn`        - The original watch function to remove. Must be the same instance that was added.</li><li>`notifyNow`  - The function will be triggered immediately with the current state.  Defaults to `false`.</li></ul> |
| **Returns**                                          | <ul><li>`cp.prop`        - The same `cp.prop` instance</li><li>`function`   - The watch function, which can be passed to [unwatch](#unwatch) to stop watching.</li></ul>          |
| **Notes**                                            | <ul><li>You can watch immutable values. Wrapped `cp.prop` instances may not be immutable, and any changes to them will cause watchers to be notified up the chain.</li></ul>                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:update() -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Forces an update of the property and notifies any watchers if it has changed.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:value([newValue]) -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current value of the `cp.prop` instance. If a `newValue` is provided, and the instance is mutable, the value will be updated and the new value is returned. If it is not mutable, an error will be thrown.                                                                                         |
| **Parameters**                                       | <ul><li>`newValue`   - The new value to set the instance to.</li></ul> |
| **Returns**                                          | <ul><li>The current boolean value.</li></ul>          |
| **Notes**                                            | <ul><li>If you need to set the property to `nil`, use the [set method](#set), otherwise it will be ignored.</li></ul>                |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:watch(watchFn[, notifyNow]) -> cp.prop, function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the watch function to the value. When the value changes, watchers are notified by calling the function. The function should have the following signature:                                                                                         |
| **Parameters**                                       | <ul><li>`watchFn`        - The watch function, with the signature `function(newValue, owner)`.</li><li>`notifyNow`  - The function will be triggered immediately with the current state.  Defaults to `false`.</li><li>`uncloned`   - If `true`, the watch function will not be attached to any clones of this prop.</li></ul> |
| **Returns**                                          | <ul><li>`cp.prop`        - The same `cp.prop` instance</li><li>`function`   - The watch function, which can be passed to [unwatch](#unwatch) to stop watching.</li></ul>          |
| **Notes**                                            | <ul><li>You can watch immutable values. Wrapped `cp.prop` instances may not be immutable, and any changes to them will cause watchers to be notified up the chain.</li></ul>                |

#### [wrap](#wrap)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.prop:wrap([owner[, key]]) -> cp.prop <anything>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a new property that wraps this one. It will be able to get and set the same as this, and changes                                                                                         |
| **Parameters**                                       | <ul><li>`owner`  -    (optional) If provided, the wrapper will be bound to the specified owner.</li><li>`key`    -    (optional) If provided, the wrapper will be assigned to the owner with the specified key.</li></ul> |
| **Returns**                                          | <ul><li>A new `cp.prop` which wraps this property.</li></ul>          |

