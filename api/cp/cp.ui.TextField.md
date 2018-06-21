# [docs](index.md) » cp.ui.TextField
---

Text Field Module.

## API Overview
* Variables - Configurable values
 * [isShowing](#isshowing)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [clear](#clear)
 * [getValue](#getvalue)
 * [isEnabled](#isenabled)
 * [loadLayout](#loadlayout)
 * [new](#new)
 * [parent](#parent)
 * [saveLayout](#savelayout)
 * [setValue](#setvalue)
 * [snapshot](#snapshot)
 * [UI](#ui)

## API Documentation

### Variables

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField.isShowing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is the Text Field showing?                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul>            |

### Fields

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField.value <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The current value of the text field.                                                                                         |

### Methods

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:clear() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Clears the value of a Text Field.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>Self</li></ul>            |

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:getValue() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the value of the Text Field.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The value of the Text Field as a string.</li></ul>            |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Text Field enabled?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if enabled, otherwise <code>false</code>.</li></ul>            |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Text Field layout.                                                                                         |
| **Parameters**                                       | <ul><li>layout - A table containing the Text Field layout settings - created using <code>cp.ui.TextField:saveLayout()</code>.</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField.new(parent, finderFn[, convertFn]) -> TextField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new TextField. They have a parent and a finder function.                                                                                         |
| **Parameters**                                       | <ul><li>parent   - The parent object.</li></ul><ul><li>finderFn - The function will return the <code>axuielement</code> for the TextField.</li></ul><ul><li>convertFn    - (optional) If provided, will be passed the <code>string</code> value when returning.</li></ul>   |
| **Returns**                                          | <ul><li>The new <code>TextField</code>.</li></ul>            |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The parent object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The parent object.</li></ul>            |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Text Field layout to a table.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A table containing the current Text Field Layout.</li></ul>            |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:setValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the value of the Text Field.                                                                                         |
| **Parameters**                                       | <ul><li>value - The value you want to set the Text Field to as a string.</li></ul>   |
| **Returns**                                          | <ul><li>Self</li></ul>            |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>path     - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li></ul>   |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:UI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the `TextField`, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |

