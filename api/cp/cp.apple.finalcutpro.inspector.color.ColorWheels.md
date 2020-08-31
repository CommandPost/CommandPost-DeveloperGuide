# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorWheels
---

Color Wheels Module.

Extends [Element](cp.ui.Element.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [ColorWheels](#colorwheels)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contentUI](#contentui)
 * [highlights](#highlights)
 * [hue](#hue)
 * [hueRow](#huerow)
 * [hueSlider](#hueslider)
 * [hueTextField](#huetextfield)
 * [master](#master)
 * [maxValue](#maxvalue)
 * [midtones](#midtones)
 * [minValue](#minvalue)
 * [mix](#mix)
 * [mixRow](#mixrow)
 * [mixSlider](#mixslider)
 * [mixTextField](#mixtextfield)
 * [shadows](#shadows)
 * [temperature](#temperature)
 * [temperatureRow](#temperaturerow)
 * [temperatureSlider](#temperatureslider)
 * [temperatureTextField](#temperaturetextfield)
 * [tint](#tint)
 * [tintRow](#tintrow)
 * [tintSlider](#tintslider)
 * [tintTextField](#tinttextfield)
 * [value](#value)
 * [viewingAllWheels](#viewingallwheels)
 * [viewMode](#viewmode)
 * [wheelType](#wheeltype)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doShow](#doshow)
 * [show](#show)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the specified element is the Color Wheels element. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is the Color Wheels.</li></ul> |

### Constructors

#### [ColorWheels](#colorwheels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels(parent) -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new ColorWheels object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A new <code>ColorInspector</code> object</li></ul> |

### Fields

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` representing the content element of the ColorWheels corrector. |

#### [highlights](#highlights)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.highlights <ColorWheel>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `ColorWheel` that allows control of the 'highlights' color settings. |

#### [hue](#hue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.hue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The hue for the corrector. A number from `0` to `360`. |

#### [hueRow](#huerow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.hueRow <cp.ui.PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `PropertyRow` that provides access to the 'Hue' parameter, and `axuielement` |

#### [hueSlider](#hueslider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.hueSlider <cp.ui.Slider>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns a `Slider` that provides access to the 'Hue' slider. |

#### [hueTextField](#huetextfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.hueTextField <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `TextField` that provides access to the 'Hue' slider. |

#### [master](#master)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.master <ColorWheel>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `ColorWheel` that allows control of the 'master' color settings. |

#### [maxValue](#maxvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.maxValue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The maximum value of the indicator as a number. |

#### [midtones](#midtones)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.midtones <ColorWheel>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `ColorWheel` that allows control of the 'midtones' color settings. |

#### [minValue](#minvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.minValue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The minimum value of the indicator as a number. |

#### [mix](#mix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.mix <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The mix amount for this corrector. A number ranging from `0` to `1`. |

#### [mixRow](#mixrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.mixRow <cp.ui.PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `PropertyRow` that provides access to the 'Mix' parameter, and `axuielement` |

#### [mixSlider](#mixslider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.mixSlider <cp.ui.Slider>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `Slider` that provides access to the 'Mix' slider. |

#### [mixTextField](#mixtextfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.mixTextField <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `TextField` that provides access to the 'Mix' slider. |

#### [shadows](#shadows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.shadows <ColorWheel>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `ColorWheel` that allows control of the 'shadows' color settings. |

#### [temperature](#temperature)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.temperature <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The color temperature for this corrector. A number from 2500 to 10000. |

#### [temperatureRow](#temperaturerow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.temperatureRow <cp.ui.PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `PropertyRow` that provides access to the 'Temperatures' parameter, and `axuielement` |

#### [temperatureSlider](#temperatureslider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.temperatureSlider <cp.ui.Slider>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `Slider` that provides access to the 'Temperatures' slider. |

#### [temperatureTextField](#temperaturetextfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.temperatureTextField <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `TextField` that provides access to the 'Temperature' slider. |

#### [tint](#tint)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.tint <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The tint for the corrector. A number from `-50` to `50`. |

#### [tintRow](#tintrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.tintRow <cp.ui.PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `PropertyRow` that provides access to the 'Tint' parameter, and `axuielement` |

#### [tintSlider](#tintslider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.tintSlider <cp.ui.Slider>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns a `Slider` that provides access to the 'Tint' slider. |

#### [tintTextField](#tinttextfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.tintTextField <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `TextField` that provides access to the 'Tint' slider. |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.value <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The value of the value indicator as a number. |

#### [viewingAllWheels](#viewingallwheels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.viewingAllWheels <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Reports and modifies whether the ColorWheels corrector is showing "All Wheels" (`true`) or "Single Wheels" (`false`). |

#### [viewMode](#viewmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.viewMode <cp.ui.MenuButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [MenuButton](cp.ui.MenuButton.md) for the View Mode. |

#### [wheelType](#wheeltype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.wheelType <cp.ui.RadioGroup>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `RadioGroup` that allows selection of the wheel type. Only available when |

### Methods

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:doShow() -> cs.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that shows the Color Board within the Color Inspector. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> if successfully shown.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's the Color Board within the Color Inspector. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorWheels object</li></ul> |

