# [docs](index.md) » cp.rx.go.Require.AreNot
---

Specifies that the `Require`d values `AreNot` a specific value.

## API Overview
* Constants - Useful values which cannot be changed
 * [AreNot](#arenot)
* Methods - API calls which can only be made on an object returned by a constructor
 * [OrThrow](#orthrow)

## API Documentation

### Constants

#### [AreNot](#arenot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require.AreNot <cp.rx.go.Statement.Modifier>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `Statement.Modifier` that sets a specific value all values from the `requirement` must not match. |

### Methods

#### [OrThrow](#orthrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require.AreNot:OrThrow(...) -> Require.OrThrow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies what is thrown if the [Require](cp.rx.go.Require.md) test fails. |
| **Parameters**                                       | <ul><li>...  - The list of <code>resolvable</code> items to process.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Require.OrThrow.md">Require.OrThrow</a> instance.</li></ul> |

