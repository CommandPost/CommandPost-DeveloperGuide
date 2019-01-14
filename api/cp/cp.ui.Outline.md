# [docs](index.md) » cp.ui.Outline
---

Represents an `AXOutline` `axuielement`.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Outline](#outline)
* Methods - API calls which can only be made on an object returned by a constructor
 * [childrenUI](#childrenui)
 * [columns](#columns)
 * [columnsUI](#columnsui)
 * [createColumn](#createcolumn)
 * [createRow](#createrow)
 * [fetchColumn](#fetchcolumn)
 * [fetchRow](#fetchrow)
 * [fetchRows](#fetchrows)
 * [filterRows](#filterrows)
 * [rows](#rows)
 * [rowsUI](#rowsui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `element` is an `Outline`. |

### Constructors

#### [Outline](#outline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline(parent, uiFinder) -> cp.ui.Outline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Outline` with the specified `parent` and `uiFinder`. |
| **Parameters**                                       | <ul><li>parent - The parent instance.</li><li>uiFinder - A <code>function</code> or a <code>cp.prop</code> which will return the <code>AXOutline</code> <code>axuielement</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Outline</code> instance.</li></ul> |

### Methods

#### [childrenUI](#childrenui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:childrenUI() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides a `table` containing the `axuielement`s which are children of the outline. |

#### [columns](#columns)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:columns() -> table of cp.ui.Columns` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the list of [Column](cp.ui.Column.md)s in this `Outline`. |

#### [columnsUI](#columnsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:columnsUI() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides a `table` containing the `axuielement`s which are columns of the outline. |

#### [createColumn](#createcolumn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:createColumn(columnUI) -> cp.ui.Column` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to create a new [Column](cp.ui.Column.md) with the provided `columnUI` `axuielement`. |
| **Parameters**                                       | <ul><li>columnUI - the <code>AXColumn</code> <code>axuielement</code> to create a <a href="cp.ui.Column.md">Column</a> for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.ui.Column.md">Column</a> or an error if a problem occurred.</li></ul> |
| **Notes**                                            | <ul><li>Subclasses which want to provide a custom <a href="cp.ui.Column.md">Column</a> implementation should override this method.</li></ul> |

#### [createRow](#createrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:createRow(rowUI) -> cp.ui.Row` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to create a new [Row](cp.ui.Row.md) with the provided `rowUI` `axuielement`. |
| **Parameters**                                       | <ul><li>rowUI - the <code>AXRow</code> <code>axuielement</code> to create a <a href="cp.ui.Row.md">Row</a> for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.ui.Row.md">Row</a> or an error if a problem occurred.</li></ul> |
| **Notes**                                            | <ul><li>Subclasses which want to provide a custom <a href="cp.ui.Row.md">Row</a> implementation should override this method.</li></ul> |

#### [fetchColumn](#fetchcolumn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:fetchColumn(columnsUI) -> table of cp.ui.Columns` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` of the same length as `columnsUI`. |
| **Parameters**                                       | <ul><li>columnsUI - The list of <code>AXColumn</code> <code>axuielement</code>s to find.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> with the same number of elements, containing the matching <a href="cp.ui.Column.md">Column</a> instances.</li></ul> |

#### [fetchRow](#fetchrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:fetchRow(rowUI) -> cp.ui.Row or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the [Row](cp.ui.Row.md) that represents the provided `rowUI`, if it is actually present |
| **Parameters**                                       | <ul><li>rowUI - The <code>axuielement</code> for the <code>AXRow</code> to find a <a href="cp.ui.Row.md">Row</a> for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.ui.Row.md">Row</a>, or <code>nil</code> if the <code>rowUI</code> is not in this <code>Outline</code>.</li></ul> |

#### [fetchRows](#fetchrows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:fetchRows(rowsUI) -> table of cp.ui.Rows` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` of the same length as `rowsUI`. |
| **Parameters**                                       | <ul><li>rowsUI - The list of <code>AXRow</code> <code>axuielement</code>s to find.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> with the same number of elements, containing the matching <a href="cp.ui.Row.md">Row</a> instances.</li></ul> |

#### [filterRows](#filterrows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:filterRows(matcherFn) -> table of cp.ui.Rows or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table only containing [Row](cp.ui.Row.md)s which pass the predicate `matcherFn`. |
| **Parameters**                                       | <ul><li>matcherFn - the <code>function</code> that will accept a <a href="cp.ui.Row.md">Row</a> and return a <code>boolean</code>.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> of <a href="cp.ui.Row.md">Row</a>s, or <code>nil</code> if no UI is currently available.</li></ul> |

#### [rows](#rows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:rows() -> table of cp.ui.Row or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides a `table` with the list of `cp.ui.Row` elements for the rows. |
| **Returns**                                          | <ul><li>A table containing the list of <a href="cp.ui.Row.md">Row</a>s in the <code>Outline</code>, or <code>nil</code> if the <code>Outline</code> is not presently available.</li></ul> |

#### [rowsUI](#rowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Outline:rowsUI() -> table of axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides a `table` containing the `axuielement`s which are rows in the outline. |

