# [docs](index.md) » cp.ui.PopUpButton
---

Pop Up Button Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [getValue](#getvalue)
 * [isEnabled](#isenabled)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [press](#press)
 * [saveLayout](#savelayout)
 * [selectItem](#selectitem)
 * [setValue](#setvalue)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton.new(axuielement, function) -> cp.ui.PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new PopUpButton.                                                                                         |
| **Parameters**                                       |  * parent		- The parent table. Should have a `isShowing` property.                                       |
| **Returns**                                          |  * The new `PopUpButton` instance.                                                |

### Methods

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:getValue() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `PopUpButton` value.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `PopUpButton` value as string, or `nil` if the value cannot be determined.                                                |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the `PopUpButton` enabled?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if enabled otherwise `false`.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a `PopUpButton` layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the `PopUpButton` layout settings - created using `cp.ui.PopUpButton:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * parent                                                |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:press() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the `PopUpButton`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * self                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current `PopUpButton` layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current `PopUpButton` Layout.                                                |

#### [selectItem](#selectitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:selectItem(index) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select an item on the `PopUpButton` by index.                                                                                         |
| **Parameters**                                       |  * index - The index of the item you want to select.                                       |
| **Returns**                                          |  * self                                                |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:setValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the `PopUpButton` value.                                                                                         |
| **Parameters**                                       |  * value - The value you want to set the `PopUpButton` to.                                       |
| **Returns**                                          |  * self                                                |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       |  * path		- (optional) The path to save the file. Should include the extension (should be `.png`).                                       |

