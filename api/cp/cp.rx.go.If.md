# [docs](index.md) » cp.rx.go.If
---

A `Statement` that will check if a `resolvable` matches a predicate, then executes other `resolvables`.

## Submodules
 * [cp.rx.go.If.Are](cp.rx.go.If.Are.md)
 * [cp.rx.go.If.AreNot](cp.rx.go.If.AreNot.md)
 * [cp.rx.go.If.Is](cp.rx.go.If.Is.md)
 * [cp.rx.go.If.IsNot](cp.rx.go.If.IsNot.md)
 * [cp.rx.go.If.Matches](cp.rx.go.If.Matches.md)
 * [cp.rx.go.If.Then](cp.rx.go.If.Then.md)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [If](#if)
* Methods - API calls which can only be made on an object returned by a constructor
 * [Are](#are)
 * [AreNot](#arenot)
 * [Is](#is)
 * [IsNot](#isnot)
 * [Matches](#matches)
 * [Then](#then)

## API Documentation

### Constructors

#### [If](#if)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If(value) -> If` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `If` `Statement` which will check the first result of `value`. |
| **Parameters**                                       | <ul><li>requirement  - a <code>resolvable</code> value that will be checked.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> instance which will check if the <code>resolvable</code> matches the requirement.</li></ul> |

### Methods

#### [Are](#are)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If:Are(value) -> If.Are` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to check. |
| **Parameters**                                       | <ul><li>value  - The value to wait for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.If.Are.md">Are</a> <a href="cp.rx.go.Statement.Modifier.md">Statement.Modifier</a>.</li></ul> |

#### [AreNot](#arenot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If:AreNot(value) -> If.AreNot` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to check. |
| **Parameters**                                       | <ul><li>value  - The value to not match.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.If.AreNot.md">AreNot</a> <a href="cp.rx.go.Statement.Modifier.md">Statement.Modifier</a>.</li></ul> |

#### [Is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If:Is(value) -> If.Is` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to check. |
| **Parameters**                                       | <ul><li>value  - The value to check for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.If.Is.md">Is</a> <a href="cp.rx.go.Statement.Modifier.md">Statement.Modifier</a>.</li></ul> |

#### [IsNot](#isnot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If:IsNot(value) -> If.IsNot` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the value to not match. |
| **Parameters**                                       | <ul><li>value  - The value to check for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.If.IsNot.md">IsNot</a> <a href="cp.rx.go.Statement.Modifier.md">Statement.Modifier</a>.</li></ul> |

#### [Matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If:Matches(predicate) -> If.Matches` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the predicate function that will check the `value` results. |
| **Parameters**                                       | <ul><li>predicate  - The function that will get called to determine if it has been found.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.If.Matches.md">Matches</a> <a href="cp.rx.go.Statement.Modifier.md">Statement.Modifier</a>.</li></ul> |

#### [Then](#then)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.If:Then(...) -> If.Then` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call this to define what will happen if value resolves successfully. |
| **Parameters**                                       | <ul><li>...  - The list of <code>resolveable</code> values to process for the successful <code>If</code> result.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Then</code> <code>Statement.Modifier</code>.</li></ul> |

