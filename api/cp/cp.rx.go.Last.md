# [docs](index.md) » cp.rx.go.Last
---

A `Statement` that will complete after the only the last result resolves.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [Last](#last)

## API Documentation

### Constructors

#### [Last](#last)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Last(resolvable) -> Last` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Last` `Statement` that will return the first value from the `resolvable` and complete. |
| **Parameters**                                       | <ul><li>resolvable  - a <code>resolvable</code> value, of which the first result will be returned.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> which will return the first value when executed.</li></ul> |

