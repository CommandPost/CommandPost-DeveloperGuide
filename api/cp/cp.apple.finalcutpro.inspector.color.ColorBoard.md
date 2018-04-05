# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorBoard
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
 * [matches](#matches)
 * [matchesCurrent](#matchescurrent)
 * [matchesOriginal](#matchesoriginal)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isColorInspectorSupported](#iscolorinspectorsupported)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [aspectGroup](#aspectgroup)
 * [backButton](#backbutton)
 * [childUI](#childui)
 * [color](#color)
 * [contentUI](#contentui)
 * [current](#current)
 * [exposure](#exposure)
 * [hide](#hide)
 * [isActive](#isactive)
 * [isShowing](#isshowing)
 * [new](#new)
 * [nextAspect](#nextaspect)
 * [parent](#parent)
 * [reset](#reset)
 * [saturation](#saturation)
 * [show](#show)
 * [topToolbarUI](#toptoolbarui)
 * [UI](#ui)

## API Documentation

### Constants

#### [aspect](#aspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.aspect -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing tables of all the aspect panel settings                                                                                         |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.aspect.color -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the Color Board Color panel settings                                                                                         |

#### [exposure](#exposure)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.aspect.exposure -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the Color Board Exposure panel settings                                                                                         |

#### [saturation](#saturation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.aspect.saturation -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the Color Board Saturation panel settings                                                                                         |

### Variables

#### [currentAspect](#currentaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.currentAspect -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The current aspect as a string.                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if a GUI element is the Color Board or not                                                                                         |
| **Parameters**                                       | <ul><li>`element`    - The element you want to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if the `element` is a Color Board otherwise `false`</li></ul>          |

#### [matchesCurrent](#matchescurrent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.matchesCurrent(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if a GUI element is the 'current' (10.4+) Color Board.                                                                                         |
| **Parameters**                                       | <ul><li>`element`    - The element you want to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if the `element` is a 10.4+ Color Board otherwise `false`</li></ul>          |

#### [matchesOriginal](#matchesoriginal)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.matchesOriginal(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if a GUI element is the 'original' (pre-10.4) Color Board.                                                                                         |
| **Parameters**                                       | <ul><li>`element`    - The element you want to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if the `element` is a pre-10.4 Color Board otherwise `false`</li></ul>          |

### Fields

#### [isColorInspectorSupported](#iscolorinspectorsupported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.isColorInspectorSupported <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the Color Inspector (from 10.4) is supported.                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul>          |

#### [aspectGroup](#aspectgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:aspectGroup() -> cp.ui.RadioGroup` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `RadioGroup` for the 'aspect' currently being controlled                                                                                          |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `RadioGroup`.</li></ul>          |

#### [backButton](#backbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:backButton() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `Button` to access the 'Back' button, if present.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `Button` for 'back'.</li></ul>          |
| **Notes**                                            | <ul><li>This no longer exists in FCP 10.4+, so will always be non-functional.</li></ul>                |

#### [childUI](#childui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:childUI(id) -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `hs._asm.axuielement` object for a child with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>axID - `AXIdentifier` of the child</li></ul> |
| **Returns**                                          | <ul><li>An `hs._asm.axuielement` object</li></ul>          |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:color() -> ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `color` aspect of the color board.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `ColorBoardAspect`.</li></ul>          |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:contentUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Color Board's content.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A `hs._asm.axuielement` object</li></ul>          |

#### [current](#current)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:current() -> ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the currently-selected 'aspect' of the Color Board - either the `color`, `saturation` or `exposure`.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The currently active `ColorBoardAspect`, or the `color` aspect if none is showing.</li></ul>          |

#### [exposure](#exposure)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:exposure() -> ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `exposure` aspect of the color board.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `ColorBoardAspect`.</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Color Board                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [isActive](#isactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:isActive() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the Color Board is active                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if the Color Board is active, otherwise `false`</li></ul>          |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the Color Board is visible                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if the Color Board is showing, otherwise `false`</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:new(parent) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new ColorBoard object                                                                                         |
| **Parameters**                                       | <ul><li>`parent`     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A ColorBoard object</li></ul>          |

#### [nextAspect](#nextaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:nextAspect() -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggles the Color Board Panels between "Color", "Saturation" and "Exposure"                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ColorBoard's parent table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul>          |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:reset() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resets the current aspect.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [saturation](#saturation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:saturation() -> ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `saturation` aspect of the color board.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `ColorBoardAspect`.</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:show() -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Color Board                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul>          |

#### [topToolbarUI](#toptoolbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:topToolbarUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `hs._asm.axuielement` object for the top toolbar (i.e. where the Back Button is located in Final Cut Pro 10.3)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `hs._asm.axuielement` object</li></ul>          |
| **Notes**                                            | <ul><li>This object doesn't exist in Final Cut Pro 10.4 as the Color Board is now contained within the Color Inspector</li></ul>                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:UI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Color Board                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A `hs._asm.axuielement` object</li></ul>          |

