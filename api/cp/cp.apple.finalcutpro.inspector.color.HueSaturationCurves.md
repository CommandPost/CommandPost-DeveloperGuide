# [docs](index.md) » cp.apple.finalcutpro.inspector.color.HueSaturationCurves
---

Color Curves Module.

Requires Final Cut Pro 10.4 or later.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [HueSaturationCurves](#huesaturationcurves)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [colorVsSat](#colorvssat)
 * [contentUI](#contentui)
 * [hueVsHue](#huevshue)
 * [hueVsLuma](#huevsluma)
 * [hueVsSat](#huevssat)
 * [lumaVsSat](#lumavssat)
 * [mix](#mix)
 * [mixRow](#mixrow)
 * [mixSlider](#mixslider)
 * [satVsSat](#satvssat)
 * [viewingAllCurves](#viewingallcurves)
 * [viewModeButton](#viewmodebutton)
 * [wheelType](#wheeltype)
* Methods - API calls which can only be made on an object returned by a constructor
 * [show](#show)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the specified element is the Color Curves element. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is the Color Curves.</li></ul> |

### Constructors

#### [HueSaturationCurves](#huesaturationcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves(parent) -> HueSaturationCurves object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new HueSaturationCurves object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A ColorInspector object</li></ul> |

### Fields

#### [colorVsSat](#colorvssat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.colorVsSat <HueSaturationCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [HueSaturationCurve](cp.apple.finalcutpro.inspector.color.HueSaturationCurve.md) |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` representing the content element of the HueSaturationCurves corrector. |

#### [hueVsHue](#huevshue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.hueVsHue <HueSaturationCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [HueSaturationCurve](cp.apple.finalcutpro.inspector.color.HueSaturationCurve.md) |

#### [hueVsLuma](#huevsluma)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.hueVsLuma <HueSaturationCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [HueSaturationCurve](cp.apple.finalcutpro.inspector.color.HueSaturationCurve.md) |

#### [hueVsSat](#huevssat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.hueVsSat <HueSaturationCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [HueSaturationCurve](cp.apple.finalcutpro.inspector.color.HueSaturationCurve.md) |

#### [lumaVsSat](#lumavssat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.lumaVsSat <HueSaturationCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [HueSaturationCurve](cp.apple.finalcutpro.inspector.color.HueSaturationCurve.md) |

#### [mix](#mix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.mix <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The mix amount for this corrector. A number ranging from `0` to `1`. |

#### [mixRow](#mixrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.mixRow <cp.ui.PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `PropertyRow` that provides access to the 'Mix' parameter, and `axuielement` |

#### [mixSlider](#mixslider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.mixSlider <cp.ui.Slider>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `Slider` that provides access to the 'Mix' slider. |

#### [satVsSat](#satvssat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.satVsSat <HueSaturationCurve>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [HueSaturationCurve](cp.apple.finalcutpro.inspector.color.HueSaturationCurve.md) |

#### [viewingAllCurves](#viewingallcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.viewingAllCurves <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Reports and modifies whether the corrector is showing "All Curves" (`true`) or "Single Curves" (`false`). |

#### [viewModeButton](#viewmodebutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.viewModeButton <cp.ui.MenuButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [MenuButton](cp.ui.MenuButton.md) for the View Mode. |

#### [wheelType](#wheeltype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.wheelType <RadioGroup>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `RadioGroup` that allows selection of the curve type. Only available when |

### Methods

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's the Color Board within the Color Inspector. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>HueSaturationCurves object</li></ul> |

