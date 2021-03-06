# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorInspector
---

Color Inspector Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [CORRECTION_TYPES](#correction_types)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [colorBoard](#colorboard)
 * [colorCurves](#colorcurves)
 * [colorWheels](#colorwheels)
 * [corrections](#corrections)
 * [correctorUI](#correctorui)
 * [hueSaturationCurves](#huesaturationcurves)
 * [topBarUI](#topbarui)
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activateCorrection](#activatecorrection)
 * [addCorrection](#addcorrection)
 * [ColorInspector](#colorinspector)
 * [doActivateCorrection](#doactivatecorrection)
 * [doAddCorrection](#doaddcorrection)
 * [doShow](#doshow)
 * [hide](#hide)
 * [show](#show)

## API Documentation

### Constants

#### [CORRECTION_TYPES](#correction_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.CORRECTION_TYPES` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of Correction Types: |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the specified element is the Color Inspector element. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is the Color Inspector.</li></ul> |

### Fields

#### [colorBoard](#colorboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.colorBoard <ColorBoard>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The ColorBoard object. |

#### [colorCurves](#colorcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.colorCurves <ColorCurves>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The ColorCurves object. |

#### [colorWheels](#colorwheels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.colorWheels <ColorWheels>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The ColorWheels object. |

#### [corrections](#corrections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.corrections <CorrectionsBar>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CorrectionsBar` instance representing the available corrections, |

#### [correctorUI](#correctorui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.correctorUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `hs._asm.axuielement` object representing the currently-selected corrector panel. |

#### [hueSaturationCurves](#huesaturationcurves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.hueSaturationCurves <HueSaturationCurves>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The HueSaturationCurves object. |

#### [topBarUI](#topbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.topBarUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `hs._asm.axuielement` object representing the top bar. |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector.value <cp.prop: cp.drawing.color>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets the Color Well Value as a `cp.drawing.color`. |

### Methods

#### [activateCorrection](#activatecorrection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:activateCorrection(correctionType[, number]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Activates the named correction type and number, if present. If no corrector with the type/number combination exists, a new one is added. |
| **Parameters**                                       | <ul><li>correctionType   - The string for the type of correction (in English). E.g. "Color Wheels", "Color Board", etc.</li><li>number           - The correction number for that type. Defaults to <code>1</code>.</li></ul> |
| **Returns**                                          | <ul><li>ColorInspector object</li></ul> |

#### [addCorrection](#addcorrection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:addCorrection(correctionType) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds the named correction type. |
| **Parameters**                                       | <ul><li>correctionType   - The string for the type of correction (in English). E.g. "Color Wheels", "Color Board", etc.</li></ul> |
| **Returns**                                          | <ul><li>ColorInspector object</li></ul> |

#### [ColorInspector](#colorinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector(parent) -> ColorInspector object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new ColorInspector object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A ColorInspector object</li></ul> |

#### [doActivateCorrection](#doactivatecorrection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:doActivateCorrection(correctionType[, number]) -> cp.rx.go.Statement<boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that activates the named correction type and number, if present. |
| **Parameters**                                       | <ul><li>correctionType   - The string for the type of correction (in English). E.g. "Color Wheels", "Color Board", etc.</li><li>number           - The correction number for that type. Defaults to <code>1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, which sends a single <code>true</code> value if successful, or sends an error if not.</li></ul> |

#### [doAddCorrection](#doaddcorrection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:doAddCorrection(correctionType) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that adds the named correction type. |
| **Parameters**                                       | <ul><li>correctionType   - The string for the type of correction (in English). E.g. "Color Wheels", "Color Board", etc.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> if successful, or sending an error if not.</li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that attempts to show the Color Inspector. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> if successful or sending an error if not.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:hide() -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the Color Inspector |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorInspector object</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorInspector:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Color Inspector. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorInspector object</li></ul> |

