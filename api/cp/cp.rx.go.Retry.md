# [docs](index.md) » cp.rx.go.Retry
---

_Extends:_ [Statement](cp.rx.go.Statement.md)

A [Statement](cp.rx.go.Statement.md) that will retry the contained statement if there is an error.
It can be limited to a set number of retries, and have a delay added between retries.

## API Overview
* Constants - Useful values which cannot be changed
 * [DelayedBy](#delayedby)
 * [UpTo](#upto)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Retry](#retry)
* Methods - API calls which can only be made on an object returned by a constructor
 * [DelayedBy](#delayedby)
 * [UpTo](#upto)

## API Documentation

### Constants

#### [DelayedBy](#delayedby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Retry.DelayedBy <cp.rx.go.Statement.Modifier>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `Statement.Modifier` that sets the delay between retries. |

#### [UpTo](#upto)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Retry.UpTo <cp.rx.go.Statement.Modifier>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `Statement.Modifier` that sets the number of times to retry. |

### Constructors

#### [Retry](#retry)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Retry(resolvable) -> Retry` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Retry` `Statement` that will retry the `resolveable` if it emits an error. |
| **Parameters**                                       | <ul><li>resolvable  - a <code>resolvable</code> value, which will be retried if it sends an <code>error</code> signal.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>.</li></ul> |

### Methods

#### [DelayedBy](#delayedby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Retry:DelayedBy(milliseconds) -> Retry.DelayedBy` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specify a time in millieconds to delay by. |
| **Parameters**                                       | <ul><li>milliseconds - The amount of time do delay between retries.</li></ul> |
| **Returns**                                          | <ul><li>The <code>DelayedBy</code> <code>Statement.Modifier</code>.</li></ul> |

#### [UpTo](#upto)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Retry:UpTo(count) -> Retry.UpTo` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the number of times to retry up to. |
| **Parameters**                                       | <ul><li>count  - The number of times to retry.</li></ul> |
| **Returns**                                          | <ul><li>The <code>UpTo</code> <code>Statement.Modifier</code>.</li></ul> |

