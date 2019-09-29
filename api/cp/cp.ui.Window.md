# [docs](index.md) » cp.ui.Window
---

A Window UI element.

## API Overview
* Functions - API calls offered directly by the extension
 * [findSectionUI](#findsectionui)
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Window](#window)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [exists](#exists)
 * [focused](#focused)
 * [frame](#frame)
 * [fullScreen](#fullscreen)
 * [hsWindow](#hswindow)
 * [id](#id)
 * [isShowing](#isshowing)
 * [minimized](#minimized)
 * [UI](#ui)
 * [visible](#visible)
* Methods - API calls which can only be made on an object returned by a constructor
 * [alert](#alert)
 * [close](#close)
 * [doClose](#doclose)
 * [doFocus](#dofocus)
 * [findSectionUI](#findsectionui)
 * [focus](#focus)
 * [notifier](#notifier)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [findSectionUI](#findsectionui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.findSectionUI(windowUI, sectionID) -> hs._asm.axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Finds the `axuielement` for the specified `sectionID`, if present in the provided `axuielement` `windowUI`. |
| **Parameters**                                       | <ul><li>windowUI - The <code>AXWindow</code> <code>axuielement</code> to search in.</li><li>sectionID - The string value for the <code>SectionUniqueID</code>.</li></ul> |
| **Returns**                                          | <ul><li>The matching <code>axuielement</code>, or <code>nil</code>.</li></ul> |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided element is a valid window. |

### Constructors

#### [Window](#window)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window(cpApp, uiProp) -> Window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Window |
| **Parameters**                                       | <ul><li><code>cpApp</code>    - a <code>cp.app</code> for the application the Window belongs to.</li><li><code>uiProp</code>   - a <code>cp.prop</code> that returns the <code>hs._asm.axuielement</code> for the window.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Window</code> instance.</li></ul> |

### Fields

#### [exists](#exists)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.exists <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns `true` if the window exists. It may not be visible. |

#### [focused](#focused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.focused <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is `true` if the window has mouse/keyboard focused. |

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.frame <cp.prop: hs.geometry rect>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `hs.geometry` rect value describing the window's position. |

#### [fullScreen](#fullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.fullScreen <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns `true` if the window is full-screen. |

#### [hsWindow](#hswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.hsWindow <cp.prop: hs.window; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `hs.window` instance for the window, or `nil` if it can't be found. |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.id <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The window title, or `nil` if the window is not currently visible. |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.isShowing <cp.prop: boolean; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the `Window` is currently showing on screen. |

#### [minimized](#minimized)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.minimized <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns `true` if the window exists and is minimised. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.UI <cp.prop: hs._asm.axuielement: read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The UI `axuielement` for the Window. |

#### [visible](#visible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window.visible <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns `true` if the window is visible on a screen. |

### Methods

#### [alert](#alert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:alert() -> cp.ui.Alert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides access to any 'Alert' windows on the Window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>cp.ui.Alert</code> object</li></ul> |

#### [close](#close)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:close() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to close the window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the window was successfully closed.</li></ul> |

#### [doClose](#doclose)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:doClose() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will attempt to close the window, if it is visible. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute, resolving to <code>true</code> if the window is closed successfully, or <code>false</code> if not.</li></ul> |

#### [doFocus](#dofocus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:doFocus() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) will attempt to focus on the window, if it is visible. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute, which resolves to <code>true</code> if the window was successfully focused, or <code>false</code> if not.</li></ul> |

#### [findSectionUI](#findsectionui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:findSectionUI(sectionID) -> hs._asm.axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Looks for th section with the specified `SectionUniqueID` value and returns the matching `axuielement` value. |
| **Parameters**                                       | <ul><li>sectionID - The string for the section ID.</li></ul> |
| **Returns**                                          | <ul><li>The matching <code>axuielement</code>, or <code>nil</code>.</li></ul> |

#### [focus](#focus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:focus() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to focus the window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the window was successfully focused.</li></ul> |

#### [notifier](#notifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:notifier() -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `notifier` that is tracking the application UI element. It has already been started. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The notifier.</li></ul> |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Window:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it. |
| **Parameters**                                       | <ul><li>path      - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li></ul> |

