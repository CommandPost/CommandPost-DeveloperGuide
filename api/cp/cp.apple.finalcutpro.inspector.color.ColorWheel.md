# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorWheel
---

Represents a single Color Well in the Color Wheels Inspector.

## API Overview
* Constants - Useful values which cannot be changed
 * [TYPE](#type)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [brightnessValue](#brightnessvalue)
 * [colorOrientation](#colororientation)
 * [colorPosition](#colorposition)
 * [colorValue](#colorvalue)
 * [focused](#focused)
 * [isShowing](#isshowing)
 * [puckPosition](#puckposition)
 * [saturationValue](#saturationvalue)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [brightness](#brightness)
 * [colorWell](#colorwell)
 * [nudgeColor](#nudgecolor)
 * [reset](#reset)
 * [resetButton](#resetbutton)
 * [saturation](#saturation)
 * [select](#select)

## API Documentation

### Constants

#### [TYPE](#type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.TYPE` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The possible types of ColorWheels: MASTER, SHADOWS, MIDTONES, HIGHLIGHTS. |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the specified element is a Color Well. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is a Color Well.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.new(parent, type) -> ColorWheel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ColorWheel` instance, with the specified parent and type. |
| **Parameters**                                       | <ul><li>parent    - The parent object.* type      - The type of color wheel. Must be one of the <code>ColorWheel.TYPE</code> values.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>ColorWheel</code> instance.</li></ul> |

### Fields

#### [brightnessValue](#brightnessvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.brightnessValue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current brightness value, as a number between -12 and 10. |

#### [colorOrientation](#colororientation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.colorOrientation <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Provides the orientation of the color as a table containing an `up` and `right` value. |

#### [colorPosition](#colorposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.colorPosition <cp.prop: point>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | X/Y screen position for the current color value of the Color Well. This ignores the bounds of the |

#### [colorValue](#colorvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.colorValue <cp.prop: hs.drawing.color>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current color value, as a `hs.drawing.color` table. |

#### [focused](#focused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.focused <cp.pref: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets and sets whether the Color Well has focus. |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the ColorWheel is showing on screen. |

#### [puckPosition](#puckposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.puckPosition <cp.prop: point>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Absolute X/Y screen position for the puck in the Color Well. Colours outside the bounds are clamped inside the color well. |

#### [saturationValue](#saturationvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.saturationValue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current saturation value, as a number between 0 and 10. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` for the ColorWheel. |

### Methods

#### [brightness](#brightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:brightness() -> ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the brightness `ValueIndicator` for this ColorWheel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The brightness <code>ValueIndicator</code> instance.</li></ul> |

#### [colorWell](#colorwell)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:colorWell() -> ColorWell` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `ColorWell` for this ColorWheel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorWell</code> instance.</li></ul> |

#### [nudgeColor](#nudgecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:nudgeColor(right, up) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Nudges the `colorPosition` by `right`/`up` values. Negative `right` values shift left, |
| **Parameters**                                       | <ul><li><code>right</code> - The number of steps to shift right. May be negative to shift left. * <code>up</code> - The number of pixels to shift down. May be negative to shift down.</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorWheel</code> instance.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:reset() -> ColorWheel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resets the color wheel values, if the ColorWheel is showing. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The ColorWheel instance.</li></ul> |

#### [resetButton](#resetbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:resetButton() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `Button` that triggers a value reset. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The reset <code>Button</code> instance.</li></ul> |

#### [saturation](#saturation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:saturation() -> ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the saturation `ValueIndicator` for this ColorWheel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The saturation <code>ValueIndicator</code> instance.</li></ul> |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheel:select() -> cp.apple.finalcutpro.inspector.color.ColorWheel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows and selects this color wheel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorWheel</code> instance.</li></ul> |

