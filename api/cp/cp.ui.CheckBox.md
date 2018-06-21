# [docs](index.md) » cp.ui.CheckBox
---

Check Box UI Module.

This represents an `hs._asm.axuielement` with a `AXCheckBox` role.
It allows checking and modifying the `checked` status like so:

```lua
myButton:checked() == true			-- happens to be checked already
myButton:checked(false) == false	-- update to unchecked.
myButton.checked:toggle() == true	-- toggled back to being checked.
```

You can also call instances of `CheckBox` as a function, which will return
the `checked` status:

```lua
myButton() == true			-- still true
myButton(false) == false	-- now false
```

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [isEnabled](#isenabled)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [press](#press)
 * [saveLayout](#savelayout)
 * [snapshot](#snapshot)
 * [toggle](#toggle)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the provided `hs._asm.axuielement` is a CheckBox.                                                                                         |
| **Parameters**                                       |  * element		- The `axuielement` to check.                                       |
| **Returns**                                          |  * `true` if it's a match, or `false` if not.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox.new(parent, finderFn) -> cp.ui.CheckBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new CheckBox.                                                                                         |
| **Parameters**                                       |  * parent		- The parent object. * finderFn		- A function which will return the `hs._asm.axuielement` when available.                                       |
| **Returns**                                          |  * The new `CheckBox`.                                                |

### Methods

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if the radio button exists and is enabled.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          | `true` or `false`.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:loadLayout(layout) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies the settings in the provided layout table.                                                                                         |
| **Parameters**                                       |  * layout		- The table containing layout settings. Usually created by the `saveLayout` method.                                       |
| **Returns**                                          |  * nil                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object.                                                |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:press() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attempts to press the button. May fail if the `UI` is not available.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          | The `CheckBox` instance.                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table containing the layout settings for the checkbox.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A settings table.                                                |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       |  * path		- (optional) The path to save the file. Should include the extension (should be `.png`).                                       |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:toggle() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggles the `checked` status of the button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `CheckBox` instance.                                                |

