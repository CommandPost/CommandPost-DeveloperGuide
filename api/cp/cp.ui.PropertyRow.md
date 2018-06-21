# [docs](index.md) » cp.ui.PropertyRow
---

Represents a single property row, typically in a Property Inspector.

## API Overview
* Functions - API calls offered directly by the extension
 * [isParent](#isparent)
 * [matches](#matches)
 * [parentUIFinder](#parentuifinder)
 * [prepareParent](#prepareparent)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isShowing](#isshowing)
 * [label](#label)
 * [labelUI](#labelui)
 * [propertiesUI](#propertiesui)
 * [reset](#reset)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [children](#children)
 * [hide](#hide)
 * [labelKeys](#labelkeys)
 * [parent](#parent)
 * [show](#show)

## API Documentation

### Functions

#### [isParent](#isparent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.isParent(parent) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `parent` has been prepared via [prepareParent](#prepareParent).                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if the parent is prepared.                                                |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the provided `axuielement` could be a property row.                                                                                         |
| **Parameters**                                       |  * element   - The element to check.                                       |
| **Returns**                                          |  * `true` if the element could be a property row.                                                |

#### [parentUIFinder](#parentuifinder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.parentUIFinder(parent) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the `cp.prop` which finds the `hs._asm.axuielement` that contains property rows from the parent.                                                                                         |
| **Parameters**                                       |  * parent        - The parent which has a finder assigned.                                       |
| **Returns**                                          |  * The `cp.prop` which provides access to the finder, or `nil`.                                                |

#### [prepareParent](#prepareparent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.prepareParent(parent, uiFinder) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Call this to make `parent` table ready to be a parent of `PropertyRow`s.                                                                                         |
| **Parameters**                                       |  * parent    - The parent table. * uiFinder  - The function or cp.prop which will be called to find the parent UI element. Functions will be passed the `parent` when being executed.                                       |
| **Returns**                                          |  * None                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.new(parent, labelKey[, index]) -> cp.ui.PropertyRow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `PropertyRow` with the specified parent and label key.                                                                                         |
| **Parameters**                                       |  * parent        - The parent object. * labelKey      - The key of the label that the row will map to. * index         - The row number with the same label to get. Defaults to `1`.                                       |
| **Returns**                                          |  * The new `PropertyRow` instance.                                                |

### Fields

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the row is showing.                                                                                         |

#### [label](#label)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.label <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The label of the property row, in the current langauge.                                                                                         |

#### [labelUI](#labelui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.labelUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` containing the row label.                                                                                         |

#### [propertiesUI](#propertiesui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.propertiesUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` from the parent that contains the properties.                                                                                         |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.reset <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `reset` button for the row, which may or may not actually exist.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `axuielement` for the row.                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [children](#children)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow:children() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a table of children for the Property Row.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table of children or `nil`.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the `PropertyRow`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * self                                                |

#### [labelKeys](#labelkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow:labelKeys() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the key of the label that the row will map to.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * string                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * parent                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the `PropertyRow`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * self                                                |

