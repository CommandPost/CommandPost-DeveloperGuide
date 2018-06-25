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
local video = fcp:inspector():video()
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
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [parent](#parent)
 * [show](#show)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided element could be a VideoInspector. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector.new(parent) -> cp.apple.finalcutpro.video.VideoInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `VideoInspector` object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A <code>VideoInspector</code> object</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the VideoInspector's parent table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.video.VideoInspector:show() -> VideoInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Video Inspector |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>VideoInspector</li></ul> |

