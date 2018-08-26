# [docs](index.md) » cp.rx.go.List
---

_Extends:_ [Statement](cp.rx.go.Statement.md)

A [Statement](cp.rx.go.Statement.md) that will loop through a table as a list from item `1` to the table length.

## Submodules
 * [cp.rx.go.List.Sorted](cp.rx.go.List.Sorted.md)
 * [cp.rx.go.List.SortedBy](cp.rx.go.List.SortedBy.md)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [List](#list)
* Methods - API calls which can only be made on an object returned by a constructor
 * [Sorted](#sorted)
 * [SortedBy](#sortedby)

## API Documentation

### Constructors

#### [List](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.List(values) -> List` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `List` `Statement` that will loop through the provided table as a list. |
| **Parameters**                                       | <ul><li>values  - a <code>table</code> value, or a <code>function</code> which returns a table.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> which will return the first value when executed.</li></ul> |

### Methods

#### [Sorted](#sorted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.List:Sorted() -> List.Sorted` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates the List should be sorted by its natural order before being sent out individually. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Sorted</code> <code>Statement.Modifier</code>.</li></ul> |

#### [SortedBy](#sortedby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.List:SortedBy(...) -> List.SortedBy` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates the List should be sorted by the provided `function`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>SortedBy</code> <code>Statement.Modifier</code>.</li></ul> |

