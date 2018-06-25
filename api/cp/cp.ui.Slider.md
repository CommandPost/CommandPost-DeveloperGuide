# [docs](index.md) » cp.ui.Slider
---

Slider Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [decrement](#decrement)
 * [getMaxValue](#getmaxvalue)
 * [getMinValue](#getminvalue)
 * [getValue](#getvalue)
 * [increment](#increment)
 * [isEnabled](#isenabled)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [saveLayout](#savelayout)
 * [setValue](#setvalue)
 * [shiftValue](#shiftvalue)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided `hs._asm.axuielement` is a Slider. |
| **Parameters**                                       | <ul><li>element      - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it's a match, or <code>false</code> if not.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider.new(parent, finderFn) -> cp.ui.Slider` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Slider |
| **Parameters**                                       | <ul><li>parent       - The parent object. Should have an <code>isShowing</code> property. * finderFn        - The function which returns an <code>hs._asm.axuielement</code> for the slider, or <code>nil</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Slider</code> instance.</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the app instance. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [decrement](#decrement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:decrement() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Decrements the slider by one step. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [getMaxValue](#getmaxvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:getMaxValue() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the maximum value of the slider. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The value as a number.</li></ul> |

#### [getMinValue](#getminvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:getMinValue() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the minimum value of the slider. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The value as a number.</li></ul> |

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:getValue() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the value of the slider. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The value of the slider as a number.</li></ul> |

#### [increment](#increment)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:increment() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Increments the slider by one step. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Is the slider enabled? |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if enabled, otherwise <code>false</code>.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a Slider layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the Slider layout settings - created using <code>cp.ui.Slider:saveLayout()</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The parent object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object.</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current Slider layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current Slider Layout.</li></ul> |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:setValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the value of the slider. |
| **Parameters**                                       | <ul><li>value - The value you want to set the slider to as a number.</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [shiftValue](#shiftvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:shiftValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shifts the value of the slider. |
| **Parameters**                                       | <ul><li>value - The value you want to shift the slider by as a number.</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it. |
| **Parameters**                                       | <ul><li>path - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li></ul> |

