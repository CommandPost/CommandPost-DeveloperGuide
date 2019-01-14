# [docs](index.md) » cp.ui.TextField
---

Text Field Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [clear](#clear)
 * [doConfirm](#doconfirm)
 * [doFocus](#dofocus)
 * [forceFocus](#forcefocus)
 * [getValue](#getvalue)
 * [loadLayout](#loadlayout)
 * [saveLayout](#savelayout)
 * [setValue](#setvalue)
 * [TextField](#textfield)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField.matches(element[, subrole]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li><li>subrole - (optional) If provided, the field must have the specified subrole.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Fields

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField.value <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current value of the text field. |

### Methods

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:clear() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Clears the value of a Text Field. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [doConfirm](#doconfirm)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:doConfirm() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will confirm the current text value. |

#### [doFocus](#dofocus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:doFocus() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to focus on the current `TextField`. |

#### [forceFocus](#forcefocus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:forceFocus()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Configures the TextField to force a focus on the field before editing. |

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:getValue() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the value of the Text Field. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The value of the Text Field as a string.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a Text Field layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the Text Field layout settings - created using <code>cp.ui.TextField:saveLayout()</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current Text Field layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current Text Field Layout.</li></ul> |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:setValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the value of the Text Field. |
| **Parameters**                                       | <ul><li>value - The value you want to set the Text Field to as a string.</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [TextField](#textfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField(parent, uiFinder[, convertFn]) -> TextField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new TextField. They have a parent and a finder function. |
| **Parameters**                                       | <ul><li>parent   - The parent object.</li><li>uiFinder - The function will return the <code>axuielement</code> for the TextField.</li><li>convertFn    - (optional) If provided, will be passed the <code>string</code> value when returning.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>TextField</code>.</li></ul> |

