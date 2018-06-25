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
 * [animationDuration](#animationduration)
 * [setFrameCorrectness](#setframecorrectness)
* Functions - API calls offered directly by the extension
 * [allWindows](#allwindows)
 * [desktop](#desktop)
 * [invisibleWindows](#invisiblewindows)
 * [minimizedWindows](#minimizedwindows)
 * [orderedWindows](#orderedwindows)
 * [setShadows](#setshadows)
 * [snapshotForID](#snapshotforid)
 * [visibleWindows](#visiblewindows)
* Constructors - API calls which return an object, typically one that offers API methods
 * [find](#find)
 * [focusedWindow](#focusedwindow)
 * [frontmostWindow](#frontmostwindow)
 * [get](#get)
* Methods - API calls which can only be made on an object returned by a constructor
 * [application](#application)
 * [becomeMain](#becomemain)
 * [centerOnScreen](#centeronscreen)
 * [close](#close)
 * [focus](#focus)
 * [focusTab](#focustab)
 * [focusWindowEast](#focuswindoweast)
 * [focusWindowNorth](#focuswindownorth)
 * [focusWindowSouth](#focuswindowsouth)
 * [focusWindowWest](#focuswindowwest)
 * [frame](#frame)
 * [id](#id)
 * [isFullScreen](#isfullscreen)
 * [isMinimized](#isminimized)
 * [isStandard](#isstandard)
 * [isVisible](#isvisible)
 * [maximize](#maximize)
 * [minimize](#minimize)
 * [move](#move)
 * [moveOneScreenEast](#moveonescreeneast)
 * [moveOneScreenNorth](#moveonescreennorth)
 * [moveOneScreenSouth](#moveonescreensouth)
 * [moveOneScreenWest](#moveonescreenwest)
 * [moveToScreen](#movetoscreen)
 * [moveToUnit](#movetounit)
 * [otherWindowsAllScreens](#otherwindowsallscreens)
 * [otherWindowsSameScreen](#otherwindowssamescreen)
 * [raise](#raise)
 * [role](#role)
 * [screen](#screen)
 * [sendToBack](#sendtoback)
 * [setFrame](#setframe)
 * [setFrameInScreenBounds](#setframeinscreenbounds)
 * [setFrameWithWorkarounds](#setframewithworkarounds)
 * [setFullScreen](#setfullscreen)
 * [setSize](#setsize)
 * [setTopLeft](#settopleft)
 * [size](#size)
 * [snapshot](#snapshot)
 * [subrole](#subrole)
 * [tabCount](#tabcount)
 * [title](#title)
 * [toggleFullScreen](#togglefullscreen)
 * [toggleZoom](#togglezoom)
 * [topLeft](#topleft)
 * [unminimize](#unminimize)
 * [windowsToEast](#windowstoeast)
 * [windowsToNorth](#windowstonorth)
 * [windowsToSouth](#windowstosouth)
 * [windowsToWest](#windowstowest)
 * [zoomButtonRect](#zoombuttonrect)

## API Documentation

### Variables

#### [animationDuration](#animationduration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.animationDuration (number)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The default duration for animations, in seconds. Initial value is 0.2; set to 0 to disable animations.                                                                                         |

#### [setFrameCorrectness](#setframecorrectness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.setFrameCorrectness` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Using `hs.window:setFrame()` in some cases does not work as expected: namely, the bottom (or Dock) edge, and edges between screens, might                                                                                         |

### Functions

#### [allWindows](#allwindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.allWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns all windows                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A list of <code>hs.window</code> objects representing all open windows</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li><code>visibleWindows()</code>, <code>orderedWindows()</code>, <code>get()</code>, <code>find()</code>, and several more functions and methods in this and other    modules make use of this function, so it is important to understand its limitations * This function queries all applications for their windows every time it is invoked; if you need to call it a lot and   performance is not acceptable consider using the <code>hs.window.filter</code> module * This function can only return windows in the current Mission Control Space; if you need to address windows across   different Spaces you can use the <code>hs.window.filter</code> module   - if <code>Displays have separate Spaces</code> is <em>on</em> (in System Preferences&gt;Mission Control) the current Space is defined     as the union of all currently visible Spaces   - minimized windows and hidden windows (i.e. belonging to hidden apps, e.g. via cmd-h) are always considered     to be in the current Space * This function filters out the desktop "window"; use <code>hs.window.desktop()</code> to address it. (Note however that   <code>hs.application.get'Finder':allWindows()</code> <em>will</em> include the desktop in the returned list) * Beside the limitations discussed above, this function will return <em>all</em> windows as reported by OSX, including some   "windows" that one wouldn't expect: for example, every Google Chrome (actual) window has a companion window for its   status bar; therefore you might get unexpected results  - in the Chrome example, calling <code>hs.window.focusWindowSouth()</code>   from a Chrome window would end up "focusing" its status bar, and therefore the proper window itself, seemingly resulting   in a no-op. In order to avoid such surprises you can use the <code>hs.window.filter</code> module, and more specifically   the default windowfilter (<code>hs.window.filter.default</code>) which filters out known cases of not-actual-windows * Some windows will not be reported by OSX - e.g. things that are on different Spaces, or things that are Full Screen</li><br /></ul>                                             |

#### [desktop](#desktop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.desktop() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the desktop "window"                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.window</code> object representing the desktop</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The desktop belongs to Finder.app: when Finder is the active application, you can focus the desktop by cycling   through windows via cmd-<code>* The desktop window has no id, a role of</code>AXScrollArea<code>and no subrole * The desktop is filtered out from</code>hs.window.allWindows()` (and downstream uses)</li><br /></ul>                                             |

#### [invisibleWindows](#invisiblewindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.invisibleWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all invisible windows                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A list containing <code>hs.window</code> objects representing all windows that are not visible as per <code>hs.window:isVisible()</code></li><br /></ul>                                           |

#### [minimizedWindows](#minimizedwindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.minimizedWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all minimized windows                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A list containing <code>hs.window</code> objects representing all windows that are minimized as per <code>hs.window:isMinimized()</code></li><br /></ul>                                           |

#### [orderedWindows](#orderedwindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.orderedWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns all visible windows, ordered from front to back                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A list of <code>hs.window</code> objects representing all visible windows, ordered from front to back</li><br /></ul>                                           |

#### [setShadows](#setshadows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.setShadows(shadows)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enables/Disables window shadows                                                                                         |
| **Parameters**                                       | <ul><br /><li>shadows - A boolean, true to show window shadows, false to hide window shadows</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This function uses a private, undocumented OS X API call, so it is not guaranteed to work in any future OS X release</li><br /></ul>                                             |

#### [snapshotForID](#snapshotforid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.snapshotForID(ID [, keepTransparency]) -> hs.image-object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a snapshot of the window specified by the ID as an `hs.image` object                                                                                         |
| **Parameters**                                       | <ul><br /><li>ID - Window ID of the window to take a snapshot of. * keepTransparency - optional boolean value indicating if the windows alpha value (transparency) should be maintained in the resulting image or if it should be fully opaque (default).</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>hs.image</code> object of the window snapshot or nil if unable to create a snapshot</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>See also method <code>hs.window:snapshot()</code> * Because the window ID cannot always be dynamically determined, this function will allow you to provide the ID of a window that was cached earlier.</li><br /></ul>                                             |

#### [visibleWindows](#visiblewindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.visibleWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all visible windows                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A list containing <code>hs.window</code> objects representing all windows that are visible as per <code>hs.window:isVisible()</code></li><br /></ul>                                           |

### Constructors

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.find(hint) -> hs.window object(s)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Finds windows                                                                                         |
| **Parameters**                                       | <ul><br /><li>hint - search criterion for the desired window(s); it can be:   - an id number as per <code>hs.window:id()</code>   - a string pattern that matches (via <code>string.find</code>) the window title as per <code>hs.window:title()</code> (for convenience, the matching will be done on lowercased strings)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>one or more hs.window objects that match the supplied search criterion, or <code>nil</code> if none found</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>for convenience you can call this as <code>hs.window(hint)</code> * see also <code>hs.window.get</code> * for more sophisticated use cases and/or for better performance if you call this a lot, consider using <code>hs.window.filter</code></li><br /></ul>                                             |

#### [focusedWindow](#focusedwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.focusedWindow() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns the window that has keyboard/mouse focus                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.window</code> object representing the currently focused window</li><br /></ul>                                           |

#### [frontmostWindow](#frontmostwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.frontmostWindow() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns the focused window or, if no window has focus, the frontmost one                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.window</code> object representing the frontmost window, or <code>nil</code> if there are no visible windows</li><br /></ul>                                           |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.get(hint) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Gets a specific window                                                                                         |
| **Parameters**                                       | <ul><br /><li>hint - search criterion for the desired window; it can be:   - an id number as per <code>hs.window:id()</code>   - a window title string as per <code>hs.window:title()</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the first hs.window object that matches the supplied search criterion, or <code>nil</code> if not found</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>see also <code>hs.window.find</code> and <code>hs.application:getWindow()</code></li><br /></ul>                                             |

### Methods

#### [application](#application)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:application() -> app or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `hs.application` object the window belongs to                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.application</code> object representing the application that owns the window, or nil if an error occurred</li><br /></ul>                                           |

#### [becomeMain](#becomemain)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:becomeMain() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Makes the window the main window of its application                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Make a window become the main window does not transfer focus to the application. See <code>hs.window.focus()</code></li><br /></ul>                                             |

#### [centerOnScreen](#centeronscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:centerOnScreen([screen][, ensureInScreenBounds][, duration]) --> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Centers the window on a screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>screen - (optional) An <code>hs.screen</code> object or argument for <code>hs.screen.find</code>; if nil, use the screen the window is currently on * ensureInScreenBounds - (optional) if <code>true</code>, use <code>setFrameInScreenBounds()</code> to ensure the resulting window frame is fully contained within   the window's screen * duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [close](#close)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:close() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Closes the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>True if the operation succeeded, false if not</li><br /></ul>                                           |

#### [focus](#focus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:focus() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Focuses the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [focusTab](#focustab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:focusTab(index) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Focuses the tab in the window's tab group at index, or the last tab if                                                                                         |
| **Parameters**                                       | <ul><br /><li>index - A number, a 1-based index of a tab to focus</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>true if the tab was successfully pressed, or false if there was a problem</li><br /></ul>                                           |

#### [focusWindowEast](#focuswindoweast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:focusWindowEast([candidateWindows[, frontmost[, strict]]]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Focuses the nearest possible window to the east (i.e. right)                                                                                         |
| **Parameters**                                       | <ul><br /><li>candidateWindows - (optional) a list of candidate windows to consider; if nil, all visible windows   to the east are candidates. * frontmost - (optional) boolean, if true focuses the nearest window that isn't occluded by any other window * strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   eastward axis</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if a window was found and focused, <code>false</code> otherwise; <code>nil</code> if the search couldn't take place</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If you don't pass <code>candidateWindows</code>, Hammerspoon will query for the list of all visible windows   every time this method is called; this can be slow, and some undesired "windows" could be included   (see the notes for <code>hs.window.allWindows()</code>); consider using the equivalent methods in   <code>hs.window.filter</code> instead</li><br /></ul>                                             |

#### [focusWindowNorth](#focuswindownorth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:focusWindowNorth([candidateWindows[, frontmost[, strict]]]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Focuses the nearest possible window to the north (i.e. up)                                                                                         |

#### [focusWindowSouth](#focuswindowsouth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:focusWindowSouth([candidateWindows[, frontmost[, strict]]]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Focuses the nearest possible window to the south (i.e. down)                                                                                         |

#### [focusWindowWest](#focuswindowwest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:focusWindowWest([candidateWindows[, frontmost[, strict]]]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Focuses the nearest possible window to the west (i.e. right)                                                                                         |

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:frame() -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the frame of the window in absolute coordinates                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An hs.geometry rect containing the co-ordinates of the top left corner of the window and its width and height</li><br /></ul>                                           |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:id() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the unique identifier of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A number containing the unique identifier of the window, or nil if an error occurred</li><br /></ul>                                           |

#### [isFullScreen](#isfullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:isFullScreen() -> bool or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the fullscreen state of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>True if the window is fullscreen, false if not. Nil if an error occurred</li><br /></ul>                                           |

#### [isMinimized](#isminimized)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:isMinimized() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the minimized state of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>True if the window is minimized, otherwise false</li><br /></ul>                                           |

#### [isStandard](#isstandard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:isStandard() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determines if the window is a standard window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>True if the window is standard, otherwise false</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>"Standard window" means that this is not an unusual popup window, a modal dialog, a floating window, etc.</li><br /></ul>                                             |

#### [isVisible](#isvisible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:isVisible() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determines if a window is visible (i.e. not hidden and not minimized)                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the window is visible, otherwise <code>false</code></li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This does not mean the user can see the window - it may be obscured by other windows, or it may be off the edge of the screen</li><br /></ul>                                             |

#### [maximize](#maximize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:maximize([duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Maximizes the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The window will be resized as large as possible, without obscuring the dock/menu</li><br /></ul>                                             |

#### [minimize](#minimize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:minimize() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Minimizes the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This method will always animate per your system settings and is not affected by <code>hs.window.animationDuration</code></li><br /></ul>                                             |

#### [move](#move)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:move(rect[, screen][, ensureInScreenBounds][, duration]) --> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>rect - It can be:   - an <code>hs.geometry</code> point, or argument to construct one; will move the screen by this delta, keeping its size constant; <code>screen</code> is ignored   - an <code>hs.geometry</code> rect, or argument to construct one; will set the window frame to this rect, in absolute coordinates; <code>screen</code> is ignored   - an <code>hs.geometry</code> unit rect, or argument to construct one; will set the window frame to this rect relative to the desired screen;     if <code>screen</code> is nil, use the screen the window is currently on * screen - (optional) An <code>hs.screen</code> object or argument for <code>hs.screen.find</code>; only valid if <code>rect</code> is a unit rect * ensureInScreenBounds - (optional) if <code>true</code>, use <code>setFrameInScreenBounds()</code> to ensure the resulting window frame is fully contained within   the window's screen * duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [moveOneScreenEast](#moveonescreeneast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:moveOneScreenEast([noResize, ensureInScreenBounds][, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window one screen east (i.e. right)                                                                                         |
| **Parameters**                                       | <ul><br /><li>noResize - (optional) if <code>true</code>, maintain the window's absolute size * ensureInScreenBounds - (optional) if <code>true</code>, use <code>setFrameInScreenBounds()</code> to ensure the resulting window frame is fully contained within   the window's screen * duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [moveOneScreenNorth](#moveonescreennorth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:moveOneScreenNorth([noResize, ensureInScreenBounds][, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window one screen north (i.e. up)                                                                                         |

#### [moveOneScreenSouth](#moveonescreensouth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:moveOneScreenSouth([noResize, ensureInScreenBounds][, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window one screen south (i.e. down)                                                                                         |

#### [moveOneScreenWest](#moveonescreenwest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:moveOneScreenWest([noResize, ensureInScreenBounds][, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window one screen west (i.e. left)                                                                                         |

#### [moveToScreen](#movetoscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:moveToScreen(screen[, noResize, ensureInScreenBounds][, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window to a given screen, retaining its relative position and size                                                                                         |
| **Parameters**                                       | <ul><br /><li>screen - An <code>hs.screen</code> object, or an argument for <code>hs.screen.find()</code>, representing the screen to move the window to * noResize - (optional) if <code>true</code>, maintain the window's absolute size * ensureInScreenBounds - (optional) if <code>true</code>, use <code>setFrameInScreenBounds()</code> to ensure the resulting window frame is fully contained within   the window's screen * duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [moveToUnit](#movetounit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:moveToUnit(unitrect[, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves and resizes the window to occupy a given fraction of the screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>unitrect - An <code>hs.geometry</code> unit rect, or constructor argument to create one * duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>An example, which would make a window fill the top-left quarter of the screen: <code>win:moveToUnit'[0,0,50,50]'</code></li><br /></ul>                                             |

#### [otherWindowsAllScreens](#otherwindowsallscreens)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:otherWindowsAllScreens() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets every window except this one                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing <code>hs.window</code> objects representing all visible windows other than this one</li><br /></ul>                                           |

#### [otherWindowsSameScreen](#otherwindowssamescreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:otherWindowsSameScreen() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets other windows on the same screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table of <code>hs.window</code> objects representing the visible windows other than this one that are on the same screen</li><br /></ul>                                           |

#### [raise](#raise)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:raise() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Brings a window to the front of the screen without focussing it                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [role](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:role() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the role of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string containing the role of the window</li><br /></ul>                                           |

#### [screen](#screen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:screen() -> hs.screen object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the screen which the window is on                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object representing the screen which most contains the window (by area)</li><br /></ul>                                           |

#### [sendToBack](#sendtoback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:sendToBack() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends the window to the back                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Due to the way this method works and OSX limitations, calling this method when you have a lot of randomly overlapping  (as opposed to neatly tiled) windows might be visually jarring, and take a fair amount of time to complete.  So if you don't use orderly layouts, or if you have a lot of windows in general, you're probably better off using  <code>hs.application:hide()</code> (or simply <code>cmd-h</code>)</li><br /></ul>                                             |

#### [setFrame](#setframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setFrame(rect[, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the frame of the window in absolute coordinates                                                                                         |
| **Parameters**                                       | <ul><br /><li>rect - An hs.geometry rect, or constructor argument, describing the frame to be applied to the window * duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [setFrameInScreenBounds](#setframeinscreenbounds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setFrameInScreenBounds([rect][, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the frame of the window in absolute coordinates, possibly adjusted to ensure it is fully inside the screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>rect - An hs.geometry rect, or constructor argument, describing the frame to be applied to the window; if omitted,   the current window frame will be used * duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [setFrameWithWorkarounds](#setframewithworkarounds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setFrameWithWorkarounds(rect[, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the frame of the window in absolute coordinates, using the additional workarounds described in `hs.window.setFrameCorrectness`                                                                                         |
| **Parameters**                                       | <ul><br /><li>rect - An hs.geometry rect, or constructor argument, describing the frame to be applied to the window * duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [setFullScreen](#setfullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setFullScreen(fullscreen) -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the fullscreen state of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>fullscreen - A boolean, true if the window should be set fullscreen, false if not</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [setSize](#setsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setSize(size) -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resizes the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>size - A size-table containing the width and height the window should be resized to</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [setTopLeft](#settopleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setTopLeft(point) -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window to a given point                                                                                         |
| **Parameters**                                       | <ul><br /><li>point - A point-table containing the absolute co-ordinates the window should be moved to</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [size](#size)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:size() -> size` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the size of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A size-table containing the width and height of the window</li><br /></ul>                                           |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:snapshot([keepTransparency]) -> hs.image-object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a snapshot of the window as an `hs.image` object                                                                                         |
| **Parameters**                                       | <ul><br /><li>keepTransparency - optional boolean value indicating if the windows alpha value (transparency) should be maintained in the resulting image or if it should be fully opaque (default).</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>hs.image</code> object of the window snapshot or nil if unable to create a snapshot</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>See also function <code>hs.window.snapshotForID()</code></li><br /></ul>                                             |

#### [subrole](#subrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:subrole() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the subrole of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string containing the subrole of the window</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This typically helps to determine if a window is a special kind of window - such as a modal window, or a floating window</li><br /></ul>                                             |

#### [tabCount](#tabcount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:tabCount() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the number of tabs in the window has, or nil if the window doesn't have tabs.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A number containing the number of tabs, or nil if an error occurred</li><br /></ul>                                           |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:title() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the title of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string containing the title of the window</li><br /></ul>                                           |

#### [toggleFullScreen](#togglefullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:toggleFullScreen() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggles the fullscreen state of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Not all windows support being full-screened</li><br /></ul>                                             |

#### [toggleZoom](#togglezoom)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:toggleZoom() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggles the zoom state of the window (this is effectively equivalent to clicking the green maximize/fullscreen button at the top left of a window)                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [topLeft](#topleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:topLeft() -> point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the absolute co-ordinates of the top left of the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A point-table containing the absolute co-ordinates of the top left corner of the window</li><br /></ul>                                           |

#### [unminimize](#unminimize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:unminimize() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Un-minimizes the window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.window</code> object</li><br /></ul>                                           |

#### [windowsToEast](#windowstoeast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:windowsToEast([candidateWindows[, frontmost[, strict]]]) -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets all windows to the east of this window                                                                                         |
| **Parameters**                                       | <ul><br /><li>candidateWindows - (optional) a list of candidate windows to consider; if nil, all visible windows   to the east are candidates. * frontmost - (optional) boolean, if true unoccluded windows will be placed before occluded ones in the result list * strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   eastward axis</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A list of <code>hs.window</code> objects representing all windows positioned east (i.e. right) of the window, in ascending order of distance</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If you don't pass <code>candidateWindows</code>, Hammerspoon will query for the list of all visible windows   every time this method is called; this can be slow, and some undesired "windows" could be included   (see the notes for <code>hs.window.allWindows()</code>); consider using the equivalent methods in   <code>hs.window.filter</code> instead</li><br /></ul>                                             |

#### [windowsToNorth](#windowstonorth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:windowsToNorth([candidateWindows[, frontmost[, strict]]]) -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets all windows to the north of this window                                                                                         |

#### [windowsToSouth](#windowstosouth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:windowsToSouth([candidateWindows[, frontmost[, strict]]]) -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets all windows to the south of this window                                                                                         |

#### [windowsToWest](#windowstowest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:windowsToWest([candidateWindows[, frontmost[, strict]]]) -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets all windows to the west of this window                                                                                         |

#### [zoomButtonRect](#zoombuttonrect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:zoomButtonRect() -> rect-table or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a rect-table for the location of the zoom button (the green button typically found at the top left of a window)                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A rect-table containing the bounding frame of the zoom button, or nil if an error occured</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The co-ordinates in the rect-table (i.e. the <code>x</code> and <code>y</code> values) are in absolute co-ordinates, not relative to the window the button is part of, or the screen the window is on * Although not perfect as such, this method can provide a useful way to find a region of the titlebar suitable for simulating mouse click events on, with <code>hs.eventtap</code></li><br /></ul>                                             |

