# [docs](index.md) » cp.ui.Cell
---

Represents an `AXCell` `axuielement`.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [childrenUI](#childrenui)
 * [columnIndexRange](#columnindexrange)
 * [rowIndexRange](#rowindexrange)
 * [selected](#selected)
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [textValueIs](#textvalueis)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Cell.matches(element) ->  boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `element` is an `AXCell`. |

### Fields

#### [childrenUI](#childrenui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Cell.childrenUI <cp.prop: table of axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The list of `axuielement`s which are children of this `Cell`. |

#### [columnIndexRange](#columnindexrange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Cell.columnIndexRange <cp.prop: table; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns a table of `{len,loc}`, which indicates if the cell covers multiple columns. |

#### [rowIndexRange](#rowindexrange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Cell.rowIndexRange <cp.prop: table; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns a table of `{len,loc}`, which indicates if the cell covers multiple rows. |

#### [selected](#selected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Cell.selected <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the cell is currently selected. |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Cell.value <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The cell value, if it is a string. |

### Methods

#### [textValueIs](#textvalueis)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Cell.textValueIs(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the cell's text value equals `value`. |
| **Parameters**                                       | <ul><li><code>value</code>  - The text value to compare.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the cell text value equals the provided <code>value</code>.</li></ul> |

