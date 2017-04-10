# [docs](index.md) » hs.window
---

Inspect/manipulate windows

Notes:
 * See `hs.screen` and `hs.geometry` for more information on how Hammerspoon uses window/screen frames and coordinates

## Submodules
 * [hs.window.filter](hs.window.filter.md)
 * [hs.window.highlight](hs.window.highlight.md)
 * [hs.window.layout](hs.window.layout.md)
 * [hs.window.switcher](hs.window.switcher.md)
 * [hs.window.tiling](hs.window.tiling.md)

## API Overview
* Variables - Configurable values
 * [animationDuration](#animationDuration)
 * [setFrameCorrectness](#setFrameCorrectness)
* Functions - API calls offered directly by the extension
 * [allWindows](#allWindows)
 * [desktop](#desktop)
 * [orderedWindows](#orderedWindows)
 * [setShadows](#setShadows)
 * [snapshotForID](#snapshotForID)
 * [visibleWindows](#visibleWindows)
* Constructors - API calls which return an object, typically one that offers API methods
 * [find](#find)
 * [focusedWindow](#focusedWindow)
 * [frontmostWindow](#frontmostWindow)
 * [get](#get)
* Methods - API calls which can only be made on an object returned by a constructor
 * [application](#application)
 * [becomeMain](#becomeMain)
 * [centerOnScreen](#centerOnScreen)
 * [close](#close)
 * [focus](#focus)
 * [focusWindowEast](#focusWindowEast)
 * [focusWindowNorth](#focusWindowNorth)
 * [focusWindowSouth](#focusWindowSouth)
 * [focusWindowWest](#focusWindowWest)
 * [frame](#frame)
 * [id](#id)
 * [isFullScreen](#isFullScreen)
 * [isMinimized](#isMinimized)
 * [isStandard](#isStandard)
 * [isVisible](#isVisible)
 * [maximize](#maximize)
 * [minimize](#minimize)
 * [move](#move)
 * [moveOneScreenEast](#moveOneScreenEast)
 * [moveOneScreenNorth](#moveOneScreenNorth)
 * [moveOneScreenSouth](#moveOneScreenSouth)
 * [moveOneScreenWest](#moveOneScreenWest)
 * [moveToScreen](#moveToScreen)
 * [moveToUnit](#moveToUnit)
 * [otherWindowsAllScreens](#otherWindowsAllScreens)
 * [otherWindowsSameScreen](#otherWindowsSameScreen)
 * [raise](#raise)
 * [role](#role)
 * [screen](#screen)
 * [sendToBack](#sendToBack)
 * [setFrame](#setFrame)
 * [setFrameInScreenBounds](#setFrameInScreenBounds)
 * [setFrameWithWorkarounds](#setFrameWithWorkarounds)
 * [setFullScreen](#setFullScreen)
 * [setSize](#setSize)
 * [setTopLeft](#setTopLeft)
 * [size](#size)
 * [snapshot](#snapshot)
 * [subrole](#subrole)
 * [title](#title)
 * [toggleFullScreen](#toggleFullScreen)
 * [toggleZoom](#toggleZoom)
 * [topLeft](#topLeft)
 * [unminimize](#unminimize)
 * [windowsToEast](#windowsToEast)
 * [windowsToNorth](#windowsToNorth)
 * [windowsToSouth](#windowsToSouth)
 * [windowsToWest](#windowsToWest)
 * [zoomButtonRect](#zoomButtonRect)

## API Documentation
### Variables

#### [animationDuration](#animationDuration)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.animationDuration (number)  |
| Type        | Variable |
| Description | The default duration for animations, in seconds. Initial value is 0.2; set to 0 to disable animations. |


#### [setFrameCorrectness](#setFrameCorrectness)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.setFrameCorrectness  |
| Type        | Variable |
| Description | Using `hs.window:setFrame()` in some cases does not work as expected: namely, the bottom (or Dock) edge, and edges between screens, might |
 |

### Functions

#### [allWindows](#allWindows)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.allWindows() -> list of hs.window objects  |
| Type        | Function |
| Description | Returns all windows |
| Parameters |  * None |
| Returns |  * A list of `hs.window` objects representing all open windows |
| Notes |  * `visibleWindows()`, `orderedWindows()`, `get()`, `find()`, and several more functions and methods in this and other    modules make use of this function, so it is important to understand its limitations * This function queries all applications for their windows every time it is invoked; if you need to call it a lot and   performance is not acceptable consider using the `hs.window.filter` module * This function can only return windows in the current Mission Control Space; if you need to address windows across   different Spaces you can use the `hs.window.filter` module   - if `Displays have separate Spaces` is *on* (in System Preferences>Mission Control) the current Space is defined     as the union of all currently visible Spaces   - minimized windows and hidden windows (i.e. belonging to hidden apps, e.g. via cmd-h) are always considered     to be in the current Space * This function filters out the desktop "window"; use `hs.window.desktop()` to address it. (Note however that   `hs.application.get'Finder':allWindows()` *will* include the desktop in the returned list) * Beside the limitations discussed above, this function will return *all* windows as reported by OSX, including some   "windows" that one wouldn't expect: for example, every Google Chrome (actual) window has a companion window for its   status bar; therefore you might get unexpected results  - in the Chrome example, calling `hs.window.focusWindowSouth()`   from a Chrome window would end up "focusing" its status bar, and therefore the proper window itself, seemingly resulting   in a no-op. In order to avoid such surprises you can use the `hs.window.filter` module, and more specifically   the default windowfilter (`hs.window.filter.default`) which filters out known cases of not-actual-windows

#### [desktop](#desktop)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.desktop() -> hs.window object  |
| Type        | Function |
| Description | Returns the desktop "window" |
| Parameters |  * None |
| Returns |  * An `hs.window` object representing the desktop |
| Notes |  * The desktop belongs to Finder.app: when Finder is the active application, you can focus the desktop by cycling   through windows via cmd-` * The desktop window has no id, a role of `AXScrollArea` and no subrole * The desktop is filtered out from `hs.window.allWindows()` (and downstream uses)

#### [orderedWindows](#orderedWindows)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.orderedWindows() -> list of hs.window objects  |
| Type        | Function |
| Description | Returns all visible windows, ordered from front to back |
| Parameters |  * None |
| Returns |  * A list of `hs.window` objects representing all visible windows, ordered from front to back |


#### [setShadows](#setShadows)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.setShadows(shadows)  |
| Type        | Function |
| Description | Enables/Disables window shadows |
| Parameters |  * shadows - A boolean, true to show window shadows, false to hide window shadows |
| Returns |  * None |
| Notes |  * This function uses a private, undocumented OS X API call, so it is not guaranteed to work in any future OS X release

#### [snapshotForID](#snapshotForID)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.snapshotForID(ID [, keepTransparency]) -> hs.image-object  |
| Type        | Function |
| Description | Returns a snapshot of the window specified by the ID as an `hs.image` object |
| Parameters |  * ID - Window ID of the window to take a snapshot of. * keepTransparency - optional boolean value indicating if the windows alpha value (transparency) should be maintained in the resulting image or if it should be fully opaque (default). |
| Returns |  * `hs.image` object of the window snapshot or nil if unable to create a snapshot |
| Notes |  * See also method `hs.window:snapshot()` * Because the window ID cannot always be dynamically determined, this function will allow you to provide the ID of a window that was cached earlier.

#### [visibleWindows](#visibleWindows)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.visibleWindows() -> list of hs.window objects  |
| Type        | Function |
| Description | Gets all visible windows |
| Parameters |  * None |
| Returns |  * A list containing `hs.window` objects representing all windows that are visible as per `hs.window:isVisible()` |
 |

### Constructors

#### [find](#find)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.find(hint) -> hs.window object(s)  |
| Type        | Constructor |
| Description | Finds windows |
| Parameters |  * hint - search criterion for the desired window(s); it can be:   - an id number as per `hs.window:id()`   - a string pattern that matches (via `string.find`) the window title as per `hs.window:title()` (for convenience, the matching will be done on lowercased strings) |
| Returns |  * one or more hs.window objects that match the supplied search criterion, or `nil` if none found |
| Notes |  * for convenience you can call this as `hs.window(hint)` * see also `hs.window.get` * for more sophisticated use cases and/or for better performance if you call this a lot, consider using `hs.window.filter`

#### [focusedWindow](#focusedWindow)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.focusedWindow() -> window  |
| Type        | Constructor |
| Description | Returns the window that has keyboard/mouse focus |
| Parameters |  * None |
| Returns |  * An `hs.window` object representing the currently focused window |


#### [frontmostWindow](#frontmostWindow)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.frontmostWindow() -> hs.window object  |
| Type        | Constructor |
| Description | Returns the focused window or, if no window has focus, the frontmost one |
| Parameters |  * None |
| Returns | * An `hs.window` object representing the frontmost window, or `nil` if there are no visible windows |


#### [get](#get)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window.get(hint) -> hs.window object  |
| Type        | Constructor |
| Description | Gets a specific window |
| Parameters |  * hint - search criterion for the desired window; it can be:   - an id number as per `hs.window:id()`   - a window title string as per `hs.window:title()` |
| Returns |  * the first hs.window object that matches the supplied search criterion, or `nil` if not found |
| Notes |  * see also `hs.window.find` and `hs.application:getWindow()` |

### Methods

#### [application](#application)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:application() -> app or nil  |
| Type        | Method |
| Description | Gets the `hs.application` object the window belongs to |
| Parameters |  * None |
| Returns |  * An `hs.application` object representing the application that owns the window, or nil if an error occurred |


#### [becomeMain](#becomeMain)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:becomeMain() -> window  |
| Type        | Method |
| Description | Makes the window the main window of its application |
| Parameters |  * None |
| Returns |  * The `hs.window` object |
| Notes |  * Make a window become the main window does not transfer focus to the application. See `hs.window.focus()`

#### [centerOnScreen](#centerOnScreen)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:centerOnScreen([screen][, ensureInScreenBounds][, duration]) --> hs.window object  |
| Type        | Method |
| Description | Centers the window on a screen |
| Parameters |  * screen - (optional) An `hs.screen` object or argument for `hs.screen.find`; if nil, use the screen the window is currently on * ensureInScreenBounds - (optional) if `true`, use `setFrameInScreenBounds()` to ensure the resulting window frame is fully contained within   the window's screen * duration - (optional) The number of seconds to animate the transition. Defaults to the value of `hs.window.animationDuration` |
| Returns |  * The `hs.window` object |


#### [close](#close)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:close() -> bool  |
| Type        | Method |
| Description | Closes the window |
| Parameters |  * None |
| Returns |  * True if the operation succeeded, false if not |


#### [focus](#focus)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:focus() -> hs.window object  |
| Type        | Method |
| Description | Focuses the window |
| Parameters |  * None |
| Returns |  * The `hs.window` object |


#### [focusWindowEast](#focusWindowEast)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:focusWindowEast([candidateWindows[, frontmost[, strict]]]) -> boolean  |
| Type        | Method |
| Description | Focuses the nearest possible window to the east (i.e. right) |
| Parameters |  * candidateWindows - (optional) a list of candidate windows to consider; if nil, all visible windows   to the east are candidates. * frontmost - (optional) boolean, if true focuses the nearest window that isn't occluded by any other window * strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   eastward axis |
| Returns |  * `true` if a window was found and focused, `false` otherwise; `nil` if the search couldn't take place |
| Notes |  * If you don't pass `candidateWindows`, Hammerspoon will query for the list of all visible windows   every time this method is called; this can be slow, and some undesired "windows" could be included   (see the notes for `hs.window.allWindows()`); consider using the equivalent methods in   `hs.window.filter` instead

#### [focusWindowNorth](#focusWindowNorth)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:focusWindowNorth([candidateWindows[, frontmost[, strict]]]) -> boolean  |
| Type        | Method |
| Description | Focuses the nearest possible window to the north (i.e. up) |


#### [focusWindowSouth](#focusWindowSouth)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:focusWindowSouth([candidateWindows[, frontmost[, strict]]]) -> boolean  |
| Type        | Method |
| Description | Focuses the nearest possible window to the south (i.e. down) |


#### [focusWindowWest](#focusWindowWest)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:focusWindowWest([candidateWindows[, frontmost[, strict]]]) -> boolean  |
| Type        | Method |
| Description | Focuses the nearest possible window to the west (i.e. right) |


#### [frame](#frame)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:frame() -> hs.geometry rect  |
| Type        | Method |
| Description | Gets the frame of the window in absolute coordinates |
| Parameters |  * None |
| Returns |  * An hs.geometry rect containing the co-ordinates of the top left corner of the window and its width and height |


#### [id](#id)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:id() -> number or nil  |
| Type        | Method |
| Description | Gets the unique identifier of the window |
| Parameters |  * None |
| Returns |  * A number containing the unique identifier of the window, or nil if an error occurred |


#### [isFullScreen](#isFullScreen)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:isFullScreen() -> bool or nil  |
| Type        | Method |
| Description | Gets the fullscreen state of the window |
| Parameters |  * None |
| Returns |  * True if the window is fullscreen, false if not. Nil if an error occurred |


#### [isMinimized](#isMinimized)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:isMinimized() -> bool  |
| Type        | Method |
| Description | Gets the minimized state of the window |
| Parameters |  * None |
| Returns |  * True if the window is minimized, otherwise false |


#### [isStandard](#isStandard)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:isStandard() -> bool  |
| Type        | Method |
| Description | Determines if the window is a standard window |
| Parameters |  * None |
| Returns |  * True if the window is standard, otherwise false |
| Notes |  * "Standard window" means that this is not an unusual popup window, a modal dialog, a floating window, etc.

#### [isVisible](#isVisible)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:isVisible() -> boolean  |
| Type        | Method |
| Description | Determines if a window is visible (i.e. not hidden and not minimized) |
| Parameters |  * None |
| Returns |  * `true` if the window is visible, otherwise `false` |
| Notes |  * This does not mean the user can see the window - it may be obscured by other windows, or it may be off the edge of the screen

#### [maximize](#maximize)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:maximize([duration]) -> hs.window object  |
| Type        | Method |
| Description | Maximizes the window |
| Parameters |  * duration - (optional) The number of seconds to animate the transition. Defaults to the value of `hs.window.animationDuration` |
| Returns |  * The `hs.window` object |
| Notes |  * The window will be resized as large as possible, without obscuring the dock/menu

#### [minimize](#minimize)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:minimize() -> window  |
| Type        | Method |
| Description | Minimizes the window |
| Parameters |  * None |
| Returns |  * The `hs.window` object |
| Notes |  * This method will always animate per your system settings and is not affected by `hs.window.animationDuration`

#### [move](#move)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:move(rect[, screen][, ensureInScreenBounds][, duration]) --> hs.window object  |
| Type        | Method |
| Description | Moves the window |
| Parameters |  * rect - It can be:   - an `hs.geometry` point, or argument to construct one; will move the screen by this delta, keeping its size constant; `screen` is ignored   - an `hs.geometry` rect, or argument to construct one; will set the window frame to this rect, in absolute coordinates; `screen` is ignored   - an `hs.geometry` unit rect, or argument to construct one; will set the window frame to this rect relative to the desired screen;     if `screen` is nil, use the screen the window is currently on * screen - (optional) An `hs.screen` object or argument for `hs.screen.find`; only valid if `rect` is a unit rect * ensureInScreenBounds - (optional) if `true`, use `setFrameInScreenBounds()` to ensure the resulting window frame is fully contained within   the window's screen * duration - (optional) The number of seconds to animate the transition. Defaults to the value of `hs.window.animationDuration` |
| Returns |  * The `hs.window` object |


#### [moveOneScreenEast](#moveOneScreenEast)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:moveOneScreenEast([noResize, ensureInScreenBounds][, duration]) -> hs.window object  |
| Type        | Method |
| Description | Moves the window one screen east (i.e. right) |
| Parameters |  * noResize - (optional) if `true`, maintain the window's absolute size * ensureInScreenBounds - (optional) if `true`, use `setFrameInScreenBounds()` to ensure the resulting window frame is fully contained within   the window's screen * duration - (optional) The number of seconds to animate the transition. Defaults to the value of `hs.window.animationDuration` |
| Returns |  * The `hs.window` object |


#### [moveOneScreenNorth](#moveOneScreenNorth)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:moveOneScreenNorth([noResize, ensureInScreenBounds][, duration]) -> hs.window object  |
| Type        | Method |
| Description | Moves the window one screen north (i.e. up) |


#### [moveOneScreenSouth](#moveOneScreenSouth)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:moveOneScreenSouth([noResize, ensureInScreenBounds][, duration]) -> hs.window object  |
| Type        | Method |
| Description | Moves the window one screen south (i.e. down) |


#### [moveOneScreenWest](#moveOneScreenWest)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:moveOneScreenWest([noResize, ensureInScreenBounds][, duration]) -> hs.window object  |
| Type        | Method |
| Description | Moves the window one screen west (i.e. left) |


#### [moveToScreen](#moveToScreen)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:moveToScreen(screen[, noResize, ensureInScreenBounds][, duration]) -> hs.window object  |
| Type        | Method |
| Description | Moves the window to a given screen, retaining its relative position and size |
| Parameters |  * screen - An `hs.screen` object, or an argument for `hs.screen.find()`, representing the screen to move the window to * noResize - (optional) if `true`, maintain the window's absolute size * ensureInScreenBounds - (optional) if `true`, use `setFrameInScreenBounds()` to ensure the resulting window frame is fully contained within   the window's screen * duration - (optional) The number of seconds to animate the transition. Defaults to the value of `hs.window.animationDuration` |
| Returns |  * The `hs.window` object |


#### [moveToUnit](#moveToUnit)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:moveToUnit(unitrect[, duration]) -> hs.window object  |
| Type        | Method |
| Description | Moves and resizes the window to occupy a given fraction of the screen |
| Parameters |  * unitrect - An `hs.geometry` unit rect, or constructor argument to create one * duration - (optional) The number of seconds to animate the transition. Defaults to the value of `hs.window.animationDuration` |
| Returns |  * The `hs.window` object |
| Notes |  * An example, which would make a window fill the top-left quarter of the screen: `win:moveToUnit'[0,0,50,50]'`

#### [otherWindowsAllScreens](#otherWindowsAllScreens)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:otherWindowsAllScreens() -> list of hs.window objects  |
| Type        | Method |
| Description | Gets every window except this one |
| Parameters |  * None |
| Returns |  * A table containing `hs.window` objects representing all visible windows other than this one |


#### [otherWindowsSameScreen](#otherWindowsSameScreen)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:otherWindowsSameScreen() -> list of hs.window objects  |
| Type        | Method |
| Description | Gets other windows on the same screen |
| Parameters |  * None |
| Returns |  * A table of `hs.window` objects representing the visible windows other than this one that are on the same screen |


#### [raise](#raise)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:raise() -> window  |
| Type        | Method |
| Description | Brings a window to the front of the screen without focussing it |
| Parameters |  * None |
| Returns |  * The `hs.window` object |


#### [role](#role)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:role() -> string  |
| Type        | Method |
| Description | Gets the role of the window |
| Parameters |  * None |
| Returns |  * A string containing the role of the window |


#### [screen](#screen)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:screen() -> hs.screen object  |
| Type        | Method |
| Description | Gets the screen which the window is on |
| Parameters |  * None |
| Returns |  * An `hs.screen` object representing the screen which most contains the window (by area) |


#### [sendToBack](#sendToBack)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:sendToBack() -> hs.window object  |
| Type        | Method |
| Description | Sends the window to the back |
| Parameters |  * None |
| Returns |  * The `hs.window` object |
| Notes |  * Due to the way this method works and OSX limitations, calling this method when you have a lot of randomly overlapping  (as opposed to neatly tiled) windows might be visually jarring, and take a fair amount of time to complete.  So if you don't use orderly layouts, or if you have a lot of windows in general, you're probably better off using  `hs.application:hide()` (or simply `cmd-h`)

#### [setFrame](#setFrame)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:setFrame(rect[, duration]) -> hs.window object  |
| Type        | Method |
| Description | Sets the frame of the window in absolute coordinates |
| Parameters |  * rect - An hs.geometry rect, or constructor argument, describing the frame to be applied to the window * duration - (optional) The number of seconds to animate the transition. Defaults to the value of `hs.window.animationDuration` |
| Returns |  * The `hs.window` object |


#### [setFrameInScreenBounds](#setFrameInScreenBounds)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:setFrameInScreenBounds([rect][, duration]) -> hs.window object  |
| Type        | Method |
| Description | Sets the frame of the window in absolute coordinates, possibly adjusted to ensure it is fully inside the screen |
| Parameters |  * rect - An hs.geometry rect, or constructor argument, describing the frame to be applied to the window; if omitted,   the current window frame will be used * duration - (optional) The number of seconds to animate the transition. Defaults to the value of `hs.window.animationDuration` |
| Returns |  * The `hs.window` object |


#### [setFrameWithWorkarounds](#setFrameWithWorkarounds)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:setFrameWithWorkarounds(rect[, duration]) -> hs.window object  |
| Type        | Method |
| Description | Sets the frame of the window in absolute coordinates, using the additional workarounds described in `hs.window.setFrameCorrectness` |
| Parameters |  * rect - An hs.geometry rect, or constructor argument, describing the frame to be applied to the window * duration - (optional) The number of seconds to animate the transition. Defaults to the value of `hs.window.animationDuration` |
| Returns |  * The `hs.window` object |


#### [setFullScreen](#setFullScreen)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:setFullScreen(fullscreen) -> window  |
| Type        | Method |
| Description | Sets the fullscreen state of the window |
| Parameters |  * fullscreen - A boolean, true if the window should be set fullscreen, false if not |
| Returns |  * The `hs.window` object |


#### [setSize](#setSize)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:setSize(size) -> window  |
| Type        | Method |
| Description | Resizes the window |
| Parameters |  * size - A size-table containing the width and height the window should be resized to |
| Returns |  * The `hs.window` object |


#### [setTopLeft](#setTopLeft)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:setTopLeft(point) -> window  |
| Type        | Method |
| Description | Moves the window to a given point |
| Parameters |  * point - A point-table containing the absolute co-ordinates the window should be moved to |
| Returns |  * The `hs.window` object |


#### [size](#size)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:size() -> size  |
| Type        | Method |
| Description | Gets the size of the window |
| Parameters |  * None |
| Returns |  * A size-table containing the width and height of the window |


#### [snapshot](#snapshot)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:snapshot([keepTransparency]) -> hs.image-object  |
| Type        | Method |
| Description | Returns a snapshot of the window as an `hs.image` object |
| Parameters |  * keepTransparency - optional boolean value indicating if the windows alpha value (transparency) should be maintained in the resulting image or if it should be fully opaque (default). |
| Returns |  * `hs.image` object of the window snapshot or nil if unable to create a snapshot |
| Notes |  * See also function `hs.window.snapshotForID()`

#### [subrole](#subrole)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:subrole() -> string  |
| Type        | Method |
| Description | Gets the subrole of the window |
| Parameters |  * None |
| Returns |  * A string containing the subrole of the window |
| Notes |  * This typically helps to determine if a window is a special kind of window - such as a modal window, or a floating window

#### [title](#title)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:title() -> string  |
| Type        | Method |
| Description | Gets the title of the window |
| Parameters |  * None |
| Returns |  * A string containing the title of the window |


#### [toggleFullScreen](#toggleFullScreen)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:toggleFullScreen() -> hs.window object  |
| Type        | Method |
| Description | Toggles the fullscreen state of the window |
| Parameters |  * None |
| Returns |  * The `hs.window` object |
| Notes |  * Not all windows support being full-screened

#### [toggleZoom](#toggleZoom)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:toggleZoom() -> window  |
| Type        | Method |
| Description | Toggles the zoom state of the window (this is effectively equivalent to clicking the green maximize/fullscreen button at the top left of a window) |
| Parameters |  * None |
| Returns |  * The `hs.window` object |


#### [topLeft](#topLeft)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:topLeft() -> point  |
| Type        | Method |
| Description | Gets the absolute co-ordinates of the top left of the window |
| Parameters |  * None |
| Returns |  * A point-table containing the absolute co-ordinates of the top left corner of the window |


#### [unminimize](#unminimize)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:unminimize() -> window  |
| Type        | Method |
| Description | Un-minimizes the window |
| Parameters |  * None |
| Returns |  * The `hs.window` object |


#### [windowsToEast](#windowsToEast)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:windowsToEast([candidateWindows[, frontmost[, strict]]]) -> list of hs.window objects  |
| Type        | Method |
| Description | Gets all windows to the east of this window |
| Parameters |  * candidateWindows - (optional) a list of candidate windows to consider; if nil, all visible windows   to the east are candidates. * frontmost - (optional) boolean, if true unoccluded windows will be placed before occluded ones in the result list * strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   eastward axis |
| Returns |  * A list of `hs.window` objects representing all windows positioned east (i.e. right) of the window, in ascending order of distance |
| Notes |  * If you don't pass `candidateWindows`, Hammerspoon will query for the list of all visible windows   every time this method is called; this can be slow, and some undesired "windows" could be included   (see the notes for `hs.window.allWindows()`); consider using the equivalent methods in   `hs.window.filter` instead

#### [windowsToNorth](#windowsToNorth)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:windowsToNorth([candidateWindows[, frontmost[, strict]]]) -> list of hs.window objects  |
| Type        | Method |
| Description | Gets all windows to the north of this window |


#### [windowsToSouth](#windowsToSouth)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:windowsToSouth([candidateWindows[, frontmost[, strict]]]) -> list of hs.window objects  |
| Type        | Method |
| Description | Gets all windows to the south of this window |


#### [windowsToWest](#windowsToWest)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:windowsToWest([candidateWindows[, frontmost[, strict]]]) -> list of hs.window objects  |
| Type        | Method |
| Description | Gets all windows to the west of this window |


#### [zoomButtonRect](#zoomButtonRect)
|             |                 |
| ------------|-----------------|
| Signature   | hs.window:zoomButtonRect() -> rect-table or nil  |
| Type        | Method |
| Description | Gets a rect-table for the location of the zoom button (the green button typically found at the top left of a window) |
| Parameters |  * None |
| Returns |  * A rect-table containing the bounding frame of the zoom button, or nil if an error occured |
| Notes |  * The co-ordinates in the rect-table (i.e. the `x` and `y` values) are in absolute co-ordinates, not relative to the window the button is part of, or the screen the window is on * Although not perfect as such, this method can provide a useful way to find a region of the titlebar suitable for simulating mouse click events on, with `hs.eventtap` |
