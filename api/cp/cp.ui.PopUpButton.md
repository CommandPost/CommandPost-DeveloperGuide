# [docs](index.md) » cp.ui.PopUpButton
---

Pop Up Button Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [PopUpButton](#popupbutton)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [menuUI](#menuui)
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doPress](#dopress)
 * [doSelectItem](#doselectitem)
 * [doSelectValue](#doselectvalue)
 * [getValue](#getvalue)
 * [loadLayout](#loadlayout)
 * [press](#press)
 * [saveLayout](#savelayout)
 * [selectItem](#selectitem)
 * [setValue](#setvalue)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [PopUpButton](#popupbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton(parent, uiFinder) -> cp.ui.PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new PopUpButton. |
| **Parameters**                                       | <ul><li>parent       - The parent table. Should have a <code>isShowing</code> property.</li><li>uiFinder      - The <code>function</code> or <code>cp.prop</code> that provides the current <code>hs._asm.axuielement</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>PopUpButton</code> instance.</li></ul> |

### Fields

#### [menuUI](#menuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton.menuUI <cp.prop: hs._asm.axuielement; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `AXMenu` for the PopUpMenu if it is currently visible. |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton.value <cp.prop: anything; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns or sets the current `PopUpButton` value. |

### Methods

#### [doPress](#dopress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:doPress() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that presses the `PopUpButton`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |

#### [doSelectItem](#doselectitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:doSelectItem(index) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will select an item on the `PopUpButton` by index. |
| **Parameters**                                       | <ul><li>index - The index number of the item you want to select.</li></ul> |
| **Returns**                                          | <ul><li>the <code>Statement</code>.</li></ul> |

#### [doSelectValue](#doselectvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:doSelectValue(value) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will select an item on the `PopUpButton` by value. |
| **Parameters**                                       | <ul><li>value - The value of the item to match.</li></ul> |
| **Returns**                                          | <ul><li>the <code>Statement</code>.</li></ul> |

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:getValue() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the `PopUpButton` value. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>PopUpButton</code> value as string, or <code>nil</code> if the value cannot be determined.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a `PopUpButton` layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the <code>PopUpButton</code> layout settings - created using <a href="#saveLayout">saveLayout</a>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:press() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Presses the `PopUpButton`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current `PopUpButton` layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current <code>PopUpButton</code> Layout.</li></ul> |

#### [selectItem](#selectitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:selectItem(index) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select an item on the `PopUpButton` by index. |
| **Parameters**                                       | <ul><li>index - The index of the item you want to select.</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:setValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the `PopUpButton` value. |
| **Parameters**                                       | <ul><li>value - The value you want to set the <code>PopUpButton</code> to.</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

