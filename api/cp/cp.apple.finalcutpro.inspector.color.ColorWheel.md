# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorWheel
---

Represents a single Color Well in the Color Wheels Inspector.

## API Overview
* Constants - Useful values which cannot be changed
 * [TYPE](#type)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [brightnessValue](#brightnessvalue)
 * [colorPosition](#colorposition)
 * [colorScreenPosition](#colorscreenposition)
 * [colorValue](#colorvalue)
 * [puckPosition](#puckposition)
 * [puckScreenPosition](#puckscreenposition)
 * [saturationValue](#saturationvalue)
* Methods - API calls which can only be made on an object returned by a constructor
 * [brightness](#brightness)
 * [colorWell](#colorwell)
 * [new](#new)
 * [nudgeColor](#nudgecolor)
 * [reset](#reset)
 * [resetButton](#resetbutton)
 * [saturation](#saturation)

## API Documentation

### Constants

#### [TYPE](#type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.TYPE` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The possible types of ColorWheels: MASTER, SHADOWS, MIDTONES, HIGHLIGHTS.                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the specified element is a Color Well.                                                                                         |
| **Parameters**                                       | <ul><li>* element	- The element to check</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the element is a Color Well.</li></ul>          |

### Fields

#### [brightnessValue](#brightnessvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.brightnessValue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The current brightness value, as a number between -12 and 10.                                                                                         |

#### [colorPosition](#colorposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.colorPosition <cp.prop: point>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Relative X/Y position for the current color value of the Color Well. This will be a `point` table,                                                                                         |

#### [colorScreenPosition](#colorscreenposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.colorScreenPosition <cp.prop: point>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | X/Y screen position for the current color value of the Color Well. This ignores the bounds of the                                                                                         |

#### [colorValue](#colorvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.colorValue <cp.prop: hs.drawing.color>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The current color value, as a `hs.drawing.color` table.                                                                                         |

#### [puckPosition](#puckposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.puckPosition <cp.prop: point>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | X/Y position for the puck in the Color Well. Colours outside the bounds are clamped inside the color well.                                                                                         |

#### [puckScreenPosition](#puckscreenposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.puckScreenPosition <cp.prop: point>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Absolute X/Y screen position for the puck in the Color Well. Colours outside the bounds are clamped inside the color well.                                                                                         |

#### [saturationValue](#saturationvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.saturationValue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The current saturation value, as a number between 0 and 10.                                                                                         |

### Methods

#### [brightness](#brightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:brightness() -> ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the brightness `ValueIndicator` for this ColorWheel.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The brightness `ValueIndicator` instance.</li></ul>          |

#### [colorWell](#colorwell)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:colorWell() -> ColorWell` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `ColorWell` for this ColorWheel.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `ColorWell` instance.</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:new(parent, type) -> ColorWheel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new `ColorWheel` instance, with the specified parent and type.                                                                                         |
| **Parameters**                                       | <ul><li>* parent	- The parent object.</li><li>* type		- The type of color wheel. Must be one of the `ColorWheel.TYPE` values.</li></ul> |
| **Returns**                                          | <ul><li>* A new `ColorWheel` instance.</li></ul>          |

#### [nudgeColor](#nudgecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:nudgeColor(x, y) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Nudges the `colorPosition` by `x`/`y` values. Positive `x` values shift right,                                                                                         |
| **Parameters**                                       | <ul><li>* x		- The number of pixels to shift horizontally.</li><li>* y		- The number of pixels to shift vertically.</li></ul> |
| **Returns**                                          | <ul><li>* The `ColorWheel` instance.</li></ul>          |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:reset() -> ColorWheel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resets the color wheel values, if the ColorWheel is showing.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The ColorWheel instance.</li></ul>          |

#### [resetButton](#resetbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:resetButton() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `Button` that triggers a value reset.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The reset `Button` instance.</li></ul>          |

#### [saturation](#saturation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:saturation() -> ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the saturation `ValueIndicator` for this ColorWheel.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The saturation `ValueIndicator` instance.</li></ul>          |

