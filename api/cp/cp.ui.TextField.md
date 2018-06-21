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
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

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
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Self                                                |

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:getValue() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the value of the Text Field.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The value of the Text Field as a string.                                                |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Text Field enabled?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if enabled, otherwise `false`.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Text Field layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the Text Field layout settings - created using `cp.ui.TextField:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField.new(parent, finderFn[, convertFn]) -> TextField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new TextField. They have a parent and a finder function.                                                                                         |
| **Parameters**                                       |  * parent	- The parent object. * finderFn	- The function will return the `axuielement` for the TextField. * convertFn	- (optional) If provided, will be passed the `string` value when returning.                                       |
| **Returns**                                          |  * The new `TextField`.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object.                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Text Field layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current Text Field Layout.                                                |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:setValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the value of the Text Field.                                                                                         |
| **Parameters**                                       |  * value - The value you want to set the Text Field to as a string.                                       |
| **Returns**                                          |  * Self                                                |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       |  * path		- (optional) The path to save the file. Should include the extension (should be `.png`).                                       |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:UI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the `TextField`, or `nil` if not available.                                                                                         |
| **Parameters**                                       |  * None                                       |

