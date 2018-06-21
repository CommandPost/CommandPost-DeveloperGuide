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
| **Parameters**                                       |  * `cell`	- The cell to check                                       |
| **Returns**                                          |  * The combined text value of the cell.                                                |

#### [cellTextValueIs](#celltextvalueis)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.cellTextValueIs(cell, value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the cell's text value equals `value`.                                                                                         |
| **Parameters**                                       |  * `cell`	- The cell to check * `value`	- The text value to compare.                                       |
| **Returns**                                          |  * `true` if the cell text value equals the provided `value`.                                                |

#### [discloseRow](#discloserow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.discloseRow(row) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Discloses the row, if possible.                                                                                         |
| **Parameters**                                       |  * `row`		- The row to disclose                                       |
| **Returns**                                          |  * `true` if the row is disclosable and is now expanded.                                                |

#### [findRow](#findrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.findRow(rows, names) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Finds the row at the sub-level named in the `names` table and returns it.                                                                                         |
| **Parameters**                                       |  * `rows`		- The array of rows to process. * `names`		- The array of names to navigate down                                       |
| **Returns**                                          |  * The row that was visited, or `nil` if not.                                                |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `thing` is a `Table`.                                                                                         |
| **Parameters**                                       |  * `thing`		- The thing to check                                       |
| **Returns**                                          |  * `true` if the thing is a `Table` instance.                                                |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the element is a valid table.                                                                                         |
| **Parameters**                                       |  * `element`	- The element to check.                                       |
| **Returns**                                          |  * `true` if it matches.                                                |

#### [matchesContent](#matchescontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.matchesContent(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `element` is a valid table content element.                                                                                         |
| **Parameters**                                       |  * `element`	- The element to check                                       |
| **Returns**                                          |  * `true` if the element is a valid content element.                                                |

#### [visitRow](#visitrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.visitRow(rows, names) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects the row at the sub-level named in the `names` table.                                                                                         |
| **Parameters**                                       |  * `rows`		- The array of rows to process. * `names`		- The array of names to navigate down                                       |
| **Returns**                                          |  * The row that was visited, or `nil` if not.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.new(parent, finder) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Table.                                                                                         |
| **Parameters**                                       |  * `parent`		- The parent object. * `finder`		- A function which will return the `axuielement` that this table represents.                                       |
| **Returns**                                          |  * A new `Table` instance.                                                |

### Methods

#### [columnsUI](#columnsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:columnsUI() -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a list of column headers, if present.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Table of column headers. If the table is visible but no column headers are defined, an empty table is returned. If it's not visible, `nil` is returned.                                                |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:deselectAll(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deselects the specified rows. If `rowsUI` is `nil`, then all rows will be deselected.                                                                                         |
| **Parameters**                                       |  * rowUI - A table of `hs._asm.axuielement` objects for the rows you want to deselect.                                       |

#### [deselectRow](#deselectrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:deselectRow(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deselect a specific row.                                                                                         |
| **Parameters**                                       |  * rowUI - The `hs._asm.axuielement` object of the row you want to deselect.                                       |

#### [deselectRowAt](#deselectrowat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:deselectRowAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deselects a row at a specific index.                                                                                         |
| **Parameters**                                       |  * index - The index of the row you wish to deselect.                                       |

#### [findCellUI](#findcellui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:findCellUI(rowNumber, columnId) -> `hs._asm.axuielement` | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a specific Cell UI.                                                                                         |
| **Parameters**                                       |  * rowNumber - The row number. * columnId - The Column ID.                                       |
| **Returns**                                          |  * A `hs._asm.axuielement` object for the cell, or `nil` if the cell cannot be found.                                                |

#### [findColumnIndex](#findcolumnindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:findColumnIndex(id) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the Column Index based on an `AXIdentifier` ID.                                                                                         |
| **Parameters**                                       |  * id - The `AXIdentifier` of the column index you want to find.                                       |
| **Returns**                                          |  * A column index as a number, or `nil` if no index can be found.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Table layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the Table layout settings - created using `cp.ui.Table:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:parent() -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The table's parent, as provided in the constructor.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The table's parent.                                                |

#### [rowsUI](#rowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:rowsUI([filterFn]) -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the list of rows in the table. An optional filter function may be provided.                                                                                         |
| **Parameters**                                       |  * `filterFn`	- An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.                                       |
| **Returns**                                          |  * Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be `nil`.                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Table layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current Table Layout.                                                |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectAll(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects the specified rows. If `rowsUI` is `nil`, then all rows will be selected.                                                                                         |
| **Parameters**                                       |  * rowUI - A table of `hs._asm.axuielement` objects for the rows you want to select.                                       |

#### [selectedRowsUI](#selectedrowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectedRowsUI() -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a table of selected row UIs.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Table of `hs._asm.axuielement` objects, or `nil` if none could be found.                                                |

#### [selectRow](#selectrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectRow(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select a specific row.                                                                                         |
| **Parameters**                                       |  * rowUI - The `hs._asm.axuielement` object of the row you want to select.                                       |

#### [selectRowAt](#selectrowat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:selectRowAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select a row at a specific index.                                                                                         |
| **Parameters**                                       |  * index - The index of the row you wish to select.                                       |

#### [showRow](#showrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:showRow(rowUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows a specific row.                                                                                         |
| **Parameters**                                       |  * rowUI - The `hs._asm.axuielement` object of the row you want to show.                                       |

#### [showRowAt](#showrowat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:showRowAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows a row at a specific index.                                                                                         |
| **Parameters**                                       |  * index - The index of the row you wish to show.                                       |

#### [topRowsUI](#toprowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:topRowsUI(filterFn) -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a list of top-level rows in the table. An optional filter function may be provided.                                                                                         |
| **Parameters**                                       |  * `filterFn`	- An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.                                       |
| **Returns**                                          |  * Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be `nil`.                                                |

#### [uncached](#uncached)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:uncached() -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Calling this will force the table to look up the `axuielement` on demand, rather than caching the result.                                                                                         |
| **Parameters**                                       |  * None                                       |

#### [viewFrame](#viewframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:viewFrame() -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Table frame.                                                                                         |
| **Parameters**                                       |  * None                                       |

