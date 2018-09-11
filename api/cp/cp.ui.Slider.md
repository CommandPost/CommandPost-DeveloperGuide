# [docs](index.md) » cp.ui.Slider
---

Slider Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Slider](#slider)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [maxValue](#maxvalue)
 * [minValue](#minvalue)
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [decrement](#decrement)
 * [getMaxValue](#getmaxvalue)
 * [getMinValue](#getminvalue)
 * [getValue](#getvalue)
 * [increment](#increment)
 * [loadLayout](#loadlayout)
 * [saveLayout](#savelayout)
 * [setValue](#setvalue)
 * [shiftValue](#shiftvalue)

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

#### [Slider](#slider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider(parent, uiFinder) -> cp.ui.Slider` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Slider |
| **Parameters**                                       | <ul><li>parent       - The parent object. Should have an <code>isShowing</code> property.</li><li>uiFinder     - The function which returns an <code>hs._asm.axuielement</code> for the slider, or <code>nil</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Slider</code> instance.</li></ul> |

### Fields

#### [maxValue](#maxvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider.maxValue <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets the maximum value of the slider. |

#### [minValue](#minvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider.minValue <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets the minimum value of the slider. |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider.value <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Sets or gets the value of the slider. |

### Methods

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

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a Slider layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the Slider layout settings - created using [saveLayout](#saveLayout].</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

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

