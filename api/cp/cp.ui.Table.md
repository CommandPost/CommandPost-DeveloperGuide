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
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [columnsUI](#columnsui)
 * [deselectAll](#deselectall)
 * [deselectRow](#deselectrow)
 * [deselectRowAt](#deselectrowat)
 * [findCellUI](#findcellui)
 * [findColumnIndex](#findcolumnindex)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [rowsUI](#rowsui)
 * [saveLayout](#savelayout)
 * [selectAll](#selectall)
 * [selectedRowsUI](#selectedrowsui)
 * [selectRow](#selectrow)
 * [selectRowAt](#selectrowat)
 * [showRow](#showrow)
 * [showRowAt](#showrowat)
 * [topRowsUI](#toprowsui)
 * [uncached](#uncached)
 * [viewFrame](#viewframe)

## API Documentation

### Functions

#### [cellTextValue](#celltextvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.cellTextValue(cell) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the cell's text value.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>cell</code>   - The cell to check</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The combined text value of the cell.</li><br /></ul>                                           |

#### [cellTextValueIs](#celltextvalueis)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.cellTextValueIs(cell, value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the cell's text value equals `value`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>cell</code>   - The cell to check * <code>value</code>   - The text value to compare.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the cell text value equals the provided <code>value</code>.</li><br /></ul>                                           |

#### [discloseRow](#discloserow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.discloseRow(row) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Discloses the row, if possible.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>row</code>        - The row to disclose</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the row is disclosable and is now expanded.</li><br /></ul>                                           |

#### [findRow](#findrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.findRow(rows, names) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Finds the row at the sub-level named in the `names` table and returns it.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>rows</code>       - The array of rows to process. * <code>names</code>       - The array of names to navigate down</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The row that was visited, or <code>nil</code> if not.</li><br /></ul>                                           |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `thing` is a `Table`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>thing</code>      - The thing to check</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the thing is a <code>Table</code> instance.</li><br /></ul>                                           |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the element is a valid table.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>element</code>    - The element to check.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if it matches.</li><br /></ul>                                           |

#### [matchesContent](#matchescontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.matchesContent(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `element` is a valid table content element.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>element</code>    - The element to check</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the element is a valid content element.</li><br /></ul>                                           |

#### [visitRow](#visitrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.visitRow(rows, names) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects the row at the sub-level named in the `names` table.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>rows</code>       - The array of rows to process. * <code>names</code>       - The array of names to navigate down</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The row that was visited, or <code>nil</code> if not.</li><br /></ul>                                           |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.new(parent, finder) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Table.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>parent</code>     - The parent object. * <code>finder</code>     - A function which will return the <code>axuielement</code> that this table represents.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A new <code>Table</code> instance.</li><br /></ul>                                           |

### Methods

#### [columnsUI](#columnsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:columnsUI() -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a list of column headers, if present.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table of column headers. If the table is visible but no column headers are defined, an empty table is returned. If it's not visible, <code>nil</code> is returned.</li><br /></ul>                                           |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:deselectAll(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deselects the specified rows. If `rowsUI` is `nil`, then all rows will be deselected.                                                                                         |
| **Parameters**                                       | <ul><br /><li>rowUI - A table of <code>hs._asm.axuielement</code> objects for the rows you want to deselect.</li><br /></ul>                                        |

#### [deselectRow](#deselectrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:deselectRow(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deselect a specific row.                                                                                         |
| **Parameters**                                       | <ul><br /><li>rowUI - The <code>hs._asm.axuielement</code> object of the row you want to deselect.</li><br /></ul>                                        |

#### [deselectRowAt](#deselectrowat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:deselectRowAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deselects a row at a specific index.                                                                                         |
| **Parameters**                                       | <ul><br /><li>index - The index of the row you wish to deselect.</li><br /></ul>                                        |

#### [findCellUI](#findcellui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:findCellUI(rowNumber, columnId) -> `hs._asm.axuielement` | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a specific Cell UI.                                                                                         |
| **Parameters**                                       | <ul><br /><li>rowNumber - The row number. * columnId - The Column ID.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A <code>hs._asm.axuielement</code> object for the cell, or <code>nil</code> if the cell cannot be found.</li><br /></ul>                                           |

#### [findColumnIndex](#findcolumnindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:findColumnIndex(id) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the Column Index based on an `AXIdentifier` ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li>id - The <code>AXIdentifier</code> of the column index you want to find.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A column index as a number, or <code>nil</code> if no index can be found.</li><br /></ul>                                           |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Table layout.                                                                                         |
| **Parameters**                                       | <ul><br /><li>layout - A table containing the Table layout settings - created using <code>cp.ui.Table:saveLayout()</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:parent() -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The table's parent, as provided in the constructor.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The table's parent.</li><br /></ul>                                           |

#### [rowsUI](#rowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:rowsUI([filterFn]) -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the list of rows in the table. An optional filter function may be provided.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>filterFn</code>   - An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be <code>nil</code>.</li><br /></ul>                                           |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Table layout to a table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing the current Table Layout.</li><br /></ul>                                           |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectAll(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects the specified rows. If `rowsUI` is `nil`, then all rows will be selected.                                                                                         |
| **Parameters**                                       | <ul><br /><li>rowUI - A table of <code>hs._asm.axuielement</code> objects for the rows you want to select.</li><br /></ul>                                        |

#### [selectedRowsUI](#selectedrowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectedRowsUI() -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a table of selected row UIs.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table of <code>hs._asm.axuielement</code> objects, or <code>nil</code> if none could be found.</li><br /></ul>                                           |

#### [selectRow](#selectrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectRow(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select a specific row.                                                                                         |
| **Parameters**                                       | <ul><br /><li>rowUI - The <code>hs._asm.axuielement</code> object of the row you want to select.</li><br /></ul>                                        |

#### [selectRowAt](#selectrowat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectRowAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select a row at a specific index.                                                                                         |
| **Parameters**                                       | <ul><br /><li>index - The index of the row you wish to select.</li><br /></ul>                                        |

#### [showRow](#showrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:showRow(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows a specific row.                                                                                         |
| **Parameters**                                       | <ul><br /><li>rowUI - The <code>hs._asm.axuielement</code> object of the row you want to show.</li><br /></ul>                                        |

#### [showRowAt](#showrowat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:showRowAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows a row at a specific index.                                                                                         |
| **Parameters**                                       | <ul><br /><li>index - The index of the row you wish to show.</li><br /></ul>                                        |

#### [topRowsUI](#toprowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:topRowsUI(filterFn) -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a list of top-level rows in the table. An optional filter function may be provided.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>filterFn</code>   - An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be <code>nil</code>.</li><br /></ul>                                           |

#### [uncached](#uncached)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:uncached() -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Calling this will force the table to look up the `axuielement` on demand, rather than caching the result.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |

#### [viewFrame](#viewframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:viewFrame() -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Table frame.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |

