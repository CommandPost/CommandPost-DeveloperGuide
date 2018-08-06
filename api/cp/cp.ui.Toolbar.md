# [docs](index.md) » cp.ui.Toolbar
---

Toolbar Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [frame](#frame)
 * [isShowing](#isshowing)
 * [overflowButton](#overflowbutton)
 * [selectedTitle](#selectedtitle)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [doSelect](#doselect)
 * [isEnabled](#isenabled)
 * [parent](#parent)

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

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar.new(parent, finder) -> cp.ui.Toolbar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Toolbar` instance, given the specified `parent` and `finder` |
| **Parameters**                                       | <ul><li>parent   - The parent object.</li><li>finder   - The <code>cp.prop</code> or <code>function</code> that finds the <code>hs._asm.axuielement</code> that represents the <code>Toolbar</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Toolbar</code> instance.</li></ul> |

### Fields

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar.frame <cp.prop: table; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the table containing the `x`, `y`, `w`, and `h` values for the Toolbar frame, or `nil` if not available. |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | If `true`, the `Toolbar` is showing on screen. |

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

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Retrieves the `axuielement` for the `Toolbar`, or `nil` if not available.. |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the app instance. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [doSelect](#doselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar:doSelect(title) -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will select the toolbar item with the specified title. |
| **Parameters**                                       | <ul><li>title - The title to select, if present.</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code> that when executed returns <code>true</code> if the item was found and selected, otherwise <code>false</code>.</li></ul> |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns `true` if the Toolbar is visible and enabled. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the Toolbar is visible and enabled.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Toolbar:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the parent object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>parent</li></ul> |

