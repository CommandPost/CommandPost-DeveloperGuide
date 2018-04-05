# [docs](index.md) » cp.ui.Window
---

A Window UI element.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [exists](#exists)
 * [focused](#focused)
 * [frame](#frame)
 * [fullScreen](#fullscreen)
 * [hsWindow](#hswindow)
 * [id](#id)
 * [minimized](#minimized)
 * [UI](#ui)
 * [visible](#visible)
* Methods - API calls which can only be made on an object returned by a constructor
 * [close](#close)
 * [focus](#focus)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the provided element is a valid window.                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:new(finderFn) -> Window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Window                                                                                         |
| **Parameters**                                       | <ul><li>`finderFn`   - a function which will provide the `axuielement` for the window to work with.</li></ul> |
| **Returns**                                          | <ul><li>A new `Window` instance.</li></ul>          |

### Fields

#### [exists](#exists)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.exists <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns `true` if the window exists. It may not be visible.                                                                                         |

#### [focused](#focused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.focused <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the window has mouse/keyboard focused.                                                                                         |

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.frame <cp.prop: hs.geometry rect>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `hs.geometry` rect value describing the window's position.                                                                                         |

#### [fullScreen](#fullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.fullScreen <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns `true` if the window is full-screen.                                                                                         |

#### [hsWindow](#hswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.hsWindow <cp.prop: hs.window; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `hs.window` instance for the window, or `nil` if it can't be found.                                                                                         |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.id <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The unique ID for the window.                                                                                         |

#### [minimized](#minimized)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.minimized <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns `true` if the window exists and is minimised.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.UI <cp.prop: axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `axuielement` UI for the window, or `nil` if it can't be found.                                                                                         |

#### [visible](#visible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.visible <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns `true` if the window is visible on a screen.                                                                                         |

### Methods

#### [close](#close)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.close() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attempts to close the window.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the window was successfully closed.</li></ul>          |

#### [focus](#focus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.focus() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attempts to focus the window.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the window was successfully focused.</li></ul>          |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>* path		- (optional) The path to save the file. Should include the extension (should be `.png`).</li></ul> |

