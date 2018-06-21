# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorWheels
---

Color Wheels Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contentUI](#contentui)
 * [hue](#hue)
 * [isShowing](#isshowing)
 * [maxValue](#maxvalue)
 * [minValue](#minvalue)
 * [mix](#mix)
 * [temperature](#temperature)
 * [tint](#tint)
 * [UI](#ui)
 * [value](#value)
 * [viewingAllWheels](#viewingallwheels)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [highlights](#highlights)
 * [hueRow](#huerow)
 * [hueTextField](#huetextfield)
 * [master](#master)
 * [midtones](#midtones)
 * [mixRow](#mixrow)
 * [mixSlider](#mixslider)
 * [parent](#parent)
 * [shadows](#shadows)
 * [show](#show)
 * [temperatureRow](#temperaturerow)
 * [temperatureSlider](#temperatureslider)
 * [tintRow](#tintrow)
 * [tintSlider](#tintslider)
 * [viewMode](#viewmode)
 * [wheelType](#wheeltype)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the specified element is the Color Wheels element.                                                                                         |
| **Parameters**                                       | * element	- The element to check                                       |
| **Returns**                                          | * `true` if the element is the Color Wheels.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.new(parent) -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new ColorWheels object                                                                                         |
| **Parameters**                                       |  * `parent`     - The parent                                       |
| **Returns**                                          |  * A new `ColorInspector` object                                                |

### Fields

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` representing the content element of the ColorWheels corrector.                                                                                         |

#### [hue](#hue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.hue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The hue for the corrector. A number from `0` to `360`.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the Color Wheels Corrector currently showing?                                                                                         |

#### [maxValue](#maxvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.maxValue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The maximum value of the indicator as a number.                                                                                         |

#### [minValue](#minvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.minValue <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The minimum value of the indicator as a number.                                                                                         |

#### [mix](#mix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.mix <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The mix amount for this corrector. A number ranging from `0` to `1`.                                                                                         |

#### [temperature](#temperature)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.temperature <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The color temperature for this corrector. A number from 2500 to 10000.                                                                                         |

#### [tint](#tint)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.tint <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The tint for the corrector. A number from `-50` to `50`.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` representing the ColorWheels corrector.                                                                                         |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.value <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The value of the value indicator as a number.                                                                                         |

#### [viewingAllWheels](#viewingallwheels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels.viewingAllWheels <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Reports and modifies whether the ColorWheels corrector is showing "All Wheels" (`true`) or "Single Wheels" (`false`).                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The application object as a table                                                |

#### [highlights](#highlights)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:highlights() -> ColorWheel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `ColorWheel` that allows control of the 'highlights' color settings.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `ColorWheel`.                                                |

#### [hueRow](#huerow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:hueRow() -> cp.ui.PropertyRow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `PropertyRow` that provides access to the 'Hue' parameter, and `axuielement`                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `PropertyRow`.                                                |

#### [hueTextField](#huetextfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:hueTextField() -> cp.ui.TextField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `TextField` that provides access to the 'Hue' slider.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Hue `Slider`.                                                |

#### [master](#master)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:master() -> ColorWheel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `ColorWheel` that allows control of the 'master' color settings.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `ColorWheel`.                                                |

#### [midtones](#midtones)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:midtones() -> ColorWheel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `ColorWheel` that allows control of the 'midtones' color settings.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `ColorWheel`.                                                |

#### [mixRow](#mixrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:mixRow() -> cp.ui.PropertyRow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `PropertyRow` that provides access to the 'Mix' parameter, and `axuielement`                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `PropertyRow`.                                                |

#### [mixSlider](#mixslider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:mixSlider() -> cp.ui.Slider` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `Slider` that provides access to the 'Mix' slider.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Mix `Slider`.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ColorWheels's parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [shadows](#shadows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:shadows() -> ColorWheel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `ColorWheel` that allows control of the 'shadows' color settings.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `ColorWheel`.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Color Board within the Color Inspector.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * ColorWheels object                                                |

#### [temperatureRow](#temperaturerow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:temperatureRow() -> cp.ui.PropertyRow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `PropertyRow` that provides access to the 'Temperatures' parameter, and `axuielement`                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `PropertyRow`.                                                |

#### [temperatureSlider](#temperatureslider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:temperatureSlider() -> cp.ui.Slider` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `Slider` that provides access to the 'Temperatures' slider.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Temperatures `Slider`.                                                |

#### [tintRow](#tintrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:tintRow() -> cp.ui.PropertyRow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `PropertyRow` that provides access to the 'Tint' parameter, and `axuielement`                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `PropertyRow`.                                                |

#### [tintSlider](#tintslider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:tintSlider() -> cp.ui.Slider` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `Slider` that provides access to the 'Tint' slider.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Tint `Slider`.                                                |

#### [viewMode](#viewmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:viewMode() -> MenuButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `MenuButton` for the View menu button.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `MenuButton` for the View mode.                                                |

#### [wheelType](#wheeltype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWheels:wheelType() -> RadioGroup` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `RadioGroup` that allows selection of the wheel type. Only available when                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `RadioGroup`.                                                |

