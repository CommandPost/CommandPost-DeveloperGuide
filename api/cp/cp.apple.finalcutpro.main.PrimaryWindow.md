# [docs](index.md) » cp.apple.finalcutpro.main.PrimaryWindow
---

Primary Window Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [bottomGroupUI](#bottomgroupui)
 * [browserGroupUI](#browsergroupui)
 * [frame](#frame)
 * [hsWindow](#hswindow)
 * [isFullScreen](#isfullscreen)
 * [isShowing](#isshowing)
 * [leftGroupUI](#leftgroupui)
 * [rightGroupUI](#rightgroupui)
 * [rootGroupUI](#rootgroupui)
 * [timelineGroupUI](#timelinegroupui)
 * [topGroupUI](#topgroupui)
 * [UI](#ui)
 * [viewerGroupUI](#viewergroupui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [alert](#alert)
 * [app](#app)
 * [colorBoard](#colorboard)
 * [inspector](#inspector)
 * [new](#new)
 * [show](#show)
 * [toolbar](#toolbar)
 * [window](#window)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.matches(w) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if a window matches the PrimaryWindow requirements                                                                                         |
| **Parameters**                                       | <ul><li>w - The window to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if matched otherwise `false`</li></ul>          |

### Fields

#### [bottomGroupUI](#bottomgroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow:bottomGroupUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the bottom group UI as a `hs._asm.axuielement` object.                                                                                         |

#### [browserGroupUI](#browsergroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.browserGroupUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the UI which contains the Browser.                                                                                         |

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.frame <cp.prop: frame>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The current position (x, y, width, height) of the window.                                                                                         |

#### [hsWindow](#hswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.hsWindow <cp.prop: hs.window; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `hs.window` instance for the window, or `nil` if it can't be found.                                                                                         |

#### [isFullScreen](#isfullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.isFullScreen <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the window is full-screen.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.isShowing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the window is visible.                                                                                         |

#### [leftGroupUI](#leftgroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.leftGroupUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the left group UI as a `hs._asm.axuielement` object                                                                                         |

#### [rightGroupUI](#rightgroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.rightGroupUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the right group UI as a `hs._asm.axuielement` object.                                                                                         |

#### [rootGroupUI](#rootgroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.rootGroupUI() <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the top AXSplitGroup as a `hs._asm.axuielement` object                                                                                         |

#### [timelineGroupUI](#timelinegroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.timelineGroupUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the UI that contains the `Timeline`.                                                                                         |

#### [topGroupUI](#topgroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.topGroupUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the top group UI as a `hs._asm.axuielement` object.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.UI <cp.prop: axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` for the window.                                                                                         |

#### [viewerGroupUI](#viewergroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.viewerGroupUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the UI that contains the `Viewer`.                                                                                         |

### Methods

#### [alert](#alert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow:alert() -> cp.ui.Alert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Provides access to any 'Alert' windows on the PrimaryWindow.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A `cp.ui.Alert` object</li></ul>          |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow:app() -> hs.application` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the application the display belongs to.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The app instance.</li></ul>          |

#### [colorBoard](#colorboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow:colorBoard() -> ColorBoard` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorBoard object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorBoard</li></ul>          |

#### [inspector](#inspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow:inspector() -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Inspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Inspector</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow.new(app) -> PrimaryWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new PrimaryWindow.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>PrimaryWindow</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow:show() -> PrimaryWindow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Primary Window.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `PrimaryWindow` instance.</li></ul>          |

#### [toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow:toolbar() -> PrimaryToolbar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the PrimaryToolbar element.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `PrimaryToolbar`.</li></ul>          |

#### [window](#window)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryWindow:window() -> cp.ui.Window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `Window` instance.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `Window` instance.</li></ul>          |

