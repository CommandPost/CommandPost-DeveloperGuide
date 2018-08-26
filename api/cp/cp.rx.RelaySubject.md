# [docs](index.md) » cp.rx.RelaySubject
---

A [Subject](cp.rx.Subject.md) that provides new [Observers](cp.rx.Observer.md) with some or all of the most recently
produced values upon reference.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [create](#create)
* Methods - API calls which can only be made on an object returned by a constructor
 * [onNext](#onnext)
 * [subscribe](#subscribe)

## API Documentation

### Constructors

#### [create](#create)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.RelaySubject.create([n]) -> cp.rx.RelaySubject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ReplaySubject`. |
| **Parameters**                                       | <ul><li>bufferSize      - The number of values to send to new subscribers. If <code>nil</code>, an infinite                    buffer is used (note that this could lead to memory issues).</li></ul> |
| **Returns**                                          | <ul><li>The new `ReplaySubject.</li></ul> |

### Methods

#### [onNext](#onnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.RelaySubject:onNext(...) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Pushes zero or more values to the `ReplaySubject`. They will be broadcasted to all [Observers](cp.rx.Observer.md). |
| **Parameters**                                       | <ul><li>...   - The values to send.</li></ul> |

#### [subscribe](#subscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.RelaySubject:subscribe([observer | onNext[, onError[, onCompleted]]]) -> cp.rx.Reference` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new [Observer](cp.rx.Observer.md) and attaches it to the `ReplaySubject`. |
| **Parameters**                                       | <ul><li>observer | onNext     - Either an <a href="cp.rx.Observer.md">Observer</a>, or a                          <code>function</code> to call when the <code>ReplaySubject</code> produces a value.</li><li>onError               - A <code>function</code> to call when the <code>ReplaySubject</code> terminates due to an error.</li><li>onCompleted           - A <code>function</code> to call when the ReplaySubject completes normally.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.Reference.md">Reference</a>.</li></ul> |

