# [docs](index.md) » cp.rx.go.Require
---

A `Statement` that will require that the `resolvable` value matches a predicate,
and if not, it will send an error.

## Submodules
 * [cp.rx.go.Require.Are](cp.rx.go.Require.Are.md)
 * [cp.rx.go.Require.AreNot](cp.rx.go.Require.AreNot.md)
 * [cp.rx.go.Require.Is](cp.rx.go.Require.Is.md)
 * [cp.rx.go.Require.IsNot](cp.rx.go.Require.IsNot.md)
 * [cp.rx.go.Require.Matches](cp.rx.go.Require.Matches.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [OrThrow](#orthrow)
* Functions - API calls offered directly by the extension
 * [Require](#require)
* Methods - API calls which can only be made on an object returned by a constructor
 * [Are](#are)
 * [AreNot](#arenot)
 * [Is](#is)
 * [IsNot](#isnot)
 * [Matches](#matches)
 * [OrThrow](#orthrow)

## API Documentation

### Constants

#### [OrThrow](#orthrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require.OrThrow <cp.rx.go.SubStatement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `SubStatement` that sets the message to throw if the requirement is not met. |

### Functions

#### [Require](#require)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require(requirement) -> Require` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new `Require` `Statement` with the specified `requirement`. |
| **Parameters**                                       | <ul><li>requirement  - a <code>resolvable</code> value that will be checked.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> instance which will check if the <code>requirement</code> matches the requirement.</li></ul> |

### Methods

#### [Are](#are)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require:Are(value) -> Require.Are` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to check. |
| **Parameters**                                       | <ul><li>value  - The value that all results from the <code>requirement</code> must match.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Are</code> <code>SubStatement</code>.</li></ul> |

#### [AreNot](#arenot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require:AreNot(value) -> Require.AreNot` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to check. |
| **Parameters**                                       | <ul><li>value  - The value that all results from the <code>requirement</code> must match.</li></ul> |
| **Returns**                                          | <ul><li>The <code>AreNot</code> <code>SubStatement</code>.</li></ul> |

#### [Is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require:Is(value) -> Require.Is` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to check. |
| **Parameters**                                       | <ul><li>value  - The value that all results from the <code>requirement</code> must match.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Is</code> <code>SubStatement</code>.</li></ul> |

#### [IsNot](#isnot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require:IsNot(value) -> Require.IsNot` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to check. |
| **Parameters**                                       | <ul><li>value  - The value that all results from the <code>requirement</code> must not match.</li></ul> |
| **Returns**                                          | <ul><li>The <code>IsNot</code> <code>SubStatement</code>.</li></ul> |

#### [Matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require:Matches(predicate) -> Require.Matches` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the predicate to check. |
| **Parameters**                                       | <ul><li>value  - The value that all results from the <code>requirement</code> must not match.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Matches</code> <code>SubStatement</code>.</li></ul> |

#### [OrThrow](#orthrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Require:OrThrow(message) -> Require.OrThrow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the message to throw if the requirement is not met. |
| **Parameters**                                       | <ul><li>message  - The string to throw when there is an error.</li></ul> |
| **Returns**                                          | <ul><li>The <code>OrThrow</code> <code>SubStatement</code>.</li></ul> |

