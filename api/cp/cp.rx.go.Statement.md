# [docs](index.md) » cp.rx.go.Statement
---

A `Statement` is defined to enable processing of asynchronous `resolvable` values such
as [cp.rx.Observable](cp.rx.Observable.md) values.

To define a new `Statement`, you call the [named](#named) constructor, assigning the result
to a constant value and calling the [define](#define) method.

## Definine a new Statement

To define a new `Statement` implementation, we use the [Statement.named](cp.rx.go.Statement.md#named) constructor.
This gives us a [Statement.Definition](cp.rx.go.Statement.Definition.md) which allows
us to set the rules for the statement before finally "defining" it.

Statements *may* have an `onInit`, and *must* have an `onObservable` provided,
and then the `define` method must be called.

For example, the [First](cp.rx.go.First.md) statement is defined like so:

```lua
local First = Statement.named("First")
:onInit(function(context, resolvable)
    assert(resolvable ~= nil, "The First `resolveable` may not be `nil`.")
    context.resolvable = resolvable
end)
:onObservable(function(context)
    return toObservable(context.resolvable):first()
end)
:define()
```

Once you've defined a statement, you then execute it by calling the statement directly, passing
in any parameters.

For example:
```lua
local First = require("cp.rx.go").First
First(Observable.of(1, 2, 3))
:Now(
    function(value) print("Received: "..tostring(value)) end,
    function(message) print("Error: "..tostring(message)) end,
    function() print("Completed") end
)
```

This will output:
```
Received: 1
Completed
```

The `Observable` as passed to the `onInit` function handler as the second parameter.
`context` is always the first parameter, followed by any values passed to the constructor call.

The `onObservable` function handler is called once the statement is actually executing, typically
by calling the [Now](cp.rx.go.Statement.md#Now) or [After](cp.rx.go.Statement.md#After) methods.

> It is recommended that any conversion of input parameters are converted to `Observable`s as
> late as possible, typically in the `onObservable` function handler. Otherwise, input values
> may get resolved before the user intends.

## Submodules
 * [cp.rx.go.Statement.Definition](cp.rx.go.Statement.Definition.md)
 * [cp.rx.go.Statement.Modifier](cp.rx.go.Statement.Modifier.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [defaultObserverFactory](#defaultobserverfactory)
 * [is](#is)
 * [toObservable](#toobservable)
 * [toObservables](#toobservables)
* Constructors - API calls which return an object, typically one that offers API methods
 * [named](#named)
* Methods - API calls which can only be made on an object returned by a constructor
 * [After](#after)
 * [Catch](#catch)
 * [Debug](#debug)
 * [fullName](#fullname)
 * [Label](#label)
 * [name](#name)
 * [Now](#now)
 * [ThenDelay](#thendelay)
 * [TimeoutAfter](#timeoutafter)
 * [toObservable](#toobservable)

## API Documentation

### Functions

#### [defaultObserverFactory](#defaultobserverfactory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.defaultObserverFactory([factoryFn]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets/sets the factory function which creates a new `Observer` for Statements which are executed without one being provided. |
| **Parameters**                                       | <ul><li>factoryFn     - if provided, replaces the current default factory function.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Observer</code>, or the previous factory function if a new one was provided.</li></ul> |
| **Notes**                                            | <ul><li>The factory function has no arguments provided and must return a new <code>Observer</code> instance.</li></ul> |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `Statement`. |
| **Parameters**                                       | <ul><li>thing        - The thing to test.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the thing is a <code>Statement</code>.</li></ul> |

#### [toObservable](#toobservable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.toObservable(thing[, params]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Converts the `thing` into an `Observable`. It converts the following: |
| **Parameters**                                       | <ul><li>thing    - The thing to convert. * params   - Optional table list to pass as parameters for the <code>thing</code> if it's a <code>function</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Observable</code>.</li></ul> |

#### [toObservables](#toobservables)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.toObservables(things[, params]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Converts a list of things into a list of `Observables` of those things. |
| **Parameters**                                       | <ul><li>things       - a table list of things to convert to <code>Observables</code>. * params       - an optional table list of parameters to pass to any <code>function</code> things.</li></ul> |
| **Returns**                                          | <ul><li>A table list of the things, converted to <code>Observable</code>.</li></ul> |

### Constructors

#### [named](#named)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.named(name) -> Statement.Definition` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Starts the definition of a new `Statement` with the specified names. |
| **Parameters**                                       | <ul><li>name     - The name of the <code>Statement</code>.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.Definition.md">Statement.Definition</a>.</li></ul> |

### Methods

#### [After](#after)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:After(millis[, observer][, scheduler]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Requests the statement to be executed after the specified amount of time in seconds. |
| **Parameters**                                       | <ul><li>millis      - The number of milliseconds to delay the execution. * observer     - The observer to subscribe to the final result. * scheduler    - (optional) the <code>cp.rx.Scheduler</code> to use. Uses the <code>cp.rx.util.defaultScheduler()</code> if none is provided.</li></ul> |
| **Returns**                                          | <ul><li>Nothing.</li></ul> |

#### [Catch](#catch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:Catch(handler) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Assigns a handler which will be applied at the end of the Statement. |
| **Parameters**                                       | <ul><li>handler  - The handler function</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Statement</code>.</li></ul> |

#### [Debug](#debug)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:Debug([label]) -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates that the results of the `Statement` should be output to the Error Log. |
| **Parameters**                                       | <ul><li>label    - If specified, this is output in the log.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Statement</code> instance.</li></ul> |

#### [fullName](#fullname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:fullName()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Statement's full name. |
| **Returns**                                          | <ul><li>The full Statement name.</li></ul> |

#### [Label](#label)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:Label(label) -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the custom `label` for the Statement. This will |
| **Parameters**                                       | <ul><li>label - Optional new value for the label. If provided, the <code>Statement</code> is returned.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> if a new lable is specified, otherwise the current label value.</li></ul> |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:name()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Statement name. |
| **Returns**                                          | <ul><li>The Statement name.</li></ul> |

#### [Now](#now)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:Now([observer]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the statment immediately. |
| **Parameters**                                       | <ul><li>observer      - An observer to watch the resulting <code>Observable</code>. Defaults to the default observer factory.</li></ul> |
| **Returns**                                          | <ul><li>Nothing.</li></ul> |

#### [ThenDelay](#thendelay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:ThenDelay(millis) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates that there will be a delay after this statement by the |
| **Parameters**                                       | <ul><li>millis   - the amount of time to delay, in millisecods.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Statement</code>.</li></ul> |

#### [TimeoutAfter](#timeoutafter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:TimeoutAfter(millis[, next][, scheduler]) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates that this statement should time out after the specified number of milliseconds. |
| **Parameters**                                       | <ul><li>millis       - A <code>number</code> or a <code>function</code> returning the number of milliseconds to wait before timing out. * next         - Optional string or <code>resolvable</code> value indicating how to handle it. * scheduler    - The <code>cp.rx.Scheduler</code> to use when timing out. Defaults to <code>cp.rx.defaultScheduler()</code>.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Statement</code>.</li></ul> |

#### [toObservable](#toobservable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement:toObservable([preserveTimer]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` instance for the `Statement`. Unless `preserveTimer` is `true`, this will |
| **Parameters**                                       | <ul><li>preserveTimer    - If a timer has been set via <a href="#After">After</a>, don't cancel it. Defaults to <code>false</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Observable</code>.</li></ul> |

