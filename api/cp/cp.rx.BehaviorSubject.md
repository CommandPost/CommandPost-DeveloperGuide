# [docs](index.md) » cp.rx.BehaviorSubject
---

A [Subject](cp.rx.Subject.md) that tracks its current value. Provides an accessor to retrieve the most
recent pushed value, and all subscribers immediately receive the latest value.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [create](#create)
 * [getValue](#getvalue)
 * [onNext](#onnext)
 * [subscribe](#subscribe)

## API Documentation

### Methods

#### [create](#create)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.BehaviorSubject.create(...) -> cp.rx.BehaviorSubject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new `BehaviorSubject`. |
| **Parameters**                                       | <ul><li>...     - The initial values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>BehaviorSubject</code>.</li></ul> |

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.BehaviorSubject:getValue() -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the last value emitted by the `BehaviorSubject`, or the initial value passed to the |
| **Returns**                                          | <ul><li>The last value.</li></ul> |

#### [onNext](#onnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.BehaviorSubject:onNext(...) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Pushes zero or more values to the `BehaviorSubject`. They will be broadcasted to all [Observers](cp.rx.Observer.md). |
| **Parameters**                                       | <ul><li>...     - The values to send.</li></ul> |

#### [subscribe](#subscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.BehaviorSubject:subscribe(observer | onNext, onError, onCompleted) -> cp.rx.Reference` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new [Observer](cp.rx.Observer.md) and attaches it to the `BehaviorSubject`. Immediately broadcasts the most |
| **Parameters**                                       | <ul><li>observer | onNext       - The <a href="cp.rx.Observer.md">Observer</a> subscribing, or the <code>function</code> called when the                            <code>BehaviorSubject</code> produces a value.</li><li>onError                 - A <code>function</code> called when the <code>BehaviorSubject</code> terminates due to an error.</li><li>onCompleted             - A <code>function</code> called when the <code>BehaviorSubject</code> completes normally.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.Reference.md">Reference</a></li></ul> |

