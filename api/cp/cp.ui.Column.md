# [docs](index.md) » cp.ui.Column
---

Represents an `AXColumn` `axuielement`.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [index](#index)
 * [selected](#selected)
* Methods - API calls which can only be made on an object returned by a constructor
 * [rows](#rows)
 * [visibleRows](#visiblerows)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Column.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `axuielement` is a `Column`. |
| **Parameters**                                       | <ul><li>element - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is a Column.</li></ul> |

### Fields

#### [index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Column.index <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The numeric index of this column in the overall container, with `0` being the first item. |

#### [selected](#selected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Column.selected <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the column is currently selected. May be set. |

### Methods

#### [rows](#rows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Column:rows() -> table of cp.ui.Row or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` of [Row](cp.ui.Row.md)s contained in the Column. |
| **Returns**                                          | <ul><li>The <code>table</code>, or <code>nil</code> if the column's UI is not available.</li></ul> |

#### [visibleRows](#visiblerows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Column:visibleRows() -> table of cp.ui.Rows or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` of [Row](cp.ui.Row.md)s which are currently visible on screen. |
| **Returns**                                          | <ul><li>The <code>table</code>, or <code>nil</code> if the column's UI is not available.</li></ul> |

