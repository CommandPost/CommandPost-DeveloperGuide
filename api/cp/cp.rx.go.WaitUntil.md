# [docs](index.md) » cp.rx.go.WaitUntil
---

A [Statement](cp.rx.go.Statement.md) that will wait for the first value from a `resolveable` that matches the predicate.

## API Overview
* Constants - Useful values which cannot be changed
 * [Are](#are)
 * [AreNot](#arenot)
 * [Is](#is)
 * [IsNot](#isnot)
 * [Matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [WaitUntil](#waituntil)
* Methods - API calls which can only be made on an object returned by a constructor
 * [Are](#are)
 * [AreNot](#arenot)
 * [Is](#is)
 * [IsNot](#isnot)
 * [Matches](#matches)

## API Documentation

### Constants

#### [Are](#are)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil.Are <cp.rx.go.SubStatement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `SubStatement` that sets the values to match. |

#### [AreNot](#arenot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil.AreNot <cp.rx.go.SubStatement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `SubStatement` that sets a value to skip over. |

#### [Is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil.Is <cp.rx.go.SubStatement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `SubStatement` that sets a specific value to wait for. |

#### [IsNot](#isnot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil.IsNot <cp.rx.go.SubStatement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `SubStatement` that sets a value that is skipped over. |

#### [Matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil.Matches <cp.rx.go.SubStatement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `SubStatement` that sets a predicate check values against. |

### Constructors

#### [WaitUntil](#waituntil)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil(requirement) -> WaitUntil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `WaitUntil` `Statement` with the specified `requirement`. |
| **Parameters**                                       | <ul><li>requirement  - a <code>resolvable</code> value that will be checked.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> instance which will check if the <code>resolvable</code> matches the requirement.</li></ul> |

### Methods

#### [Are](#are)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil:Are(value) -> WaitUntil.Are` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to check. |
| **Parameters**                                       | <ul><li>value  - The value to wait for.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Are</code> <code>SubStatement</code>.</li></ul> |

#### [AreNot](#arenot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil:AreNot(value) -> WaitUntil.AreNot` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to skip over. |
| **Parameters**                                       | <ul><li>value  - The value to skip over.</li></ul> |
| **Returns**                                          | <ul><li>The <code>AreNot</code> <code>SubStatement</code>.</li></ul> |

#### [Is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil:Is(value) -> WaitUntil.Is` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to check. |
| **Parameters**                                       | <ul><li>value  - The value to wait for.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Is</code> <code>SubStatement</code>.</li></ul> |

#### [IsNot](#isnot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil:IsNot(value) -> WaitUntil.IsNot` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to skip. |
| **Parameters**                                       | <ul><li>value  - The value to skip over.</li></ul> |
| **Returns**                                          | <ul><li>The <code>IsNot</code> <code>SubStatement</code>.</li></ul> |

#### [Matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.WaitUntil:Matches(predicate) -> WaitUntil.Matches` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the predicate function that will check the `requirement` results. |
| **Parameters**                                       | <ul><li>predicate  - The function that will get called to determine if it has been found.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Matches</code> <code>SubStatement</code>.</li></ul> |

