# [docs](index.md) » cp.apple.finalcutpro.inspector.text.TextInspector
---

Text Inspector Module.

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
local text = fcp:inspector():text()
-- Menu Property:
text:compositing():blendMode():value("Subtract")
-- Slider Property:
text:compositing():opacity():value(50.0)
-- XY Property:
text:transform():position():x(-10.0)
-- CheckBox property:
text:stabilization():tripodMode():value(true)
```

You should also be able to show a specific property and it will be revealed:
```lua
text:stabilization():smoothing():show():value(1.5)
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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.text.TextInspector.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the provided element could be a TextInspector.                                                                                         |
| **Parameters**                                       |  * element   - The element to check                                       |
| **Returns**                                          |  * `true` if it matches, `false` if not.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.text.TextInspector.new(parent) -> cp.apple.finalcutpro.text.TextInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `TextInspector` object                                                                                         |
| **Parameters**                                       |  * `parent`		- The parent                                       |
| **Returns**                                          |  * A `TextInspector` object                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.text.TextInspector:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The application object as a table                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.text.TextInspector:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the TextInspector's parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.text.TextInspector:show() -> TextInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Text Inspector                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * TextInspector                                                |

