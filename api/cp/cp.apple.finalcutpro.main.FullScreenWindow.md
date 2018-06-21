# [docs](index.md) » cp.apple.finalcutpro.main.FullScreenWindow
---

Full Screen Window

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isFullScreen](#isfullscreen)
 * [isShowing](#isshowing)
 * [rootGroupUI](#rootgroupui)
 * [UI](#ui)
 * [viewerGroupUI](#viewergroupui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [show](#show)
 * [window](#window)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow.new(app) -> FullScreenWindow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new FCPX `FullScreenWindow` instance.                                                                                         |
| **Parameters**                                       | * app       - The FCP app instance.                                       |
| **Returns**                                          | * The new `FullScreenWindow`.                                                |

### Fields

#### [isFullScreen](#isfullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow.isFullScreen <cp.prop; boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the window is full-screen.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow.isShowing <cp.prop; boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the window is currently showing.                                                                                         |

#### [rootGroupUI](#rootgroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow.rootGroupUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The root `AXGroup`.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow.UI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The core `axuielement` for the window.                                                                                         |

#### [viewerGroupUI](#viewergroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow.viewerGroupUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The Viewer's group UI element.                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow:app() -> cp.apple.finalcutpro` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the FCPX app.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The FCPX app.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow:show() -> cp.apple.finalcutpro` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attempts to show the full screen window.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The window instance.                                                |

#### [window](#window)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow:window() -> cp.ui.Window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `Window` instance for the full-screen window.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `Window` instance.                                                |

