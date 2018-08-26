# [docs](index.md) » cp.rx.TimeoutScheduler
---

A scheduler that uses the `hs.timer` library to schedule events on an event loop.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [create](#create)
 * [schedule](#schedule)
 * [stopAll](#stopall)

## API Documentation

### Methods

#### [create](#create)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.TimeoutScheduler.create() -> cp.rx.TimeoutScheduler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new `TimeoutScheduler`. |
| **Returns**                                          | <ul><li>The new <code>TimeoutScheduler</code>.</li></ul> |

#### [schedule](#schedule)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.TimeoutScheduler:schedule(action[, delay]) -> cp.rx.TimeoutScheduler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Schedules an action to run at a future point in time. |
| **Parameters**                                       | <ul><li>action  - The action to run.</li><li>delay   - The delay, in milliseconds. Defaults to <code>0</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.Reference.md">Reference</a>.</li></ul> |

#### [stopAll](#stopall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.TimeoutScheduler:stopAll() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops all future timers from running and clears them. |

