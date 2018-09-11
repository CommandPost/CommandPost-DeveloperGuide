# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorWell
---

Represents a single Color Well in the Color Wheels Inspector.

## API Overview
* Constants - Useful values which cannot be changed
 * [KEY_PRESS](#key_press)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [ColorWell](#colorwell)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [center](#center)
 * [colorOrientation](#colororientation)
 * [colorPosition](#colorposition)
 * [focused](#focused)
 * [puckPosition](#puckposition)
* Methods - API calls which can only be made on an object returned by a constructor
 * [nudge](#nudge)
 * [reset](#reset)
 * [select](#select)

## API Documentation

### Constants

#### [KEY_PRESS](#key_press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.KEY_PRESS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | This can be used with `nudge` to shift by the same distance |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the specified element is a Color Well. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is a Color Well.</li></ul> |

### Constructors

#### [ColorWell](#colorwell)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell(parent, uiFinder[, hueShift]) -> ColorWell` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ColorWell` instance, with the specified parent and finder function. |
| **Parameters**                                       | <ul><li>parent    - The parent object</li><li>uiFinder  - Returns the <code>axuielement</code> that represents the color well.</li><li>hueShift  - The amount to shift the hue.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>ColorWell</code> instance.</li></ul> |

### Fields

#### [center](#center)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.center <cp.prop: point; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The center point of the ColorWell. A table with `{x=..., y=...}`. |

#### [colorOrientation](#colororientation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.colorOrientation <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Provides the orientation of the color as a table containing an `up` and `right` value. |

#### [colorPosition](#colorposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.colorPosition <cp.prop: hs.geometry.point>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | X/Y screen position for the current color value of the Color Well. This ignores the bounds of the |

#### [focused](#focused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.focused <cp.pref: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets and sets whether the Color Well has focus. |

#### [puckPosition](#puckposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.puckPosition <cp.prop: hs.geometry.point>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Absolute X/Y screen position for the puck in the Color Well. Colours outside the bounds are clamped inside the color well. |

### Methods

#### [nudge](#nudge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:nudge(right, up) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that nudges the `colorPosition` by `right`/`up` values. |
| **Parameters**                                       | <ul><li><code>right</code> - The number of steps to shift right. May be negative to shift left.</li><li><code>up</code> - The number of pixels to shift down. May be negative to shift down.</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorWell</code> instance.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:reset() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resets the color wheel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorWell</code> instance.</li></ul> |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:select() -> cp.apple.finalcutpro.inspector.color.ColorWell` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects this color well. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorWell</code> instance.</li></ul> |

