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
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the provided `hs._asm.axuielement` is a Slider.                                                                                         |
| **Parameters**                                       |  * element		- The `axuielement` to check.                                       |
| **Returns**                                          |  * `true` if it's a match, or `false` if not.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider.new(parent, finderFn) -> cp.ui.Slider` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Slider                                                                                         |
| **Parameters**                                       |  * parent		- The parent object. Should have an `isShowing` property. * finderFn		- The function which returns an `hs._asm.axuielement` for the slider, or `nil`.                                       |
| **Returns**                                          |  * A new `Slider` instance.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [decrement](#decrement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:decrement() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Decrements the slider by one step.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Self                                                |

#### [getMaxValue](#getmaxvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:getMaxValue() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the maximum value of the slider.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The value as a number.                                                |

#### [getMinValue](#getminvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:getMinValue() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the minimum value of the slider.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The value as a number.                                                |

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:getValue() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the value of the slider.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The value of the slider as a number.                                                |

#### [increment](#increment)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:increment() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Increments the slider by one step.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Self                                                |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the slider enabled?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if enabled, otherwise `false`.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Slider layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the Slider layout settings - created using `cp.ui.Slider:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object.                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Slider layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current Slider Layout.                                                |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:setValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the value of the slider.                                                                                         |
| **Parameters**                                       |  * value - The value you want to set the slider to as a number.                                       |
| **Returns**                                          |  * Self                                                |

#### [shiftValue](#shiftvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:shiftValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shifts the value of the slider.                                                                                         |
| **Parameters**                                       |  * value - The value you want to shift the slider by as a number.                                       |
| **Returns**                                          |  * Self                                                |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       |  * path	- (optional) The path to save the file. Should include the extension (should be `.png`).                                       |

