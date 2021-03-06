# [docs](index.md) » cp.apple.finalcutpro.inspector.video.VideoInspector
---

Video Inspector Module.

Section Rows (`compositing`, `transform`, etc.) have the following properties:
* enabled   - (cp.ui.CheckBox) Indicates if the section is enabled.
* toggle    - (cp.ui.Button) Will toggle the Hide/Show button.
* reset     - (cp.ui.Button) Will reset the contents of the section.
* expanded  - (cp.prop <boolean>) Get/sets whether the section is expanded.

Property Rows depend on the type of property:

Menu Property:
* value     - (cp.ui.PopUpButton) The current value of the property.

Slider Property:
* value     - (cp.ui.Slider) The current value of the property.

XY Property:
* x         - (cp.ui.TextField) The current 'X' value.
* y         - (cp.ui.TextField) The current 'Y' value.

CheckBox Property:
* value     - (cp.ui.CheckBox) The currently value.

For example:
```lua
local video = fcp.inspector.video
-- Menu Property:
video:compositing():blendMode():value("Subtract")
-- Slider Property:
video:compositing():opacity():value(50.0)
-- XY Property:
video:transform():position():x(-10.0)
-- CheckBox property:
video:stabilization():tripodMode():value(true)
```

You should also be able to show a specific property and it will be revealed:
```lua
video:stabilization():smoothing():show():value(1.5)
```

## API Overview
* Constants - Useful values which cannot be changed
 * [BLEND_MODES](#blend_modes)
 * [CROP_TYPES](#crop_types)
 * [ROLLING_SHUTTER_AMOUNTS](#rolling_shutter_amounts)
 * [SPATIAL_CONFORM_TYPES](#spatial_conform_types)
 * [STABILIZATION_METHODS](#stabilization_methods)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
 * [selectedEffectCheckBox](#selectedeffectcheckbox)
* Constructors - API calls which return an object, typically one that offers API methods
 * [VideoInspector](#videoinspector)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contentUI](#contentui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [effectCheckBoxes](#effectcheckboxes)

## API Documentation

### Constants

#### [BLEND_MODES](#blend_modes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector.BLEND_MODES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Blend Modes |

#### [CROP_TYPES](#crop_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector.CROP_TYPES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Crop Types |

#### [ROLLING_SHUTTER_AMOUNTS](#rolling_shutter_amounts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector.ROLLING_SHUTTER_AMOUNTS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Rolling Shutter Amounts |

#### [SPATIAL_CONFORM_TYPES](#spatial_conform_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector.SPATIAL_CONFORM_TYPES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Spatial Conform Types |

#### [STABILIZATION_METHODS](#stabilization_methods)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector.STABILIZATION_METHODS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Stabilisation Methods |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided element could be a VideoInspector. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul> |

#### [selectedEffectCheckBox](#selectedeffectcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector:selectedEffectCheckBox() -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the selected effect checkbox object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A axuielement object.</li></ul> |

### Constructors

#### [VideoInspector](#videoinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector(parent) -> cp.apple.finalcutpro.inspector.video.VideoInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `VideoInspector` object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A <code>VideoInspector</code> object</li></ul> |

### Fields

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` containing the properties rows, if available. |

### Methods

#### [effectCheckBoxes](#effectcheckboxes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector:effectCheckBoxes() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets a table containing all of the effect checkboxes. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table.</li></ul> |

