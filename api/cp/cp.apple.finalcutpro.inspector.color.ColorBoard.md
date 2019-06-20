# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorBoard
---

Color Board Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [aspect](#aspect)
* Variables - Configurable values
 * [currentAspect](#currentaspect)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [ColorBoard](#colorboard)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contentUI](#contentui)
 * [isActive](#isactive)
 * [isShowing](#isshowing)
* Methods - API calls which can only be made on an object returned by a constructor
 * [aspectGroup](#aspectgroup)
 * [childUI](#childui)
 * [color](#color)
 * [current](#current)
 * [doHide](#dohide)
 * [doNextAspect](#donextaspect)
 * [doResetCurrent](#doresetcurrent)
 * [doSelectAspect](#doselectaspect)
 * [doShow](#doshow)
 * [exposure](#exposure)
 * [hide](#hide)
 * [nextAspect](#nextaspect)
 * [reset](#reset)
 * [saturation](#saturation)
 * [show](#show)

## API Documentation

### Constants

#### [aspect](#aspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.aspect -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table containing tables of all the aspect panel settings |

### Variables

#### [currentAspect](#currentaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.currentAspect -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The current aspect as a string. |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if a GUI element is the Color Board. |
| **Parameters**                                       | <ul><li><code>element</code>    - The element you want to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the <code>element</code> is a Color Board otherwise <code>false</code></li></ul> |

### Constructors

#### [ColorBoard](#colorboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard(parent) -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new ColorBoard object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A ColorBoard object</li></ul> |

### Fields

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.contentUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Color Board's content. |

#### [isActive](#isactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:isActive <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns whether or not the Color Board is active |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard.isShowing <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns whether or not the Color Board is visible. |

### Methods

#### [aspectGroup](#aspectgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:aspectGroup() -> cp.ui.RadioGroup` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `RadioGroup` for the 'aspect' currently being controlled  |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>RadioGroup</code>.</li></ul> |

#### [childUI](#childui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:childUI(id) -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the `hs._asm.axuielement` object for a child with the specified ID. |
| **Parameters**                                       | <ul><li>axID - <code>AXIdentifier</code> of the child</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs._asm.axuielement</code> object</li></ul> |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:color() -> ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `color` aspect of the color board. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorBoardAspect</code>.</li></ul> |

#### [current](#current)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:current() -> ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the currently-selected 'aspect' of the Color Board - either the `color`, `saturation` or `exposure`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The currently active <code>ColorBoardAspect</code>, or the <code>color</code> aspect if none is showing.</li></ul> |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that hides the Color Board. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, which will send a single <code>true</code> if successful, otherwise <code>false</code>, or an error being sent.</li></ul> |

#### [doNextAspect](#donextaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:doNextAspect() -> cp.rx.go.Statement<boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that toggles the Color Board Panels between "Color", "Saturation" and "Exposure". |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul> |

#### [doResetCurrent](#doresetcurrent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:doResetCurrent([range]) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will reset the current 'active' aspect (e.g. `color`) in the Color Board. |
| **Parameters**                                       | <ul><li>range     - Optional range to reset in the current aspect.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving with <code>true</code> if completed or an error if not.</li></ul> |

#### [doSelectAspect](#doselectaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:doSelectAspect(index) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to select the specified aspect `index`. |
| **Parameters**                                       | <ul><li>index     - The index to select.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, which will resolve to <code>true</code> if successful, or throw an error if not.</li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that shows the Color Board. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, which will send a single <code>true</code> if successful, otherwise <code>false</code>, or an error being sent.</li></ul> |

#### [exposure](#exposure)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:exposure() -> ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `exposure` aspect of the color board. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorBoardAspect</code>.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the Color Board |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul> |

#### [nextAspect](#nextaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:nextAspect() -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Toggles the Color Board Panels between "Color", "Saturation" and "Exposure" |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:reset() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resets the current aspect. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul> |

#### [saturation](#saturation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:saturation() -> ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `saturation` aspect of the color board. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorBoardAspect</code>.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoard:show() -> ColorBoard object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Color Board |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard object</li></ul> |

