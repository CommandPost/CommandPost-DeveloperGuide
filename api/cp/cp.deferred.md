# [docs](index.md) » cp.deferred
---

This extension makes it simple to defer multiple actions after a delay from the initial execution.
 Unlike `hs.timer.delayed`, the delay will not be extended
with subsequent `run()` calls, but the delay will trigger again if `run()` is called again later.

For example:

```lua
local update = deferred.new(1) -- defer 1 second
:action(function() print("Updated!"") end)
-- do something
update()
-- do something else
update()
-- one second after the inital call to `update()`, one "Updated!" is printed.
```

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [action](#action)
 * [delay](#delay)
 * [run](#run)
 * [secondsRemaining](#secondsremaining)
 * [stop](#stop)
 * [waiting](#waiting)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred.new(delay) -> cp.deferred` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `defer` instance, which will trigger any added `action`s by a set delay after                                                                                         |
| **Parameters**                                       | * delay     - The number of seconds to delay when `run()` is initally called.                                       |
| **Returns**                                          | * The new `cp.deferred` instance.                                                |

### Methods

#### [action](#action)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:action(actionFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the `action` the the list that will be called when the timer goes off.                                                                                         |
| **Parameters**                                       | * The callable action.                                       |

#### [delay](#delay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:delay([value]) -> self | number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets/gets the delay period. If no `value` is provided, the current delay is returned.                                                                                         |
| **Parameters**                                       | * value     - the new delay value.                                       |
| **Returns**                                          | * The `cp.deferred` instance if a new value is provided, or the current delay if not.                                                |

#### [run](#run)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:run() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Ensures that the actions will run after the `delay`.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `cp.deferred` instance.                                                |

#### [secondsRemaining](#secondsremaining)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:secondsRemaining() -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the number of seconds until the next execution, or `nil` if it's not running.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The number of seconds until execution.                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:stop() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops any execution of any deferred actions, if it is currently running.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The deferred timer.                                                |

#### [waiting](#waiting)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:waiting() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the defer is currently waiting to run.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `true` if the deferred action is waiting to execute.                                                |

