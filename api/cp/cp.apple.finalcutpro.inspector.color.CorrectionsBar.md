# [docs](index.md) » cp.apple.finalcutpro.inspector.color.CorrectionsBar
---

The Correction selection/management bar at the top of the ColorInspector

Requires Final Cut Pro 10.4 or later.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activate](#activate)
 * [add](#add)
 * [app](#app)
 * [findCorrectionLabel](#findcorrectionlabel)
 * [menuButton](#menubutton)
 * [parent](#parent)
 * [show](#show)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       | <ul><li>element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                          | <ul><li>`true` if matches otherwise `false`</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar.new(parent) -> CorrectionsBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new Media Import object.                                                                                         |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>A new CorrectionsBar object.</li></ul>          |

### Methods

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:activate(correctionType, number) -> cp.apple.finalcutpro.inspector.color.CorrectionsBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Activates a correction type.                                                                                         |
| **Parameters**                                       | <ul><li>`correctionType` - The correction type as string.</li><li>`number` - The number of the correction.</li></ul> |
| **Returns**                                          | <ul><li> `cp.apple.finalcutpro.inspector.color.CorrectionsBar` object.</li></ul>          |

#### [add](#add)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:add(correctionType) -> cp.apple.finalcutpro.inspector.color.CorrectionsBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specific correction type.                                                                                         |
| **Parameters**                                       | <ul><li>`correctionType` - The correction type as string.</li></ul> |
| **Returns**                                          | <ul><li> `cp.apple.finalcutpro.inspector.color.CorrectionsBar` object.</li></ul>          |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul>          |

#### [findCorrectionLabel](#findcorrectionlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:findCorrectionLabel(correctionType) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns Correction Label.                                                                                         |
| **Parameters**                                       | <ul><li>correctionType - The correction type as string.</li></ul> |
| **Returns**                                          | <ul><li>The correction label as string.</li></ul>          |

#### [menuButton](#menubutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:menuButton() -> MenuButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the menu button.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A `menuButton` object.</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Corrections Bar's parent table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attempts to show the bar.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `CorrectionsBar` instance.</li></ul>          |

