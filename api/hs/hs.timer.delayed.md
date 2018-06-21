# [docs](index.md) » hs.timer.delayed
---

Specialized timer objects to coalesce processing of unpredictable asynchronous events into a single callback

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [nextTrigger](#nexttrigger)
 * [running](#running)
 * [setDelay](#setdelay)
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed.new(delay, fn) -> hs.timer.delayed object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new delayed timer.                                                                                         |
| **Parameters**                                       |  * delay - number of seconds to wait for after a `:start()` invocation (the "callback countdown") * fn - a function to call after `delay` has fully elapsed without any further `:start()` invocations                                       |
| **Returns**                                          |  * a new `hs.timer.delayed` object                                                |
| **Notes**                                            |   * these timers are meant to be long-lived: once instantiated, there's no way to remove them from the run loop;    create them once at the module level.                                                      |

### Methods

#### [nextTrigger](#nexttrigger)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:nextTrigger() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the time left in the callback countdown                                                                                         |
| **Parameters**                                       |   * None                                       |
| **Returns**                                          |   * if the callback countdown is running, returns the number of seconds until it triggers; otherwise returns nil                                                |

#### [running](#running)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:running() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a boolean indicating whether the callback countdown is running                                                                                         |
| **Parameters**                                       |   * None                                       |
| **Returns**                                          |   * a boolean                                                |

#### [setDelay](#setdelay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:setDelay(delay) -> hs.timer.delayed object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Changes the callback countdown duration                                                                                         |
| **Parameters**                                       |   * None                                       |
| **Returns**                                          |   * the delayed timer object                                                |
| **Notes**                                            |   * if the callback countdown is running, calling this method will restart it                                                      |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:start([delay]) -> hs.timer.delayed object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts or restarts the callback countdown                                                                                         |
| **Parameters**                                       |   * delay - (optional) if provided, sets the countdown duration to this number of seconds    for this time only; subsequent calls to `:start()` will revert to the original delay (or    to the delay set with `:setDelay(delay)`)                                       |
| **Returns**                                          |   * the delayed timer object                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:stop() -> hs.timer.delayed object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Cancels the callback countdown, if running; the callback will therefore not be triggered                                                                                         |
| **Parameters**                                       |   * None                                       |
| **Returns**                                          |   * the delayed timer object                                                |

