# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorInspector
---

Color Inspector Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [CORRECTION_TYPES](#correction_types)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [correctorUI](#correctorui)
 * [isAdvanced](#isadvanced)
 * [isShowing](#isshowing)
 * [topBarUI](#topbarui)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activateCorrection](#activatecorrection)
 * [addCorrection](#addcorrection)
 * [app](#app)
 * [colorBoard](#colorboard)
 * [colorCurves](#colorcurves)
 * [colorWheels](#colorwheels)
 * [corrections](#corrections)
 * [hide](#hide)
 * [hueSaturationCurves](#huesaturationcurves)
 * [new](#new)
 * [parent](#parent)
 * [show](#show)

## API Documentation

### Constants

#### [CORRECTION_TYPES](#correction_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.CORRECTION_TYPES` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of Correction Types:                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the specified element is the Color Inspector element.                                                                                         |
| **Parameters**                                       | * element   - The element to check                                       |
| **Returns**                                          | * `true` if the element is the Color Inspector.                                                |

### Fields

#### [correctorUI](#correctorui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.correctorUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object representing the currently-selected corrector panel.                                                                                         |

#### [isAdvanced](#isadvanced)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.isAdvanced <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the Color Inspector the advanced version that was added in 10.4?                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.isShowing <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the Color Inspector is visible.                                                                                         |

#### [topBarUI](#topbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.topBarUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object representing the top bar.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Color Inspector. Prior to FCPX 10.4 this will be the Color Board.                                                                                         |

### Methods

#### [activateCorrection](#activatecorrection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:activateCorrection(correctionType[, number]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Activates the named correction type and number, if present. If no corrector with the type/number combination exists, a new one is added.                                                                                         |
| **Parameters**                                       |  * correctionType   - The string for the type of correction (in English). E.g. "Color Wheels", "Color Board", etc. * number           - The correction number for that type. Defaults to `1`.                                       |
| **Returns**                                          |  * ColorInspector object                                                |

#### [addCorrection](#addcorrection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:addCorrection(correctionType) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the named correction type.                                                                                         |
| **Parameters**                                       |  * correctionType   - The string for the type of correction (in English). E.g. "Color Wheels", "Color Board", etc.                                       |
| **Returns**                                          |  * ColorInspector object                                                |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The application object as a table                                                |

#### [colorBoard](#colorboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:colorBoard() -> ColorBoard` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorBoard object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A new ColorBoard object                                                |

#### [colorCurves](#colorcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:colorCurves() -> ColorCurves` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorCurves object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A new ColorCurves object                                                |

#### [colorWheels](#colorwheels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:colorWheels() -> ColorWheels` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorWheels object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A new ColorWheels object                                                |

#### [corrections](#corrections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:corrections() -> CorrectionsBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `CorrectionsBar` instance representing the available corrections,                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `CorrectionsBar` instance.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:hide() -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Color Inspector                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * ColorInspector object                                                |

#### [hueSaturationCurves](#huesaturationcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:hueSaturationCurves() -> HueSaturationCurves` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the HueSaturationCurves object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A new HueSaturationCurves object                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.new(parent) -> ColorInspector object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new ColorInspector object                                                                                         |
| **Parameters**                                       |  * `parent`     - The parent                                       |
| **Returns**                                          |  * A ColorInspector object                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ColorInspector's parent table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Color Inspector.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * ColorInspector object                                                |

