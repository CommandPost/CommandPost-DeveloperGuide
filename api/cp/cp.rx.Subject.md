# [docs](index.md) » cp.rx.Subject
---

`Subjects` function both as an [Observer](cp.rs.Observer.md) and as an [Observable](cp.rx.Observable.md). Subjects inherit all
`Observable` functions, including [subscribe](#subscribe). Values can also be pushed to the `Subject`, which will
be broadcasted to any subscribed [Observers](cp.rx.Observers.md).

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [onCompleted](#oncompleted)
 * [onError](#onerror)
 * [onNext](#onnext)
 * [subscribe](#subscribe)

## API Documentation

### Methods

#### [onCompleted](#oncompleted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Subject:onCompleted() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Signal to all [Observers](cp.rx.Observer.md) that the `Subject` will not produce any more values. |

#### [onError](#onerror)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Subject:onError(message) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Signal to all `Observers` that an error has occurred. |
| **Parameters**                                       | <ul><li>message     - A string describing what went wrong.</li></ul> |

#### [onNext](#onnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Subject:onNext(...) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Pushes zero or more values to the `Subject`. They will be broadcasted to all [Observers](cp.rx.Observer.md). |
| **Parameters**                                       | <ul><li>...       - The values to send.</li></ul> |

#### [subscribe](#subscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Subject:subscribe(onNext[, onError[, onCompleted]]) -> cp.rx.Reference` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new [Observer](cp.rx.Observer.md) and attaches it to the Subject. |
| **Parameters**                                       | <ul><li>observer | onNext     - Either an <a href="cp.rx.Observer.md">Observer</a>, or a <code>function</code> called                          when the <code>Subject</code> produces a value.</li><li>onError               - A <code>function</code> called when the <code>Subject</code> terminates due to an error.</li><li>onCompleted           - A <code>function</code> called when the <code>Subject</code> completes normally.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.Reference.md">Reference</a></li></ul> |

