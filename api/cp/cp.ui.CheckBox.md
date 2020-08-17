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
 * [CheckBox](#checkbox)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [checked](#checked)
 * [title](#title)
* Methods - API calls which can only be made on an object returned by a constructor
 * [click](#click)
 * [doCheck](#docheck)
 * [doPress](#dopress)
 * [doUncheck](#douncheck)
 * [loadLayout](#loadlayout)
 * [press](#press)
 * [saveLayout](#savelayout)
 * [toggle](#toggle)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided `hs._asm.axuielement` is a CheckBox. |
| **Parameters**                                       | <ul><li>element      - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it's a match, or <code>false</code> if not.</li></ul> |

### Constructors

#### [CheckBox](#checkbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox(parent, uiFinder) -> cp.ui.CheckBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new CheckBox. |
| **Parameters**                                       | <ul><li>parent       - The parent object.</li><li>uiFinder     - A function which will return the <code>hs._asm.axuielement</code> when available.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>CheckBox</code>.</li></ul> |

### Fields

#### [checked](#checked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox.checked <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the checkbox is currently checked. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox.title <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The button title, if available. |

### Methods

#### [click](#click)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:click() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Performs a single mouse click on the checkbox. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>CheckBox</code> instance.</li></ul> |

#### [doCheck](#docheck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:doCheck() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will ensure the `CheckBox` is checked. |

#### [doPress](#dopress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:doPress() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will press the button when executed, if available at the time. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> which will press the button when executed.</li></ul> |

#### [doUncheck](#douncheck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:doUncheck() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will ensure the `CheckBox` is unchecked. |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:loadLayout(layout) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Applies the settings in the provided layout table. |
| **Parameters**                                       | <ul><li>layout       - The table containing layout settings. Usually created by the <code>saveLayout</code> method.</li></ul> |
| **Returns**                                          | <ul><li>nil</li></ul> |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:press() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to press the button. May fail if the `UI` is not available. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <p>The <code>CheckBox</code> instance.</p> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table containing the layout settings for the checkbox. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A settings table.</li></ul> |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.CheckBox:toggle() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Toggles the `checked` status of the button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>CheckBox</code> instance.</li></ul> |

