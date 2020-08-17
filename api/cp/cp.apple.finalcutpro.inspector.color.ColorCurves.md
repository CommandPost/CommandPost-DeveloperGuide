# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorCurves
---

Color Curves Module.

Requires Final Cut Pro 10.4 or later.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [ColorCurves](#colorcurves)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [blue](#blue)
 * [contentUI](#contentui)
 * [green](#green)
 * [luma](#luma)
 * [mix](#mix)
 * [mixRow](#mixrow)
 * [mixSlider](#mixslider)
 * [preserveLuma](#preserveluma)
 * [preserveLumaRow](#preservelumarow)
 * [red](#red)
 * [viewingAllCurves](#viewingallcurves)
 * [viewModeButton](#viewmodebutton)
 * [wheelType](#wheeltype)
* Methods - API calls which can only be made on an object returned by a constructor
 * [show](#show)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the specified element is the Color Curves element. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is the Color Curves.</li></ul> |

### Constructors

#### [ColorCurves](#colorcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves(parent) -> ColorCurves object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new ColorCurves object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A ColorInspector object</li></ul> |

### Fields

#### [blue](#blue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.blue <ColorCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [ColorCurve](cp.apple.finalcutpro.inspector.color.ColorCurve.md) |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` representing the content element of the ColorCurves corrector. |

#### [green](#green)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.green <ColorCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [ColorCurve](cp.apple.finalcutpro.inspector.color.ColorCurve.md) |

#### [luma](#luma)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.luma <ColorCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [ColorCurve](cp.apple.finalcutpro.inspector.color.ColorCurve.md) |

#### [mix](#mix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.mix <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The mix amount for this corrector. A number ranging from `0` to `1`. |

#### [mixRow](#mixrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.mixRow <cp.ui.PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `PropertyRow` that provides access to the 'Mix' parameter, and `axuielement` |

#### [mixSlider](#mixslider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.mixSlider <cp.ui.Slider>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `Slider` that provides access to the 'Mix' slider. |

#### [preserveLuma](#preserveluma)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.preserveLuma <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns a [CheckBox](cp.ui.CheckBox.md) that provides access to the 'Preserve Luma' slider. |

#### [preserveLumaRow](#preservelumarow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.preserveLumaRow <cp.ui.PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `PropertyRow` that provides access to the 'Preserve Luma' parameter, and `axuielement` |

#### [red](#red)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.red <ColorCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [ColorCurve](cp.apple.finalcutpro.inspector.color.ColorCurve.md) |

#### [viewingAllCurves](#viewingallcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.viewingAllCurves <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Reports and modifies whether the corrector is showing "All Curves" (`true`) or "Single Curves" (`false`). |

#### [viewModeButton](#viewmodebutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.viewModeButton <cp.ui.MenuButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the [MenuButton](cp.ui.MenuButton.md) for the View Mode. |

#### [wheelType](#wheeltype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.wheelType <RadioGroup>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `RadioGroup` that allows selection of the curve type. Only available when |

### Methods

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's the Color Board within the Color Inspector. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorCurves object</li></ul> |

