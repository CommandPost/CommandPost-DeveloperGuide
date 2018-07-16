# [docs](index.md) » cp.rx.go.Require.IsNot
---

Specifies that the `Require`d value `IsNot` a specific value.

## API Overview
* Constants - Useful values which cannot be changed
 * [IsNot](#isnot)
* Methods - API calls which can only be made on an object returned by a constructor
 * [OrThrow](#orthrow)

## API Documentation

### Constants

#### [IsNot](#isnot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require.IsNot <cp.rx.go.SubStatement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `SubStatement` that sets a specific value all values from the `requirement` must not match. |

### Methods

#### [OrThrow](#orthrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require.IsNot:OrThrow(...) -> Require.OrThrow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies what is thrown if the [Require](cp.rx.go.Require.md) test fails. |
| **Parameters**                                       | <ul><li>...  - The list of <code>resolvable</code> items to process.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Require.OrThrow.md">Require.OrThrow</a> instance.</li></ul> |

