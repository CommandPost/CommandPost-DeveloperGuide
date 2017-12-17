# [docs](index.md) » cp.apple.finalcutpro.main.ColorBoard
---

Color Board Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [aspect](#aspect)
 * [color](#color)
 * [exposure](#exposure)
 * [saturation](#saturation)
* Variables - Configurable values
 * [currentAspect](#currentaspect)
* Functions - API calls offered directly by the extension
 * [isColorBoard](#iscolorboard)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [applyAngle](#applyangle)
 * [applyPercentage](#applypercentage)
 * [aspectPropertyPanelUI](#aspectpropertypanelui)
 * [childUI](#childui)
 * [colorInspectorBarUI](#colorinspectorbarui)
 * [colorSatExpUI](#colorsatexpui)
 * [getAngle](#getangle)
 * [getAspect](#getaspect)
 * [getPercentage](#getpercentage)
 * [hide](#hide)
 * [isActive](#isactive)
 * [isShowing](#isshowing)
 * [new](#new)
 * [parent](#parent)
 * [puckUI](#puckui)
 * [reset](#reset)
 * [selectedPanel](#selectedpanel)
 * [selectPuck](#selectpuck)
 * [shiftAngle](#shiftangle)
 * [shiftPercentage](#shiftpercentage)
 * [show](#show)
 * [showInspectorUI](#showinspectorui)
 * [showPanel](#showpanel)
 * [startPucker](#startpucker)
 * [togglePanel](#togglepanel)
 * [topToolbarUI](#toptoolbarui)
 * [UI](#ui)

## API Documentation

### Constants

#### [aspect](#aspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard.aspect -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing tables of all the aspect panel settings                                                                                         |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard.aspect.color -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the Color Board Color panel settings                                                                                         |

#### [exposure](#exposure)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard.aspect.exposure -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the Color Board Exposure panel settings                                                                                         |

#### [saturation](#saturation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard.aspect.saturation -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the Color Board Saturation panel settings                                                                                         |

### Variables

#### [currentAspect](#currentaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard.currentAspect -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The current aspect as a string.                                                                                         |

### Functions

#### [isColorBoard](#iscolorboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard.isColorBoard(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if a GUI element is the Color Board or not                                                                                         |
| **Parameters**                                       | <ul><li>`element`	- The element you want to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if the `element` is a Color Board otherwise `false`</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul>          |

#### [applyAngle](#applyangle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:applyAngle(aspect, property, value) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies a Color Board Angle value to the specified aspect/property                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li><li>value		- value as string</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [applyPercentage](#applypercentage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:applyPercentage(aspect, property, value) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies a Color Board Percentage value to the specified aspect/property                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li><li>value		- value as string</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [aspectPropertyPanelUI](#aspectpropertypanelui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:aspectPropertyPanelUI(aspect, property, type) -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Ensures that the specified aspect/property panel is visible and returns the specified value type `hs._asm.axuielement` object                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li><li>type			- "pct" or "angle"</li></ul> |
| **Returns**                                          | <ul><li>An `hs._asm.axuielement` object or `nil` if an error occurs</li></ul>          |

#### [childUI](#childui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:childUI(id) -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `hs._asm.axuielement` object for a child with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>id - `AXIdentifier` of the child</li></ul> |
| **Returns**                                          | <ul><li>An `hs._asm.axuielement` object</li></ul>          |

#### [colorInspectorBarUI](#colorinspectorbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:colorInspectorBarUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Final Cut Pro 10.4 Color Board Inspector Bar (i.e. where you can add new Color Corrections from the dropdown)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A `hs._asm.axuielement` object</li></ul>          |

#### [colorSatExpUI](#colorsatexpui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:colorSatExpUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `hs._asm.axuielement` object for the `AXRadioGroup` which houses the "Color", "Saturation" and "Exposure" button                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `hs._asm.axuielement` object</li></ul>          |

#### [getAngle](#getangle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:getAngle(aspect, property) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets an angle value of the specified `aspect` and `property`                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li></ul> |
| **Returns**                                          | <ul><li>Number or `nil` if an error occurred</li></ul>          |

#### [getAspect](#getaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:getAspect(aspect, property) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a table containing the ID information for a specific `aspect` and `property`                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li></ul> |
| **Returns**                                          | <ul><li>A table or `nil` if an error occurs</li></ul>          |

#### [getPercentage](#getpercentage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:getPercentage(aspect, property) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a percentage value of the specified `aspect` and `property`                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li></ul> |
| **Returns**                                          | <ul><li>Number or `nil` if an error occurred</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:hide() -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Color Board                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [isActive](#isactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:isActive() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the Color Board is active                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if the Color Board is active, otherwise `false`</li></ul>          |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the Color Board is visible                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if the Color Board is showing, otherwise `false`</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:new(parent) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new ColorBoard object                                                                                         |
| **Parameters**                                       | <ul><li>`parent`		- The parent</li></ul> |
| **Returns**                                          | <ul><li>A ColorBoard object</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ColorBoard's parent table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul>          |

#### [puckUI](#puckui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:puckUI(aspect, property) -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `hs._asm.axuielement` object of a specific Color Board puck                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li></ul> |
| **Returns**                                          | <ul><li>An `hs._asm.axuielement` object</li></ul>          |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:reset(aspect) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resets a specified `aspect`                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [selectedPanel](#selectedpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:selectedPanel() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the currently selected Color Board panel                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>"Color", "Saturation", "Exposure" or `nil` if an error occurs</li></ul>          |

#### [selectPuck](#selectpuck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:selectPuck(aspect, property) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a specific Color Board puck                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [shiftAngle](#shiftangle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:shiftAngle(aspect, property, shift) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shifts a Color Board Angle value of the specified aspect/property                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li><li>shift		- number you want to increase/decrease the angle by</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [shiftPercentage](#shiftpercentage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:shiftPercentage(aspect, property, shift) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shifts a Color Board Percentage value of the specified aspect/property                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li><li>shift		- number you want to increase/decrease the percentage by</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:show() -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Color Board                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [showInspectorUI](#showinspectorui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:showInspectorUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `hs._asm.axuielement` object for the inspector                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `hs._asm.axuielement` object</li></ul>          |

#### [showPanel](#showpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:showPanel(aspect) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows a specific panel based on the specified `aspect`                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [startPucker](#startpucker)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:startPucker(aspect, property) -> Pucker object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a Pucker object for the specified `aspect` and `property`                                                                                         |
| **Parameters**                                       | <ul><li>aspect 		- "color", "saturation" or "exposure"</li><li>property 	- "global", "shadows", "midtones" or "highlights"</li></ul> |
| **Returns**                                          | <ul><li>Pucker object</li></ul>          |

#### [togglePanel](#togglepanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:togglePanel() -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggles the Color Board Panels between "Color", "Saturation" and "Exposure"                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [topToolbarUI](#toptoolbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:topToolbarUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `hs._asm.axuielement` object for the top toolbar (i.e. where the Back Button is located in Final Cut Pro 10.3)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `hs._asm.axuielement` object</li></ul>          |
| **Notes**                                            | <ul><li>This object doesn't exist in Final Cut Pro 10.4 as the Color Board is now contained within the Color Inspector</li></ul>                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ColorBoard:UI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Color Board                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A `hs._asm.axuielement` object</li></ul>          |

