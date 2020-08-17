# [docs](index.md) » cp.ui.ComboBox
---

Combo Box Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Methods - API calls which can only be made on an object returned by a constructor
 * [ComboBox](#combobox)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ComboBox.matches(element[, subrole]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li><li>subrole - (optional) If provided, the field must have the specified subrole.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Methods

#### [ComboBox](#combobox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ComboBox(parent, uiFinder, listAdaptorFn, [, getConvertFn[, setConvertFn]]) -> ComboBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new ComboBox. They have a parent and a finder function. |
| **Parameters**                                       | <ul><li>parent   - The parent object.</li><li>uiFinder - The function will return the <code>axuielement</code> for the ComboBox.</li><li>listAdaptorFn    - A function that will recieve a <code>List</code> and <code>AXUIElement</code> value and return an <code>Element</code></li><li>getConvertFn    - (optional) If provided, will be passed the <code>string</code> value when returning.</li><li>setConvertFn    - (optional) If provided, will be passed the <code>number</code> value when setting.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>ComboBox</code>.</li></ul> |

