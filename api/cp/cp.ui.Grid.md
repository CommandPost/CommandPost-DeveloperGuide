# [docs](index.md) » cp.ui.Grid
---

Abstract base class for `AX` elements which form a grid, such as [Table2](cp.ui.Table2.md) and [Outline](cp.ui.Outline.md).

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Grid](#grid)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [selectedRows](#selectedrows)
 * [selectedRowsUI](#selectedrowsui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [childrenUI](#childrenui)
 * [column](#column)
 * [columns](#columns)
 * [columnsUI](#columnsui)
 * [createColumn](#createcolumn)
 * [createRow](#createrow)
 * [doSelectRow](#doselectrow)
 * [fetchColumn](#fetchcolumn)
 * [fetchRow](#fetchrow)
 * [fetchRows](#fetchrows)
 * [filterRows](#filterrows)
 * [findCell](#findcell)
 * [findColumnIndex](#findcolumnindex)
 * [findRow](#findrow)
 * [row](#row)
 * [rows](#rows)
 * [rowsUI](#rowsui)
 * [selectRow](#selectrow)
 * [visitRow](#visitrow)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `Grid`. |
| **Parameters**                                       | <ul><li><code>thing</code>      - The thing to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the thing is a <code>Table</code> instance.</li></ul> |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `element` is an `Grid`. |

### Constructors

#### [Grid](#grid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid(parent, uiFinder) -> cp.ui.Grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Grid` with the specified `parent` and `uiFinder`. |
| **Parameters**                                       | <ul><li>parent - The parent instance.</li><li>uiFinder - A <code>function</code> or a <code>cp.prop</code> which will return the <code>axuielement</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Grid</code> instance.</li></ul> |

### Fields

#### [selectedRows](#selectedrows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid.selectedRows <cp.prop: table of cp.ui.Row; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains the list of currently-selected [Row](cp.ui.Row.md)s. Can be set. |

#### [selectedRowsUI](#selectedrowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid.selectedRowsUI <cp.prop: table of axuielement; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains the list of currently-selected row `axuilements`. Can be set. |
| **Notes**                                            | <ul><li>Also see [#selectedRows]</li></ul> |

### Methods

#### [childrenUI](#childrenui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:childrenUI() -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides a `table` containing the `axuielement`s which are children of the outline. |

#### [column](#column)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:column(index) -> cp.ui.Column or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides the [Column](cp.ui.Column.md) at the specified index, or `nil` if it's not available. |

#### [columns](#columns)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:columns() -> table of cp.ui.Columns` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the list of [Column](cp.ui.Column.md)s. |

#### [columnsUI](#columnsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:columnsUI() -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides a `table` containing the `axuielement`s which are columns of the outline. |

#### [createColumn](#createcolumn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:createColumn(columnUI) -> cp.ui.Column` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to create a new [Column](cp.ui.Column.md) with the provided `columnUI` `axuielement`. |
| **Parameters**                                       | <ul><li>columnUI - the <code>AXColumn</code> <code>axuielement</code> to create a <a href="cp.ui.Column.md">Column</a> for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.ui.Column.md">Column</a> or an error if a problem occurred.</li></ul> |
| **Notes**                                            | <ul><li>Subclasses which want to provide a custom <a href="cp.ui.Column.md">Column</a> implementation should override this method.</li></ul> |

#### [createRow](#createrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:createRow(rowUI) -> cp.ui.Row` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to create a new [Row](cp.ui.Row.md) with the provided `rowUI` `axuielement`. |
| **Parameters**                                       | <ul><li>rowUI - the <code>AXRow</code> <code>axuielement</code> to create a <a href="cp.ui.Row.md">Row</a> for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.ui.Row.md">Row</a> or an error if a problem occurred.</li></ul> |
| **Notes**                                            | <ul><li>Subclasses which want to provide a custom <a href="cp.ui.Row.md">Row</a> implementation should override this method.</li></ul> |

#### [doSelectRow](#doselectrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:doSelectRow(path) -> [Statement](cp.rx.go.Statement.md)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects the row at the sub-level named in the `path` table. |
| **Parameters**                                       | <ul><li>path - A <code>table</code> of names to navigate through to find the <a href="cp.ui.Row.md">Row</a> to select.</li></ul> |
| **Returns**                                          | <ul><li>The selected <a href="cp.ui.Row.md">Row</a>, or <code>nil</code> if not found.</li></ul> |

#### [fetchColumn](#fetchcolumn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:fetchColumn(columnsUI) -> table of cp.ui.Columns` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` of the same length as `columnsUI`. |
| **Parameters**                                       | <ul><li>columnsUI - The list of <code>AXColumn</code> <code>axuielement</code>s to find.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> with the same number of elements, containing the matching <a href="cp.ui.Column.md">Column</a> instances.</li></ul> |

#### [fetchRow](#fetchrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:fetchRow(rowUI) -> cp.ui.Row or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the [Row](cp.ui.Row.md) that represents the provided `rowUI`, if it is actually present. |
| **Parameters**                                       | <ul><li>rowUI - The <code>axuielement</code> for the <code>AXRow</code> to find a <a href="cp.ui.Row.md">Row</a> for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.ui.Row.md">Row</a>, or <code>nil</code> if the <code>rowUI</code> is not available.</li></ul> |

#### [fetchRows](#fetchrows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:fetchRows(rowsUI) -> table of cp.ui.Rows` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` of the same length as `rowsUI`. |
| **Parameters**                                       | <ul><li>rowsUI - The list of <code>AXRow</code> <code>axuielement</code>s to find.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> with the same number of elements, containing the matching <a href="cp.ui.Row.md">Row</a> instances.</li></ul> |

#### [filterRows](#filterrows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:filterRows(matcherFn) -> table of cp.ui.Rows or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table only containing [Row](cp.ui.Row.md)s which pass the predicate `matcherFn`. |
| **Parameters**                                       | <ul><li>matcherFn - the <code>function</code> that will accept a <a href="cp.ui.Row.md">Row</a> and return a <code>boolean</code>.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> of <a href="cp.ui.Row.md">Row</a>s, or <code>nil</code> if no UI is currently available.</li></ul> |

#### [findCell](#findcell)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:findCell(rowNumber, columnId) -> `hs._asm.axuielement` | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds a specific [Cell](cp.ui.Cell.md). |
| **Parameters**                                       | <ul><li>rowNumber - The row number.</li><li>columnId - The Column ID.</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs._asm.axuielement</code> object for the cell, or <code>nil</code> if the cell cannot be found.</li></ul> |

#### [findColumnIndex](#findcolumnindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:findColumnIndex(id) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the Column Index based on an `AXIdentifier` ID. |
| **Parameters**                                       | <ul><li>id - The <code>AXIdentifier</code> of the column index you want to find.</li></ul> |
| **Returns**                                          | <ul><li>A column index as a number, or <code>nil</code> if no index can be found.</li></ul> |

#### [findRow](#findrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:findRow(matcherFn) -> cp.ui.Row or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Row](cp.ui.Row.md) that has a result of `true` when passed to the `matcherFn` predicate, |
| **Parameters**                                       | <ul><li>matcherFn - The function to check the <a href="cp.ui.Row.md">Row</a> with.</li></ul> |
| **Returns**                                          | <ul><li>The matching <a href="cp.ui.Row.md">Row</a> or <code>nil</code>.</li></ul> |

#### [row](#row)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:row(index) -> cp.ui.Row or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides the [Row](cp.ui.Row.md) at the specified index, or `nil` if it's not available. |

#### [rows](#rows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:rows() -> table of cp.ui.Row or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides a `table` with the list of `cp.ui.Row` elements for the rows. |
| **Returns**                                          | <ul><li>A table containing the list of <a href="cp.ui.Row.md">Row</a>s, or <code>nil</code> if not presently available.</li></ul> |

#### [rowsUI](#rowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:rowsUI() -> table of axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides a `table` containing the `axuielement`s which are rows in the outline. |

#### [selectRow](#selectrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:selectRow(path) -> cp.ui.Row` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects the row at the sub-level named in the `path` table. |
| **Parameters**                                       | <ul><li>path - A <code>table</code> of names to navigate through to find the <a href="cp.ui.Row.md">Row</a> to select.</li></ul> |
| **Returns**                                          | <ul><li>The selected <a href="cp.ui.Row.md">Row</a>, or <code>nil</code> if not found.</li></ul> |

#### [visitRow](#visitrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Grid:visitRow(path, actionFn) -> cp.ui.Row` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Visits the row at the sub-level named in the `names` table, and executes the `actionFn`. |
| **Parameters**                                       | <ul><li><code>names</code>      - The array of names to navigate down</li><li><code>actionFn</code>   - A function to execute when the target row is found.</li></ul> |
| **Returns**                                          | <ul><li>The row that was visited, or <code>nil</code> if not.</li></ul> |

