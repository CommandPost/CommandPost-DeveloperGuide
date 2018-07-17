# [docs](index.md) » cp.rx.go.If.Then
---

A `Statement.Modifier` that defines what happens when an `If` matches.

## Submodules
 * [cp.rx.go.If.Then.Otherwise](cp.rx.go.If.Then.Otherwise.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [Then](#then)
* Methods - API calls which can only be made on an object returned by a constructor
 * [Otherwise](#otherwise)
 * [Then](#then)

## API Documentation

### Constants

#### [Then](#then)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If.Then <cp.rx.go.Statement.Modifier>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | This is a configuration of `If`, which should be created via `If:Then(...)`. |

### Methods

#### [Otherwise](#otherwise)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If.Then:Otherwise(...) -> If.Then.Otherwise` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call this to define what will happen if value doesn't resolve successfully. |
| **Parameters**                                       | <ul><li>...  - The list of <code>resolveable</code> values to process for the unsuccessful <code>If</code> result.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Then</code> <code>Statement.Modifier</code>.</li></ul> |

#### [Then](#then)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If.Then:Then(...) -> If.Then` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Each [Then](cp.rx.go.If.Then.md) can have a subsequent `Then` which will be executed after the previous one resolves. |
| **Parameters**                                       | <ul><li>...  - The list of <code>resolvable</code> values to process for the sucessful <code>If</code> result.</li></ul> |
| **Returns**                                          | <ul><li>A new <a href="cp.rx.go.If.Then.md">If.Then</a> instance.</li></ul> |

