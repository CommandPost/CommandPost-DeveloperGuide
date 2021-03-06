# [docs](index.md) » cp.ui.Table
---

Represents an AXTable in the Apple Accessibility UX API.

## API Overview
* Functions - API calls offered directly by the extension
 * [cellTextValue](#celltextvalue)
 * [cellTextValueIs](#celltextvalueis)
 * [discloseRow](#discloserow)
 * [findRow](#findrow)
 * [is](#is)
 * [matches](#matches)
 * [matchesContent](#matchescontent)
 * [visitRow](#visitrow)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Table](#table)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contentUI](#contentui)
 * [horizontalScrollBarUI](#horizontalscrollbarui)
 * [isFocused](#isfocused)
 * [verticalScrollBarUI](#verticalscrollbarui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [columnsUI](#columnsui)
 * [deselectAll](#deselectall)
 * [deselectRow](#deselectrow)
 * [deselectRowAt](#deselectrowat)
 * [findCellUI](#findcellui)
 * [findColumnIndex](#findcolumnindex)
 * [loadLayout](#loadlayout)
 * [rowsUI](#rowsui)
 * [saveLayout](#savelayout)
 * [selectAll](#selectall)
 * [selectedRowsUI](#selectedrowsui)
 * [selectRow](#selectrow)
 * [selectRowAt](#selectrowat)
 * [showRow](#showrow)
 * [showRowAt](#showrowat)
 * [toCSV](#tocsv)
 * [topRowsUI](#toprowsui)
 * [viewFrame](#viewframe)

## API Documentation

### Functions

#### [cellTextValue](#celltextvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.cellTextValue(cell) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the cell's text value. |
| **Parameters**                                       | <ul><li><code>cell</code>   - The cell to check</li></ul> |
| **Returns**                                          | <ul><li>The combined text value of the cell.</li></ul> |

#### [cellTextValueIs](#celltextvalueis)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.cellTextValueIs(cell, value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the cell's text value equals `value`. |
| **Parameters**                                       | <ul><li><code>cell</code>   - The cell to check</li><li><code>value</code>  - The text value to compare.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the cell text value equals the provided <code>value</code>.</li></ul> |

#### [discloseRow](#discloserow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.discloseRow(row) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Discloses the row, if possible. |
| **Parameters**                                       | <ul><li><code>row</code>        - The row to disclose</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the row is disclosable and is now expanded.</li></ul> |

#### [findRow](#findrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.findRow(rows, names) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Finds the row at the sub-level named in the `names` table and returns it. |
| **Parameters**                                       | <ul><li><code>rows</code>       - The array of rows to process.</li><li><code>names</code>      - The array of names to navigate down</li></ul> |
| **Returns**                                          | <ul><li>The row that was visited, or <code>nil</code> if not.</li></ul> |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `Table`. |
| **Parameters**                                       | <ul><li><code>thing</code>      - The thing to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the thing is a <code>Table</code> instance.</li></ul> |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is a valid table. |
| **Parameters**                                       | <ul><li><code>element</code>    - The element to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches.</li></ul> |

#### [matchesContent](#matchescontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.matchesContent(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `element` is a valid table content element. |
| **Parameters**                                       | <ul><li><code>element</code>    - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is a valid content element.</li></ul> |

#### [visitRow](#visitrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.visitRow(rows, names) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Selects the row at the sub-level named in the `names` table. |
| **Parameters**                                       | <ul><li><code>rows</code>       - The array of rows to process.</li><li><code>names</code>      - The array of names to navigate down</li></ul> |
| **Returns**                                          | <ul><li>The row that was visited, or <code>nil</code> if not.</li></ul> |

### Constructors

#### [Table](#table)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table(parent, uiFinder) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Table. |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent object.</li><li><code>uiFinder</code>   - A <code>function</code> or <code>cp.prop</code> which will return the <code>axuielement</code> that this table represents.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Table</code> instance.</li></ul> |

### Fields

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `axuielement` that contains the actual rows. |

#### [horizontalScrollBarUI](#horizontalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.horizontalScrollBarUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The horizontal scroll bar UI element, if present. |

#### [isFocused](#isfocused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.isFocused <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns `true` if the table is focused by the user. |

#### [verticalScrollBarUI](#verticalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.verticalScrollBarUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The vertical scroll bar UI element, if present. |

### Methods

#### [columnsUI](#columnsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:columnsUI() -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Return a list of column headers, if present. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table of column headers. If the table is visible but no column headers are defined, an empty table is returned. If it's not visible, <code>nil</code> is returned.</li></ul> |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:deselectAll(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Deselects the specified rows. If `rowsUI` is `nil`, then all rows will be deselected. |
| **Parameters**                                       | <ul><li>rowUI - A table of <code>hs._asm.axuielement</code> objects for the rows you want to deselect.</li></ul> |

#### [deselectRow](#deselectrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:deselectRow(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Deselect a specific row. |
| **Parameters**                                       | <ul><li>rowUI - The <code>hs._asm.axuielement</code> object of the row you want to deselect.</li></ul> |

#### [deselectRowAt](#deselectrowat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:deselectRowAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Deselects a row at a specific index. |
| **Parameters**                                       | <ul><li>index - The index of the row you wish to deselect.</li></ul> |

#### [findCellUI](#findcellui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:findCellUI(rowNumber, columnId) -> `hs._asm.axuielement` | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds a specific Cell UI. |
| **Parameters**                                       | <ul><li>rowNumber - The row number.</li><li>columnId - The Column ID.</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs._asm.axuielement</code> object for the cell, or <code>nil</code> if the cell cannot be found.</li></ul> |

#### [findColumnIndex](#findcolumnindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:findColumnIndex(id) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the Column Index based on an `AXIdentifier` ID. |
| **Parameters**                                       | <ul><li>id - The <code>AXIdentifier</code> of the column index you want to find.</li></ul> |
| **Returns**                                          | <ul><li>A column index as a number, or <code>nil</code> if no index can be found.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a Table layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the Table layout settings - created using <code>cp.ui.Table:saveLayout()</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [rowsUI](#rowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:rowsUI([filterFn]) -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the list of rows in the table. An optional filter function may be provided. |
| **Parameters**                                       | <ul><li><code>filterFn</code>   - An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.</li></ul> |
| **Returns**                                          | <ul><li>Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be <code>nil</code>.</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current Table layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current Table Layout.</li></ul> |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectAll(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects the specified rows. If `rowsUI` is `nil`, then all rows will be selected. |
| **Parameters**                                       | <ul><li>rowUI - A table of <code>hs._asm.axuielement</code> objects for the rows you want to select.</li></ul> |

#### [selectedRowsUI](#selectedrowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectedRowsUI() -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Return a table of selected row UIs. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table of <code>hs._asm.axuielement</code> objects, or <code>nil</code> if none could be found.</li></ul> |

#### [selectRow](#selectrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectRow(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select a specific row. |
| **Parameters**                                       | <ul><li>rowUI - The <code>hs._asm.axuielement</code> object of the row you want to select.</li></ul> |

#### [selectRowAt](#selectrowat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectRowAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select a row at a specific index. |
| **Parameters**                                       | <ul><li>index - The index of the row you wish to select.</li></ul> |

#### [showRow](#showrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:showRow(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows a specific row. |
| **Parameters**                                       | <ul><li>rowUI - The <code>hs._asm.axuielement</code> object of the row you want to show.</li></ul> |

#### [showRowAt](#showrowat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:showRowAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows a row at a specific index. |
| **Parameters**                                       | <ul><li>index - The index of the row you wish to show.</li></ul> |

#### [toCSV](#tocsv)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:toCSV() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the contents of the table and formats it as a CSV string. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string or <code>nil</code> if an error occurs.</li></ul> |

#### [topRowsUI](#toprowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:topRowsUI(filterFn) -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a list of top-level rows in the table. An optional filter function may be provided. |
| **Parameters**                                       | <ul><li><code>filterFn</code>   - An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.</li></ul> |
| **Returns**                                          | <ul><li>Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be <code>nil</code>.</li></ul> |

#### [viewFrame](#viewframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:viewFrame() -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Table frame. |
| **Parameters**                                       | <ul><li>None</li></ul> |

