# [docs](index.md) » cp.ui.MenuButton
---

Menu Button Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [MenuButton](#menubutton)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [menuUI](#menuui)
 * [title](#title)
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doPress](#dopress)
 * [doSelectItem](#doselectitem)
 * [doSelectItemMatching](#doselectitemmatching)
 * [doSelectValue](#doselectvalue)
 * [doShowMenu](#doshowmenu)
 * [getTitle](#gettitle)
 * [getValue](#getvalue)
 * [loadLayout](#loadlayout)
 * [press](#press)
 * [saveLayout](#savelayout)
 * [selectItem](#selectitem)
 * [selectItemMatching](#selectitemmatching)
 * [setValue](#setvalue)
 * [show](#show)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [MenuButton](#menubutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton(parent, uiFinder) -> MenuButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new MenuButton. |
| **Parameters**                                       | <ul><li>parent        - The parent object. Should have an <code>isShowing</code> property.</li><li>uiFinder      - A <code>cp.prop</code> or function which will return a <code>hs._asm.axuielement</code>, or <code>nil</code> if it's not available.</li></ul> |

### Fields

#### [menuUI](#menuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton.menuUI <cp.prop: hs._asm.axuielement; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `AXMenu` for the MenuButton if it is currently visible. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton.title <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the title for the MenuButton. |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton.value <cp.prop: anything>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns or sets the current MenuButton value. |

### Methods

#### [doPress](#dopress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:doPress() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that presses the `MenuButton`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |

#### [doSelectItem](#doselectitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:doSelectItem(index) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will select an item on the `MenuButton` by index. |
| **Parameters**                                       | <ul><li>index - The index number of the item to match.</li></ul> |
| **Returns**                                          | <ul><li>the <code>Statement</code>.</li></ul> |

#### [doSelectItemMatching](#doselectitemmatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:doSelectItemMatching(pattern[, altPattern]) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will select an item on the `MenuButton` by pattern. |
| **Parameters**                                       | <ul><li>pattern - The pattern to match.</li><li>[altPattern] - An optional alternate pattern to match if the first pattern fails.</li></ul> |
| **Returns**                                          | <ul><li>the <code>Statement</code>.</li></ul> |

#### [doSelectValue](#doselectvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:doSelectValue(value) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will select an item on the `MenuButton` by value. |
| **Parameters**                                       | <ul><li>value - The value of the item to match.</li></ul> |
| **Returns**                                          | <ul><li>the <code>Statement</code>.</li></ul> |

#### [doShowMenu](#doshowmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:doShowMenu() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that presses the `MenuButton` if the menu is not showing. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:getTitle() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the `MenuButton` title. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>MenuButton</code> title as string, or <code>nil</code> if the title cannot be determined.</li></ul> |

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:getValue() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the `MenuButton` value. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>MenuButton</code> value as string, or <code>nil</code> if the value cannot be determined.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a `MenuButton` layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the <code>MenuButton</code> layout settings - created using <a href="#saveLayout">saveLayout</a>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:press() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Presses the MenuButton. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current `MenuButton` layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current <code>MenuButton</code> Layout.</li></ul> |

#### [selectItem](#selectitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:selectItem(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select an item on the `MenuButton` by index. |
| **Parameters**                                       | <ul><li>index - The index of the item you want to select.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully selected, otherwise <code>false</code>.</li></ul> |

#### [selectItemMatching](#selectitemmatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:selectItemMatching(pattern) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select an item on the `MenuButton` by pattern. |
| **Parameters**                                       | <ul><li>pattern - A pattern used to select the <code>MenuButton</code> item.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully selected, otherwise <code>false</code>.</li></ul> |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:setValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the `MenuButton` value. |
| **Parameters**                                       | <ul><li>value - The value you want to set the <code>MenuButton</code> to.</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's the MenuButton. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

