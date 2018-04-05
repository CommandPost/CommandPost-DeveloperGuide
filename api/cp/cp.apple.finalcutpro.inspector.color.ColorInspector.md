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
 * [isSupported](#issupported)
 * [topBarUI](#topbarui)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activateCorrection](#activatecorrection)
 * [app](#app)
 * [colorBoard](#colorboard)
 * [colorCurves](#colorcurves)
 * [colorWheels](#colorwheels)
 * [corrections](#corrections)
 * [hide](#hide)
 * [hueSaturationCurves](#huesaturationcurves)
 * [isShowing](#isshowing)
 * [new](#new)
 * [parent](#parent)
 * [show](#show)

## API Documentation

### Constants

#### [CORRECTION_TYPES](#correction_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.CORRECTION_TYPES` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of Correction Types                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the specified element is the Color Inspector element.                                                                                         |
| **Parameters**                                       | <ul><li>* element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the element is the Color Inspector.</li></ul>          |

### Fields

#### [correctorUI](#correctorui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.correctorUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object representing the currently-selected corrector panel.                                                                                         |

#### [isSupported](#issupported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.isSupported <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the Color Inspector supported in the installed version of Final Cut Pro?                                                                                         |

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
| **Parameters**                                       | <ul><li>correctionType   - The string for the type of correction (in English). E.g. "Color Wheels", "Color Board", etc.</li><li>number           - The correction number for that type. Defaults to `1`.</li></ul> |
| **Returns**                                          | <ul><li>ColorInspector object</li></ul>          |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul>          |

#### [colorBoard](#colorboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:colorBoard() -> ColorBoard` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorBoard object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A new ColorBoard object</li></ul>          |

#### [colorCurves](#colorcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:colorCurves() -> ColorCurves` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorCurves object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A new ColorCurves object</li></ul>          |

#### [colorWheels](#colorwheels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:colorWheels() -> ColorWheels` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorWheels object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A new ColorWheels object</li></ul>          |

#### [corrections](#corrections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:corrections() -> CorrectionsBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `CorrectionsBar` instance representing the available corrections,                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `CorrectionsBar` instance.</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:hide() -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Color Inspector                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorInspector object</li></ul>          |

#### [hueSaturationCurves](#huesaturationcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:hueSaturationCurves() -> HueSaturationCurves` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the HueSaturationCurves object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A new HueSaturationCurves object</li></ul>          |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:isShowing([correctionType]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the Color Inspector is visible                                                                                         |
| **Parameters**                                       | <ul><li>[correctionType] - A string containing the name of the Correction Type (see cp.apple.finalcutpro.inspector.color.ColorInspector.CORRECTION_TYPES).</li></ul> |
| **Returns**                                          | <ul><li>`true` if the Color Inspector is showing, otherwise `false`</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.new(parent) -> ColorInspector object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new ColorInspector object                                                                                         |
| **Parameters**                                       | <ul><li>`parent`     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A ColorInspector object</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ColorInspector's parent table.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Color Inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorInspector object</li></ul>          |

