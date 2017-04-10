# [docs](index.md) » hs.hints
---

Switch focus with a transient per-application keyboard shortcut

## API Overview
* Variables - Configurable values
** [fontName](#fontName)
** [fontSize](#fontSize)
** [hintChars](#hintChars)
** [showTitleThresh](#showTitleThresh)
** [style](#style)
** [titleMaxSize](#titleMaxSize)
* Functions - API calls offered directly by the extension
** [windowHints](#windowHints)

## API Documentation

### Variables

#### [fontName](#fontName)
| | |
|-|-|
| Signature   | hs.hints.fontName  |
| Type        | Variable |
| Description | A fully specified family-face name, preferrably the PostScript name, such as Helvetica-BoldOblique or Times-Roman. (The Font Book app displays PostScript names of fonts in the Font Info panel.) |
  The default value is the system font

#### [fontSize](#fontSize)
| | |
|-|-|
| Signature   | hs.hints.fontSize  |
| Type        | Variable |
| Description | The size of font that should be used. A value of 0.0 will use the default size. |

#### [hintChars](#hintChars)
| | |
|-|-|
| Signature   | hs.hints.hintChars  |
| Type        | Variable |
| Description | This controls the set of characters that will be used for window hints. They must be characters found in hs.keycodes.map |
  The default is the letters A-Z. Note that if `hs.hints.style` is set to "vimperator", this variable will be ignored.

#### [showTitleThresh](#showTitleThresh)
| | |
|-|-|
| Signature   | hs.hints.showTitleThresh  |
| Type        | Variable |
| Description | If there are less than or equal to this many windows on screen their titles will be shown in the hints. |
  The default is 4. Setting to 0 will disable this feature.

#### [style](#style)
| | |
|-|-|
| Signature   | hs.hints.style  |
| Type        | Variable |
| Description | If this is set to "vimperator", every window hint starts with the first character |
  of the parent application's title

#### [titleMaxSize](#titleMaxSize)
| | |
|-|-|
| Signature   | hs.hints.titleMaxSize  |
| Type        | Variable |
| Description | If the title is longer than maxSize, the string is truncated, -1 to disable, valid value is >= 6 |

### Functions

#### [windowHints](#windowHints)
| | |
|-|-|
| Signature   | hs.hints.windowHints([windows, callback, allowNonStandard])  |
| Type        | Function |
| Description | Displays a keyboard hint for switching focus to each window |
| Parameters |  * windows - An optional table containing some `hs.window` objects. If this value is nil, all windows will be hinted * callback - An optional function that will be called when a window has been selected by the user. The function will be called with a single argument containing the `hs.window` object of the window chosen by the user * allowNonStandard - An optional boolean.  If true, all windows will be included, not just standard windows | | Returns |  * None | | Notes |  * If there are more windows open than there are characters available in hs.hints.hintChars, multiple characters will be used * If hints.style is set to "vimperator", every window hint is prefixed with the first character of the parent application's name * To display hints only for the currently focused application, try something like:  * `hs.hints.windowHints(hs.window.focusedWindow():application():allWindows())` | 