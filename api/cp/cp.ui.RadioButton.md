# [docs](index.md) » cp.ui.RadioButton
---

Radio Button Module.

This represents an `hs._asm.axuielement` with a `AXRadioButton` role.
It allows checking and modifying the `checked` status like so:

```lua
myButton:checked() == true			-- happens to be checked already
myButton:checked(false) == false	-- update to unchecked.
myButton.checked:toggle() == true	-- toggled back to being checked.
```

You can also call instances of `RadioButton` as a function, which will return
the `checked` status:

```lua
myButton() == true			-- still true
myButton(false) == false	-- now false
```

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [checked](#checked)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doLayout](#dolayout)
 * [doPress](#dopress)
 * [doToggle](#dotoggle)
 * [loadLayout](#loadlayout)
 * [press](#press)
 * [RadioButton](#radiobutton)
 * [saveLayout](#savelayout)
 * [toggle](#toggle)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided `hs._asm.axuielement` is a RadioButton. |
| **Parameters**                                       | <ul><li>element       - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it's a match, or <code>false</code> if not.</li></ul> |

### Fields

#### [checked](#checked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton.checked <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the checkbox is currently checked. |

### Methods

#### [doLayout](#dolayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton:doLayout(layout) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will apply the layout provided, if possible. |
| **Parameters**                                       | <ul><li>layout - the <code>table</code> containing the layout configuration. Usually created via the [#saveLayout] method.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a>.</li></ul> |

#### [doPress](#dopress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton:doPress() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will press the button when executed, if available at the time. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> which will press the button when executed.</li></ul> |

#### [doToggle](#dotoggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton:doToggle() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will toggle the button value when executed, if available at the time. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> which will toggle the button when executed.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton:loadLayout(layout) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Processes the `layout` table to restore this to match the provided `layout`. |
| **Parameters**                                       | <ul><li>layout - the table of state values to restore to.</li></ul> |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton:press() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to press the button. May fail if the `UI` is not available. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <p>The <code>RadioButton</code> instance.</p> |

#### [RadioButton](#radiobutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton(axuielement, function) -> RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new RadioButton. |
| **Parameters**                                       | <ul><li>parent        - The parent object.</li><li>finderFn      - A function which will return the <code>hs._asm.axuielement</code> when available.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>RadioButton</code>.</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` with the button's current state. This can be passed to [#loadLayout] |
| **Returns**                                          | <ul><li>The table of the layout state.</li></ul> |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioButton:toggle() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Toggles the `checked` status of the button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>RadioButton</code> instance.</li></ul> |

