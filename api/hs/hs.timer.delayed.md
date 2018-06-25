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
| **Parameters**                                       | <ul><br /><li>delay - number of seconds to wait for after a <code>:start()</code> invocation (the "callback countdown") * fn - a function to call after <code>delay</code> has fully elapsed without any further <code>:start()</code> invocations</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a new <code>hs.timer.delayed</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>these timers are meant to be long-lived: once instantiated, there's no way to remove them from the run loop;    create them once at the module level.</li><br /></ul>                                             |

### Methods

#### [nextTrigger](#nexttrigger)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:nextTrigger() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the time left in the callback countdown                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>if the callback countdown is running, returns the number of seconds until it triggers; otherwise returns nil</li><br /></ul>                                           |

#### [running](#running)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:running() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a boolean indicating whether the callback countdown is running                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a boolean</li><br /></ul>                                           |

#### [setDelay](#setdelay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:setDelay(delay) -> hs.timer.delayed object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Changes the callback countdown duration                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the delayed timer object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>if the callback countdown is running, calling this method will restart it</li><br /></ul>                                             |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:start([delay]) -> hs.timer.delayed object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts or restarts the callback countdown                                                                                         |
| **Parameters**                                       | <ul><br /><li>delay - (optional) if provided, sets the countdown duration to this number of seconds    for this time only; subsequent calls to <code>:start()</code> will revert to the original delay (or    to the delay set with <code>:setDelay(delay)</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the delayed timer object</li><br /></ul>                                           |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.delayed:stop() -> hs.timer.delayed object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Cancels the callback countdown, if running; the callback will therefore not be triggered                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the delayed timer object</li><br /></ul>                                           |

