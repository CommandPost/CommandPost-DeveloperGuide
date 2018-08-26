# [docs](index.md) » cp.rx.Observer
---

Observers are simple objects that receive values from [Observables](cp.rx.Observables.md).

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [create](#create)
* Methods - API calls which can only be made on an object returned by a constructor
 * [onCompleted](#oncompleted)
 * [onError](#onerror)
 * [onNext](#onnext)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observer.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Tests if the `thing` is an `Observer`. |
| **Parameters**                                       | <ul><li>thing   - The thing to test.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the thing is an <code>Observer</code>, otherwise <code>false</code>.</li></ul> |

### Constructors

#### [create](#create)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observer.create(onNext, onError, onCompleted) -> cp.rx.Observer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Observer. |
| **Parameters**                                       | <ul><li>onNext      - Called when the Observable produces a value.</li><li>onError     - Called when the Observable terminates due to an error.</li><li>onCompleted - Called when the Observable completes normally.</li></ul> |
| **Returns**                                          | <ul><li>The new Observer.</li></ul> |

### Methods

#### [onCompleted](#oncompleted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observer:onCompleted() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Notify the Observer that the sequence has completed and will produce no more values. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

#### [onError](#onerror)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observer:onError(message) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Notify the Observer that an error has occurred. |
| **Parameters**                                       | <ul><li>message  - A string describing what went wrong.</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

#### [onNext](#onnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observer:onNext(...) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Pushes zero or more values to the Observer. |
| **Parameters**                                       | <ul><li>...     - The list of values to send.</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

