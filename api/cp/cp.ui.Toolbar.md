# [docs](index.md) » cp.ui.Toolbar
---

Toolbar Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Toolbar](#toolbar)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [overflowButton](#overflowbutton)
 * [selectedTitle](#selectedtitle)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doSelect](#doselect)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `element` is a `Button`, returning `true` if so. |
| **Parameters**                                       | <ul><li>element      - The <code>hs._asm.axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the <code>element</code> is a <code>Button</code>, or <code>false</code> if not.</li></ul> |

### Constructors

#### [Toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar(parent, uiFinder) -> cp.ui.Toolbar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Toolbar` instance, given the specified `parent` and `uiFinder` |
| **Parameters**                                       | <ul><li>parent   - The parent object.</li><li>uiFinder   - The <code>cp.prop</code> or <code>function</code> that finds the <code>hs._asm.axuielement</code> that represents the <code>Toolbar</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Toolbar</code> instance.</li></ul> |

### Fields

#### [overflowButton](#overflowbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar.overflowButton <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "overflow" button which appears if there are more toolbar items |

#### [selectedTitle](#selectedtitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar.selectedTitle <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The title of the first selected item, if available. |

### Methods

#### [doSelect](#doselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar:doSelect(title) -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will select the toolbar item with the specified title. |
| **Parameters**                                       | <ul><li>title - The title to select, if present.</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code> that when executed returns <code>true</code> if the item was found and selected, otherwise <code>false</code>.</li></ul> |

