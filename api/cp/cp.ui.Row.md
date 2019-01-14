# [docs](index.md) » cp.ui.Row
---

Represents an `AXRow` `axuielement`.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [Row](#row)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [disclosing](#disclosing)
 * [disclosureLevel](#disclosurelevel)
 * [index](#index)
 * [selected](#selected)
* Methods - API calls which can only be made on an object returned by a constructor
 * [disclosedByRow](#disclosedbyrow)
 * [disclosedRows](#disclosedrows)
 * [matches](#matches)

## API Documentation

### Constructors

#### [Row](#row)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Row(parent, uiFinder) -> cp.ui.Row` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Row` instance with the specified `parent` and `uiFinder`. |
| **Parameters**                                       | <ul><li>parent - the parent <code>Element</code>.</li><li>uiFinder - a <code>function</code> or <code>cp.prop</code> containing the <code>axuielement</code></li></ul> |
| **Returns**                                          | <ul><li>The new <code>Row</code>.</li></ul> |

### Fields

#### [disclosing](#disclosing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Row.disclosing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the `Row` is disclosing other `Rows`. |

#### [disclosureLevel](#disclosurelevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Row.disclosureLevel <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The depth of disclosure. `0` is the top level. |

#### [index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Row.index <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The numeric index of this row in the overall container, with `0` being the first item. |

#### [selected](#selected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Row.selected <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the row is currently selected. May be set. |

### Methods

#### [disclosedByRow](#disclosedbyrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Row:disclosedByRow() -> cp.ui.Row` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The `Row` which is disclosing this `Row`. |

#### [disclosedRows](#disclosedrows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Row:disclosedRows() -> table of cp.ui.Row or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | If available, returns a table of [Row](cp.ui.Row.md)s that are disclosed by this `Row`. |
| **Returns**                                          | <ul><li>The <code>table</code> of Rows, or <code>nil</code>.</li></ul> |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Row.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the element is a `Row`. |
| **Parameters**                                       | <ul><li>element - the <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches, otherwise <code>false</code>.</li></ul> |

