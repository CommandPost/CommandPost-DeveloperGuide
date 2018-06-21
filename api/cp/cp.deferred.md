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
| **Parameters**                                       | <ul><li>delay     - The number of seconds to delay when <code>run()</code> is initally called.</li></ul>   |
| **Returns**                                          | <ul><li>The new <code>cp.deferred</code> instance.</li></ul>            |

### Methods

#### [action](#action)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:action(actionFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the `action` the the list that will be called when the timer goes off.                                                                                         |
| **Parameters**                                       | <ul><li>The callable action.</li></ul>   |

#### [delay](#delay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:delay([value]) -> self | number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets/gets the delay period. If no `value` is provided, the current delay is returned.                                                                                         |
| **Parameters**                                       | <ul><li>value     - the new delay value.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.deferred</code> instance if a new value is provided, or the current delay if not.</li></ul>            |

#### [run](#run)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:run() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Ensures that the actions will run after the `delay`.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.deferred</code> instance.</li></ul>            |

#### [secondsRemaining](#secondsremaining)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:secondsRemaining() -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the number of seconds until the next execution, or `nil` if it's not running.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The number of seconds until execution.</li></ul>            |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:stop() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops any execution of any deferred actions, if it is currently running.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The deferred timer.</li></ul>            |

#### [waiting](#waiting)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.deferred:waiting() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the defer is currently waiting to run.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if the deferred action is waiting to execute.</li></ul>            |

