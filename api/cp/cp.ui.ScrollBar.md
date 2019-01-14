# [docs](index.md) » cp.ui.ScrollBar
---

Provides access to `AXScrollBar` `axuielement` values.

## API Overview
* Constants - Useful values which cannot be changed
 * [HORIZONTAL_ORIENTATION](#horizontal_orientation)
 * [VERTICAL_ORIENTATION](#vertical_orientation)
* Constructors - API calls which return an object, typically one that offers API methods
 * [ScrollBar](#scrollbar)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [hidden](#hidden)
 * [horizontal](#horizontal)
 * [orientation](#orientation)
 * [value](#value)
 * [vertical](#vertical)
* Methods - API calls which can only be made on an object returned by a constructor
 * [loadLayout](#loadlayout)
 * [matches](#matches)
 * [saveLayout](#savelayout)

## API Documentation

### Constants

#### [HORIZONTAL_ORIENTATION](#horizontal_orientation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar.HORIZONTAL_ORIENTATION <string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The value for `AXOrientation` when it is horizontal. |

#### [VERTICAL_ORIENTATION](#vertical_orientation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar.VERTICAL_ORIENTATION <string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The value for `AXOrientation` when it is vertical. |

### Constructors

#### [ScrollBar](#scrollbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar(parent, uiFinder) -> cp.ui.ScrollBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ScrollBar` instance with the specified `parent` and `uiFinder`. |
| **Parameters**                                       | <ul><li>parent - the parent object.</li><li>uiFinder - a <code>function</code> or <code>cp.prop</code> that provides the <code>AXScrollBar</code> <code>axuielement</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>ScrollBar</code>.</li></ul> |

### Fields

#### [hidden](#hidden)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar.hidden <cp.prop: boolean; read-only, live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is `true` if the `ScrollBar` is currently hidden. |

#### [horizontal](#horizontal)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar.horizontal <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is `true` if the `ScrollBar` is horizontal, otherwise `false`. |

#### [orientation](#orientation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar.orientation <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `AXOrientation` string. |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar.value <cp.prop: number; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is the numeric scroll value, typically between `0.0` and `1.0`. May be set. |

#### [vertical](#vertical)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar.vertical <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is `true` if the `ScrollBar` is vertical, otherwise `false`. |

### Methods

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar:loadLayout(layout)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads the provided `layout` table of configuration parameters. |
| **Parameters**                                       | <ul><li>layout - the table of parameters.</li></ul> |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the element is a `ScrollBar`. |
| **Parameters**                                       | <ul><li>element - The <code>axuielement</code> being matched.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches, otherwise <code>false</code>.</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollBar:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the `ScrollBar` layout configuration. |
| **Returns**                                          | <ul><li>a <code>table</code> with the configuration parameters.</li></ul> |

