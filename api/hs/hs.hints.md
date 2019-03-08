# [docs](index.md) » hs.hints
---

Switch focus with a transient per-application keyboard shortcut

## API Overview
* Variables - Configurable values
 * [fontName](#fontname)
 * [fontSize](#fontsize)
 * [hintChars](#hintchars)
 * [iconAlpha](#iconalpha)
 * [showTitleThresh](#showtitlethresh)
 * [style](#style)
 * [titleMaxSize](#titlemaxsize)
* Functions - API calls offered directly by the extension
 * [windowHints](#windowhints)

## API Documentation

### Variables

#### [fontName](#fontname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hints.fontName` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A fully specified family-face name, preferrably the PostScript name, such as Helvetica-BoldOblique or Times-Roman. (The Font Book app displays PostScript names of fonts in the Font Info panel.) |

#### [fontSize](#fontsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hints.fontSize` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The size of font that should be used. A value of 0.0 will use the default size. |

#### [hintChars](#hintchars)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hints.hintChars` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | This controls the set of characters that will be used for window hints. They must be characters found in hs.keycodes.map |

#### [iconAlpha](#iconalpha)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hints.iconAlpha` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Opacity of the application icon. Default is 0.95. |

#### [showTitleThresh](#showtitlethresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hints.showTitleThresh` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | If there are less than or equal to this many windows on screen their titles will be shown in the hints. |

#### [style](#style)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hints.style` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | If this is set to "vimperator", every window hint starts with the first character |

#### [titleMaxSize](#titlemaxsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hints.titleMaxSize` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | If the title is longer than maxSize, the string is truncated, -1 to disable, valid value is >= 6 |

### Functions

#### [windowHints](#windowhints)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hints.windowHints([windows, callback, allowNonStandard])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Displays a keyboard hint for switching focus to each window |
| **Parameters**                                       | <ul><li>windows - An optional table containing some <code>hs.window</code> objects. If this value is nil, all windows will be hinted</li><li>callback - An optional function that will be called when a window has been selected by the user. The function will be called with a single argument containing the <code>hs.window</code> object of the window chosen by the user</li><li>allowNonStandard - An optional boolean.  If true, all windows will be included, not just standard windows</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>If there are more windows open than there are characters available in hs.hints.hintChars, multiple characters will be used</li><li>If hints.style is set to "vimperator", every window hint is prefixed with the first character of the parent application's name</li><li>To display hints only for the currently focused application, try something like:</li><li><code>hs.hints.windowHints(hs.window.focusedWindow():application():allWindows())</code></li></ul> |

