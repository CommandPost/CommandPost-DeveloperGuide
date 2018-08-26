# [docs](index.md) » cp.rx.Reference
---

A handle representing the link between an [Observer](cp.rx.Observer.md) and an [Observable](cp.rx.Observable.md), as well as any
work required to clean up after the Observable completes or the Observer cancels.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [create](#create)
* Methods - API calls which can only be made on an object returned by a constructor
 * [cancel](#cancel)

## API Documentation

### Constructors

#### [create](#create)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Reference.create(action) -> cp.rx.Reference` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Reference. |
| **Parameters**                                       | <ul><li>action - The action to run when the reference is canceld. It will only be run once.</li></ul> |
| **Returns**                                          | <ul><li>the <a href="cp.rx.Reference.md">Reference</a>.</li></ul> |

### Methods

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Reference:cancel() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Unsubscribes the reference, performing any necessary cleanup work. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

