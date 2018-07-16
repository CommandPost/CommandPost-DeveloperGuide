# [docs](index.md) » cp.rx.go.Do
---

A [Statement](cp.rx.go.Statement.md) that will execute the provided `resolvable` values.
This will resolve the provided values into [Observables](cp.rx.Observable.md) and pass on the
first result of each to the next stage as individual parameters.
This will continue until one of the `Observables` has completed, at which
point other results from values are ignored.

For example:

```lua
Do(Observable.of(1, 2, 3), Observable.of("a", "b"))
:Now(function(number, letter) print(tostring(number)..letter))
```

This will result in:

```
1a
2b
```

For more power, you can add a [Then](#Then) to futher modify the results, or chain other operations.

## Submodules
 * [cp.rx.go.Do.Then](cp.rx.go.Do.Then.md)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [Do](#do)
* Methods - API calls which can only be made on an object returned by a constructor
 * [Then](#then)

## API Documentation

### Constructors

#### [Do](#do)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Do(...) -> Do` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Begins the definition of a `Do` `Statement`. |
| **Parameters**                                       | <ul><li>...      - the list of <code>resolvable</code> values to evaluate.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Do</code> <code>Statement</code> instance.</li></ul> |

### Methods

#### [Then](#then)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Do:Then(...) -> Do.Then` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call this to define what will happen once the `Do` values resolve successfully. |
| **Parameters**                                       | <ul><li>...  - The list of <code>resolveable</code> values to process for each <code>Do</code> result.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Do.Then.md">Then</a> <a href="cp.rx.go.SubStatement.md">SubStatement</a>.</li></ul> |

