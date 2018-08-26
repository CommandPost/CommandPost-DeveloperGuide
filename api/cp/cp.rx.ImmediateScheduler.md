# [docs](index.md) » cp.rx.ImmediateScheduler
---

Schedules `Observables` by running all operations immediately.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [create](#create)
* Methods - API calls which can only be made on an object returned by a constructor
 * [schedule](#schedule)

## API Documentation

### Constructors

#### [create](#create)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.ImmediateScheduler.create() -> cp.rx.ImmediageScheduler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ImmediateScheduler`. |
| **Returns**                                          | <ul><li>The new <code>ImmediateScheduler</code>.</li></ul> |

### Methods

#### [schedule](#schedule)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.ImmediateScheduler:schedule(action) -> cp.rx.Reference` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Schedules a `function` to be run on the scheduler. It is executed immediately. |
| **Parameters**                                       | <ul><li>action    - The <code>function</code> to execute.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.Reference.md">Reference</a>.</li></ul> |

