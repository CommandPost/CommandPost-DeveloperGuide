# [docs](index.md) » cp.rx.AsyncSubject
---

`AsyncSubjects` are subjects that produce either no values or a single value.  If
multiple values are produced via `onNext`, only the last one is used.  If `onError` is called, then
no value is produced and `onError` is called on any subscribed [Observers](cp.rx.Observers.md).
If an [Observer](cp.rx.Observer.md) subscribes and the `AsyncSubject` has already terminated,
the `Observer` will immediately receive the value or the error.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [create](#create)
* Methods - API calls which can only be made on an object returned by a constructor
 * [onCompleted](#oncompleted)
 * [onError](#onerror)
 * [onNext](#onnext)
 * [subscribe](#subscribe)

## API Documentation

### Constructors

#### [create](#create)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.AsyncSubject.create() -> cp.rx.AsyncSubject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `AsyncSubject`. |
| **Returns**                                          | <ul><li>The new <code>AsyncSubject</code>.</li></ul> |

### Methods

#### [onCompleted](#oncompleted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.AsyncSubject:onCompleted() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Signal to all [Observers](cp.rx.Observers.md) that the `AsyncSubject` will not produce any more values. |

#### [onError](#onerror)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.AsyncSubject:onError(message) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Signal to all [Observers](cp.rx.Observer.md) that an error has occurred. |
| **Parameters**                                       | <ul><li>message     - A string describing what went wrong.</li></ul> |

#### [onNext](#onnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.AsyncSubject:onNext(...) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Pushes zero or more values to the `AsyncSubject`. |
| **Parameters**                                       | <ul><li>...       - The values to send.</li></ul> |

#### [subscribe](#subscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.AsyncSubject:subscribe(onNext, onError, onCompleted) -> cp.rx.Reference` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new [Observer](cp.rx.Observer.md) and attaches it to the `AsyncSubject`. |
| **Parameters**                                       | <ul><li>onNext | observer - A <code>function</code> called when the <code>AsyncSubject</code> produces a value                      or an existing <a href="cp.rx.Observer.md">Observer</a> to attach to the <code>AsyncSubject</code>.</li><li>onError           - A <code>function</code> called when the <code>AsyncSubject</code> terminates due to an error.</li><li>onCompleted       - A <code>funtion</code> called when the <code>AsyncSubject</code> completes normally.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.Reference.md">Reference</a>.</li></ul> |

