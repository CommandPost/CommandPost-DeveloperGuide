# [docs](index.md) » cp.rx.go.Require.Matches
---

Specifies that the `Require`d value `Matches` a function predicate.

## API Overview
* Constants - Useful values which cannot be changed
 * [Matches](#matches)
* Methods - API calls which can only be made on an object returned by a constructor
 * [OrThrow](#orthrow)

## API Documentation

### Constants

#### [Matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require.Matches <cp.rx.go.SubStatement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `SubStatement` that sets a predicate function that checks values from the `requirement`. |

### Methods

#### [OrThrow](#orthrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require.Matches:OrThrow(...) -> Require.OrThrow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies what is thrown if the [Require](cp.rx.go.Require.md) test fails. |
| **Parameters**                                       | <ul><li>...  - The list of <code>resolvable</code> items to process.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Require.OrThrow.md">Require.OrThrow</a> instance.</li></ul> |

