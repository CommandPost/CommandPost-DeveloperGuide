# [docs](index.md) » cp.is
---

A simple class that lets you test if a value `is` a particular type.
Note: for best performance, assign the specific checks you want to use to local functions. Eg:

```lua
local is_nothing = require("cp.is").nothing
is_nothing(nil) == true
```

You can also get functions that negate the functions below by calling `is.nt.XXX(...)` (read: "isn't XXX").
The individual functions are not documented, but all will work as expected. Eg:

```lua
is.blank("") == true
is.nt.blank("") == false
```

They can also be assigned directly to local values for better performance:

```lua
local isnt_blank = is.nt.blank
isnt_blank(nil) == false
```

## API Overview
* Functions - API calls offered directly by the extension
 * [blank](#blank)
 * [boolean](#boolean)
 * [callable](#callable)
 * [falsey](#falsey)
 * [fn](#fn)
 * [list](#list)
 * [nothing](#nothing)
 * [number](#number)
 * [object](#object)
 * [something](#something)
 * [string](#string)
 * [table](#table)
 * [truthy](#truthy)
 * [userdata](#userdata)

## API Documentation

### Functions

#### [blank](#blank)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.blank(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a blank string value - either `nil` or `tostring(value) == ""`.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check.</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [boolean](#boolean)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.boolean(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a `function`.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [callable](#callable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.callable(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a callable - either a `function` or a `table` with `__call` in it's metatable hierarchy.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [falsey](#falsey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.falsey(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a `falsey` value.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [fn](#fn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.fn(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a `function`.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [list](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.list(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a `list`.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [nothing](#nothing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.nothing(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is `nil`.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [number](#number)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.number(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a `number`.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [object](#object)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.object(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a `object`.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [something](#something)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.something(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is not `nil`.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [string](#string)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.string(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a string.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [table](#table)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.table(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a `table`.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [truthy](#truthy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.truthy(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a `truthy` value.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

#### [userdata](#userdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.is.userdata(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the value is a `userdata` object.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the value to check</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul>            |

