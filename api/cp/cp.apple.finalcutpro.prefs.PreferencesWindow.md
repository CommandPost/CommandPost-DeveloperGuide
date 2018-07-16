# [docs](index.md) » cp.apple.finalcutpro.prefs.PreferencesWindow
---

Preferences Window Module.

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [frame](#frame)
 * [hsWindow](#hswindow)
 * [isFullScreen](#isfullscreen)
 * [isShowing](#isshowing)
 * [toolbar](#toolbar)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [window](#window)

## API Documentation

### Fields

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.frame <cp.prop: frame; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current position (x, y, width, height) of the window. |

#### [hsWindow](#hswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.hsWindow <cp.prop: hs.window; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `hs.window` instance for the window, or `nil` if it can't be found. |

#### [isFullScreen](#isfullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.isFullScreen <cp.prop: boolean; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is `true` if the window is full-screen. |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.isShowing <cp.prop: boolean; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is `true` if the window is visible. |

#### [toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.toolbar <cp.ui.Toolbar>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `Toolbar` for the Preferences Window. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.UI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` instance for the window. |

### Methods

#### [window](#window)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow:window() -> cp.ui.Window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `Window` for the Preferences Window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Window</code>.</li></ul> |

