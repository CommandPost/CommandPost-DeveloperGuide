# [docs](index.md) » cp.rx.go.Given
---

A [Statement](cp.rx.go.Statement.md) that will execute the provided `resolvable` values.
This will resolve the provided values into [Observables](cp.rx.Observable.md) and pass on the
first result of each to the next stage as individual parameters.
This will continue until one of the `Observables` has completed, at which
point other results from values are ignored.

## Submodules
 * [cp.rx.go.Given.Then](cp.rx.go.Given.Then.md)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [Given](#given)
* Methods - API calls which can only be made on an object returned by a constructor
 * [Then](#then)

## API Documentation

### Constructors

#### [Given](#given)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Given(...) -> Given` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Begins the definition of a `Given` `Statement`. |
| **Parameters**                                       | <ul><li>...      - the list of <code>resolvable</code> values to evaluate.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Given</code> <code>Statement</code> instance.</li></ul> |

### Methods

#### [Then](#then)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Given:Then(...) -> Given.Then` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call this to define what will happen once the `Given` values resolve successfully. |
| **Parameters**                                       | <ul><li>...  - The list of <code>resolveable</code> values to process for each <code>Given</code> result.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Given.Then.md">Then</a> <a href="cp.rx.go.Statement.Modifier.md">Statement.Modifier</a>.</li></ul> |

