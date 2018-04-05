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
 * [app](#app)
 * [findCorrectionLabel](#findcorrectionlabel)
 * [isShowing](#isshowing)
 * [menuButton](#menubutton)
 * [parent](#parent)
 * [show](#show)
 * [UI](#ui)

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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:new(parent) -> CorrectionsBar` </span>                                                          |
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

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Corrections Bar currently showing?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if showing, otherwise `false`</li></ul>          |

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

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.CorrectionsBar:UI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A `hs._asm.axuielement` object or `nil`.</li></ul>          |

