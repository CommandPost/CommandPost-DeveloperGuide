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
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar.new(parent) -> CorrectionsBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new Media Import object.                                                                                         |
| **Parameters**                                       |  * parent - The parent object.                                       |
| **Returns**                                          |  * A new CorrectionsBar object.                                                |

### Methods

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:activate(correctionType, number) -> cp.apple.finalcutpro.inspector.color.CorrectionsBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Activates a correction type.                                                                                         |
| **Parameters**                                       |  * `correctionType` - The correction type as string. * `number` - The number of the correction.                                       |
| **Returns**                                          |  *  `cp.apple.finalcutpro.inspector.color.CorrectionsBar` object.                                                |

#### [add](#add)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:add(correctionType) -> cp.apple.finalcutpro.inspector.color.CorrectionsBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specific correction type.                                                                                         |
| **Parameters**                                       |  * `correctionType` - The correction type as string.                                       |
| **Returns**                                          |  *  `cp.apple.finalcutpro.inspector.color.CorrectionsBar` object.                                                |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The application object as a table                                                |

#### [findCorrectionLabel](#findcorrectionlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:findCorrectionLabel(correctionType) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns Correction Label.                                                                                         |
| **Parameters**                                       |  * correctionType - The correction type as string.                                       |
| **Returns**                                          |  * The correction label as string.                                                |

#### [menuButton](#menubutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:menuButton() -> MenuButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the menu button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `menuButton` object.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Corrections Bar's parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attempts to show the bar.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `CorrectionsBar` instance.                                                |

