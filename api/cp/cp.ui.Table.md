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
 * [parent](#parent)
 * [rowsUI](#rowsui)
 * [topRowsUI](#toprowsui)
 * [uncached](#uncached)

## API Documentation

### Functions

#### [cellTextValue](#celltextvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.cellTextValue(cell) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the cell's text value.                                                                                         |
| **Parameters**                                       | <ul><li>`cell`	- The cell to check</li></ul> |
| **Returns**                                          | <ul><li>The combined text value of the cell.</li></ul>          |

#### [cellTextValueIs](#celltextvalueis)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.cellTextValueIs(cell, value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the cell's text value equals `value`.                                                                                         |
| **Parameters**                                       | <ul><li>`cell`	- The cell to check</li><li>`value`	- The text value to compare.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the cell text value equals the provided `value`.</li></ul>          |

#### [discloseRow](#discloserow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.discloseRow(row) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Discloses the row, if possible.                                                                                         |
| **Parameters**                                       | <ul><li>`row`		- The row to disclose</li></ul> |
| **Returns**                                          | <ul><li>`true` if the row is disclosable and is now expanded.</li></ul>          |

#### [findRow](#findrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.findRow(rows, names) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Finds the row at the sub-level named in the `names` table and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>`rows`		- The array of rows to process.</li><li>`names`		- The array of names to navigate down</li></ul> |
| **Returns**                                          | <ul><li>The row that was visited, or `nil` if not.</li></ul>          |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `thing` is a `Table`.                                                                                         |
| **Parameters**                                       | <ul><li>`thing`		- The thing to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if the thing is a `Table` instance.</li></ul>          |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the element is a valid table.                                                                                         |
| **Parameters**                                       | <ul><li>`element`	- The element to check.</li></ul> |
| **Returns**                                          | <ul><li>`true` if it matches.</li></ul>          |

#### [matchesContent](#matchescontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.matchesContent(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `element` is a valid table content element.                                                                                         |
| **Parameters**                                       | <ul><li>`element`	- The element to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if the element is a valid content element.</li></ul>          |

#### [visitRow](#visitrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.visitRow(rows, names) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects the row at the sub-level named in the `names` table.                                                                                         |
| **Parameters**                                       | <ul><li>`rows`		- The array of rows to process.</li><li>`names`		- The array of names to navigate down</li></ul> |
| **Returns**                                          | <ul><li>The row that was visited, or `nil` if not.</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table.new(parent, finder) -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Table.                                                                                         |
| **Parameters**                                       | <ul><li>`parent`		- The parent object.</li><li>`finder`		- A function which will return the `axuielement` that this table represents.</li></ul> |

### Methods

#### [columnsUI](#columnsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:columnsUI() -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a list of column headers, if present.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table of column headers. If the table is visible but no column headers are defined, an empty table is returned. If it's not visible, `nil` is returned.</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:parent() -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The table's parent, as provided in the constructor.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The table's parent.</li></ul>          |

#### [rowsUI](#rowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:rowsUI([filterFn]) -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the list of rows in the table. An optional filter function may be provided.                                                                                         |
| **Parameters**                                       | <ul><li>`filterFn`	- An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.</li></ul> |
| **Returns**                                          | <ul><li>Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be `nil`.</li></ul>          |

#### [topRowsUI](#toprowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:topRowsUI(filterFn) -> table of axuielements | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a list of top-level rows in the table. An optional filter function may be provided.                                                                                         |
| **Parameters**                                       | <ul><li>`filterFn`	- An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.</li></ul> |
| **Returns**                                          | <ul><li>Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be `nil`.</li></ul>          |

#### [uncached](#uncached)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Table:uncached() -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Calling this will force the table to look up the `axuielement` on demand, rather than caching the result.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |

