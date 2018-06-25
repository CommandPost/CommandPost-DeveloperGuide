# [docs](index.md) » cp.apple.finalcutpro.inspector.share.ShareInspector
---

Share Inspector Module.

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
local share = fcp:inspector():share()
-- Menu Property:
share:compositing():blendMode():value("Subtract")
-- Slider Property:
share:compositing():opacity():value(50.0)
-- XY Property:
share:transform():position():x(-10.0)
-- CheckBox property:
share:stabilization():tripodMode():value(true)
```

You should also be able to show a specific property and it will be revealed:
```lua
share:stabilization():smoothing():show():value(1.5)
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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.share.ShareInspector.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided element could be a ShareInspector. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches, <code>false</code> if not.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.share.ShareInspector.new(parent) -> cp.apple.finalcutpro.share.ShareInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ShareInspector` object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A <code>ShareInspector</code> object</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.share.ShareInspector:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.share.ShareInspector:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the ShareInspector's parent table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.share.ShareInspector:show() -> ShareInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Share Inspector |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ShareInspector</li></ul> |

