# [docs](index.md) » cp.rx.go.If.Then.Otherwise.Then
---

Each [Otherwise](cp.rx.go.If.Then.Otherwise.md) can have a subsequent `Then` which will be executed after the previous one resolves.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [Then](#then)

## API Documentation

### Methods

#### [Then](#then)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If.Then.Otherwise.Then:Then(...) -> If.Then.Otherwise.Then` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies additional `resolvables` to resolve after the previous `Then`. |
| **Parameters**                                       | <ul><li>...      - The list of <code>resolvable</code> values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Then</code> instance.</li></ul> |

