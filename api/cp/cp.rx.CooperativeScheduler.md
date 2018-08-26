# [docs](index.md) » cp.rx.CooperativeScheduler
---

Manages [Observables](cp.rx.Observer.md) using `coroutines` and a virtual clock that must be updated
manually.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [create](#create)
* Methods - API calls which can only be made on an object returned by a constructor
 * [isEmpth](#isempth)
 * [schedule](#schedule)
 * [update](#update)

## API Documentation

### Constructors

#### [create](#create)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.CooperativeScheduler.create([currentTime]) -> cp.rx.CooperativeScheduler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `CooperativeScheduler`. |
| **Parameters**                                       | <ul><li>currentTime     - A time to start the scheduler at. Defaults to <code>0</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>CooperativeScheduler</code>.</li></ul> |

### Methods

#### [isEmpth](#isempth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.CooperativeScheduler:isEmpth() -> cp.rx.CooperativeScheduler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns whether or not the `CooperativeScheduler`'s queue is empty. |
| **Returns**                                          | <ul><li><code>true</code> if the scheduler is empty, otherwise <code>false</code>.</li></ul> |

#### [schedule](#schedule)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.CooperativeScheduler:schedule(action[, delay]) -> cp.rx.Reference` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Schedules a `function` to be run after an optional delay.  Returns a [Reference](cp.rx.Reference.md) that will stop |
| **Parameters**                                       | <ul><li>action      - The <code>function</code> to execute. Will be converted into a coroutine. The                coroutine may yield execution back to the scheduler with an optional                number, which will put it to sleep for a time period.</li><li>delay       - Delay execution of the action by a virtual time period. Defaults to <code>0</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.Reference.md">Reference</a>.</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.CooperativeScheduler:update(delta) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Triggers an update of the `CooperativeScheduler`. The clock will be advanced and the scheduler |
| **Parameters**                                       | <ul><li>delta     - An amount of time to advance the clock by. It is common to pass in the</li></ul> |

