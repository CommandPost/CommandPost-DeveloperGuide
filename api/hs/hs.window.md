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
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A list of <code>hs.window</code> objects representing all open windows</li></ul>            |
| **Notes**                                            | <ul><li><code>visibleWindows()</code>, <code>orderedWindows()</code>, <code>get()</code>, <code>find()</code>, and several more functions and methods in this and other</li></ul><pre><code>modules make use of this function, so it is important to understand its limitations</code></pre><ul><li>This function queries all applications for their windows every time it is invoked; if you need to call it a lot and</li></ul><p>performance is not acceptable consider using the <code>hs.window.filter</code> module</p><ul><li>This function can only return windows in the current Mission Control Space; if you need to address windows across</li></ul><p>different Spaces you can use the <code>hs.window.filter</code> module</p><ul><li>if <code>Displays have separate Spaces</code> is <em>on</em> (in System Preferences&gt;Mission Control) the current Space is defined</li></ul><pre><code> as the union of all currently visible Spaces</code></pre><ul><li>minimized windows and hidden windows (i.e. belonging to hidden apps, e.g. via cmd-h) are always considered</li></ul><pre><code> to be in the current Space</code></pre><ul><li>This function filters out the desktop "window"; use <code>hs.window.desktop()</code> to address it. (Note however that</li></ul><p><code>hs.application.get'Finder':allWindows()</code> <em>will</em> include the desktop in the returned list)</p><ul><li>Beside the limitations discussed above, this function will return <em>all</em> windows as reported by OSX, including some</li></ul><p>"windows" that one wouldn't expect: for example, every Google Chrome (actual) window has a companion window for its</p><p>status bar; therefore you might get unexpected results  - in the Chrome example, calling <code>hs.window.focusWindowSouth()</code></p><p>from a Chrome window would end up "focusing" its status bar, and therefore the proper window itself, seemingly resulting</p><p>in a no-op. In order to avoid such surprises you can use the <code>hs.window.filter</code> module, and more specifically</p><p>the default windowfilter (<code>hs.window.filter.default</code>) which filters out known cases of not-actual-windows</p><ul><li>Some windows will not be reported by OSX - e.g. things that are on different Spaces, or things that are Full Screen</li></ul>                 |

#### [desktop](#desktop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.desktop() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the desktop "window"                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.window</code> object representing the desktop</li></ul>            |
| **Notes**                                            | <ul><li>The desktop belongs to Finder.app: when Finder is the active application, you can focus the desktop by cycling</li></ul><p>through windows via cmd-`</p><ul><li>The desktop window has no id, a role of <code>AXScrollArea</code> and no subrole</li></ul><ul><li>The desktop is filtered out from <code>hs.window.allWindows()</code> (and downstream uses)</li></ul>                 |

#### [invisibleWindows](#invisiblewindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.invisibleWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all invisible windows                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A list containing <code>hs.window</code> objects representing all windows that are not visible as per <code>hs.window:isVisible()</code></li></ul>            |

#### [minimizedWindows](#minimizedwindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.minimizedWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all minimized windows                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A list containing <code>hs.window</code> objects representing all windows that are minimized as per <code>hs.window:isMinimized()</code></li></ul>            |

#### [orderedWindows](#orderedwindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.orderedWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns all visible windows, ordered from front to back                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A list of <code>hs.window</code> objects representing all visible windows, ordered from front to back</li></ul>            |

#### [setShadows](#setshadows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.setShadows(shadows)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enables/Disables window shadows                                                                                         |
| **Parameters**                                       | <ul><li>shadows - A boolean, true to show window shadows, false to hide window shadows</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>This function uses a private, undocumented OS X API call, so it is not guaranteed to work in any future OS X release</li></ul>                 |

#### [snapshotForID](#snapshotforid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.snapshotForID(ID [, keepTransparency]) -> hs.image-object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a snapshot of the window specified by the ID as an `hs.image` object                                                                                         |
| **Parameters**                                       | <ul><li>ID - Window ID of the window to take a snapshot of.</li></ul><ul><li>keepTransparency - optional boolean value indicating if the windows alpha value (transparency) should be maintained in the resulting image or if it should be fully opaque (default).</li></ul>   |
| **Returns**                                          | <ul><li><code>hs.image</code> object of the window snapshot or nil if unable to create a snapshot</li></ul>            |
| **Notes**                                            | <ul><li>See also method <code>hs.window:snapshot()</code></li></ul><ul><li>Because the window ID cannot always be dynamically determined, this function will allow you to provide the ID of a window that was cached earlier.</li></ul>                 |

#### [visibleWindows](#visiblewindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.visibleWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all visible windows                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A list containing <code>hs.window</code> objects representing all windows that are visible as per <code>hs.window:isVisible()</code></li></ul>            |

### Constructors

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.find(hint) -> hs.window object(s)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Finds windows                                                                                         |
| **Parameters**                                       | <ul><li>hint - search criterion for the desired window(s); it can be:</li></ul><ul><li>an id number as per <code>hs.window:id()</code></li></ul><ul><li>a string pattern that matches (via <code>string.find</code>) the window title as per <code>hs.window:title()</code> (for convenience, the matching will be done on lowercased strings)</li></ul>   |
| **Returns**                                          | <ul><li>one or more hs.window objects that match the supplied search criterion, or <code>nil</code> if none found</li></ul>            |
| **Notes**                                            | <ul><li>for convenience you can call this as <code>hs.window(hint)</code></li></ul><ul><li>see also <code>hs.window.get</code></li></ul><ul><li>for more sophisticated use cases and/or for better performance if you call this a lot, consider using <code>hs.window.filter</code></li></ul>                 |

#### [focusedWindow](#focusedwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.focusedWindow() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns the window that has keyboard/mouse focus                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.window</code> object representing the currently focused window</li></ul>            |

#### [frontmostWindow](#frontmostwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.frontmostWindow() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns the focused window or, if no window has focus, the frontmost one                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.window</code> object representing the frontmost window, or <code>nil</code> if there are no visible windows</li></ul>            |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.get(hint) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Gets a specific window                                                                                         |
| **Parameters**                                       | <ul><li>hint - search criterion for the desired window; it can be:</li></ul><ul><li>an id number as per <code>hs.window:id()</code></li></ul><ul><li>a window title string as per <code>hs.window:title()</code></li></ul>   |
| **Returns**                                          | <ul><li>the first hs.window object that matches the supplied search criterion, or <code>nil</code> if not found</li></ul>            |
| **Notes**                                            | <ul><li>see also <code>hs.window.find</code> and <code>hs.application:getWindow()</code></li></ul>                 |

### Methods

#### [application](#application)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:application() -> app or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `hs.application` object the window belongs to                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.application</code> object representing the application that owns the window, or nil if an error occurred</li></ul>            |

#### [becomeMain](#becomemain)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:becomeMain() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Makes the window the main window of its application                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |
| **Notes**                                            | <ul><li>Make a window become the main window does not transfer focus to the application. See <code>hs.window.focus()</code></li></ul>                 |

#### [centerOnScreen](#centeronscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:centerOnScreen([screen][, ensureInScreenBounds][, duration]) --> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Centers the window on a screen                                                                                         |
| **Parameters**                                       | <ul><li>screen - (optional) An <code>hs.screen</code> object or argument for <code>hs.screen.find</code>; if nil, use the screen the window is currently on</li></ul><ul><li>ensureInScreenBounds - (optional) if <code>true</code>, use <code>setFrameInScreenBounds()</code> to ensure the resulting window frame is fully contained within</li></ul><p>the window's screen</p><ul><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [close](#close)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:close() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Closes the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>True if the operation succeeded, false if not</li></ul>            |

#### [focus](#focus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:focus() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Focuses the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [focusTab](#focustab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:focusTab(index) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Focuses the tab in the window's tab group at index, or the last tab if                                                                                         |
| **Parameters**                                       | <ul><li>index - A number, a 1-based index of a tab to focus</li></ul>   |
| **Returns**                                          | <ul><li>true if the tab was successfully pressed, or false if there was a problem</li></ul>            |

#### [focusWindowEast](#focuswindoweast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:focusWindowEast([candidateWindows[, frontmost[, strict]]]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Focuses the nearest possible window to the east (i.e. right)                                                                                         |
| **Parameters**                                       | <ul><li>candidateWindows - (optional) a list of candidate windows to consider; if nil, all visible windows</li></ul><p>to the east are candidates.</p><ul><li>frontmost - (optional) boolean, if true focuses the nearest window that isn't occluded by any other window</li></ul><ul><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the</li></ul><p>eastward axis</p>   |
| **Returns**                                          | <ul><li><code>true</code> if a window was found and focused, <code>false</code> otherwise; <code>nil</code> if the search couldn't take place</li></ul>            |
| **Notes**                                            | <ul><li>If you don't pass <code>candidateWindows</code>, Hammerspoon will query for the list of all visible windows</li></ul><p>every time this method is called; this can be slow, and some undesired "windows" could be included</p><p>(see the notes for <code>hs.window.allWindows()</code>); consider using the equivalent methods in</p><p><code>hs.window.filter</code> instead</p>                 |

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
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An hs.geometry rect containing the co-ordinates of the top left corner of the window and its width and height</li></ul>            |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:id() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the unique identifier of the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the unique identifier of the window, or nil if an error occurred</li></ul>            |

#### [isFullScreen](#isfullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:isFullScreen() -> bool or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the fullscreen state of the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>True if the window is fullscreen, false if not. Nil if an error occurred</li></ul>            |

#### [isMinimized](#isminimized)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:isMinimized() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the minimized state of the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>True if the window is minimized, otherwise false</li></ul>            |

#### [isStandard](#isstandard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:isStandard() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determines if the window is a standard window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>True if the window is standard, otherwise false</li></ul>            |
| **Notes**                                            | <ul><li>"Standard window" means that this is not an unusual popup window, a modal dialog, a floating window, etc.</li></ul>                 |

#### [isVisible](#isvisible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:isVisible() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determines if a window is visible (i.e. not hidden and not minimized)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if the window is visible, otherwise <code>false</code></li></ul>            |
| **Notes**                                            | <ul><li>This does not mean the user can see the window - it may be obscured by other windows, or it may be off the edge of the screen</li></ul>                 |

#### [maximize](#maximize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:maximize([duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Maximizes the window                                                                                         |
| **Parameters**                                       | <ul><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |
| **Notes**                                            | <ul><li>The window will be resized as large as possible, without obscuring the dock/menu</li></ul>                 |

#### [minimize](#minimize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:minimize() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Minimizes the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |
| **Notes**                                            | <ul><li>This method will always animate per your system settings and is not affected by <code>hs.window.animationDuration</code></li></ul>                 |

#### [move](#move)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:move(rect[, screen][, ensureInScreenBounds][, duration]) --> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window                                                                                         |
| **Parameters**                                       | <ul><li>rect - It can be:</li></ul><ul><li>an <code>hs.geometry</code> point, or argument to construct one; will move the screen by this delta, keeping its size constant; <code>screen</code> is ignored</li></ul><ul><li>an <code>hs.geometry</code> rect, or argument to construct one; will set the window frame to this rect, in absolute coordinates; <code>screen</code> is ignored</li></ul><ul><li>an <code>hs.geometry</code> unit rect, or argument to construct one; will set the window frame to this rect relative to the desired screen;</li></ul><pre><code> if `screen` is nil, use the screen the window is currently on</code></pre><ul><li>screen - (optional) An <code>hs.screen</code> object or argument for <code>hs.screen.find</code>; only valid if <code>rect</code> is a unit rect</li></ul><ul><li>ensureInScreenBounds - (optional) if <code>true</code>, use <code>setFrameInScreenBounds()</code> to ensure the resulting window frame is fully contained within</li></ul><p>the window's screen</p><ul><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [moveOneScreenEast](#moveonescreeneast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:moveOneScreenEast([noResize, ensureInScreenBounds][, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window one screen east (i.e. right)                                                                                         |
| **Parameters**                                       | <ul><li>noResize - (optional) if <code>true</code>, maintain the window's absolute size</li></ul><ul><li>ensureInScreenBounds - (optional) if <code>true</code>, use <code>setFrameInScreenBounds()</code> to ensure the resulting window frame is fully contained within</li></ul><p>the window's screen</p><ul><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

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
| **Parameters**                                       | <ul><li>screen - An <code>hs.screen</code> object, or an argument for <code>hs.screen.find()</code>, representing the screen to move the window to</li></ul><ul><li>noResize - (optional) if <code>true</code>, maintain the window's absolute size</li></ul><ul><li>ensureInScreenBounds - (optional) if <code>true</code>, use <code>setFrameInScreenBounds()</code> to ensure the resulting window frame is fully contained within</li></ul><p>the window's screen</p><ul><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [moveToUnit](#movetounit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:moveToUnit(unitrect[, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves and resizes the window to occupy a given fraction of the screen                                                                                         |
| **Parameters**                                       | <ul><li>unitrect - An <code>hs.geometry</code> unit rect, or constructor argument to create one</li></ul><ul><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |
| **Notes**                                            | <ul><li>An example, which would make a window fill the top-left quarter of the screen: <code>win:moveToUnit'[0,0,50,50]'</code></li></ul>                 |

#### [otherWindowsAllScreens](#otherwindowsallscreens)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:otherWindowsAllScreens() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets every window except this one                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A table containing <code>hs.window</code> objects representing all visible windows other than this one</li></ul>            |

#### [otherWindowsSameScreen](#otherwindowssamescreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:otherWindowsSameScreen() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets other windows on the same screen                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A table of <code>hs.window</code> objects representing the visible windows other than this one that are on the same screen</li></ul>            |

#### [raise](#raise)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:raise() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Brings a window to the front of the screen without focussing it                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [role](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:role() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the role of the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the role of the window</li></ul>            |

#### [screen](#screen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:screen() -> hs.screen object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the screen which the window is on                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.screen</code> object representing the screen which most contains the window (by area)</li></ul>            |

#### [sendToBack](#sendtoback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:sendToBack() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends the window to the back                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |
| **Notes**                                            | <ul><li>Due to the way this method works and OSX limitations, calling this method when you have a lot of randomly overlapping</li></ul><p>(as opposed to neatly tiled) windows might be visually jarring, and take a fair amount of time to complete.</p><p>So if you don't use orderly layouts, or if you have a lot of windows in general, you're probably better off using</p><p><code>hs.application:hide()</code> (or simply <code>cmd-h</code>)</p>                 |

#### [setFrame](#setframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setFrame(rect[, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the frame of the window in absolute coordinates                                                                                         |
| **Parameters**                                       | <ul><li>rect - An hs.geometry rect, or constructor argument, describing the frame to be applied to the window</li></ul><ul><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [setFrameInScreenBounds](#setframeinscreenbounds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setFrameInScreenBounds([rect][, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the frame of the window in absolute coordinates, possibly adjusted to ensure it is fully inside the screen                                                                                         |
| **Parameters**                                       | <ul><li>rect - An hs.geometry rect, or constructor argument, describing the frame to be applied to the window; if omitted,</li></ul><p>the current window frame will be used</p><ul><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [setFrameWithWorkarounds](#setframewithworkarounds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setFrameWithWorkarounds(rect[, duration]) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the frame of the window in absolute coordinates, using the additional workarounds described in `hs.window.setFrameCorrectness`                                                                                         |
| **Parameters**                                       | <ul><li>rect - An hs.geometry rect, or constructor argument, describing the frame to be applied to the window</li></ul><ul><li>duration - (optional) The number of seconds to animate the transition. Defaults to the value of <code>hs.window.animationDuration</code></li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [setFullScreen](#setfullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setFullScreen(fullscreen) -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the fullscreen state of the window                                                                                         |
| **Parameters**                                       | <ul><li>fullscreen - A boolean, true if the window should be set fullscreen, false if not</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [setSize](#setsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setSize(size) -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resizes the window                                                                                         |
| **Parameters**                                       | <ul><li>size - A size-table containing the width and height the window should be resized to</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [setTopLeft](#settopleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:setTopLeft(point) -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the window to a given point                                                                                         |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute co-ordinates the window should be moved to</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [size](#size)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:size() -> size` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the size of the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A size-table containing the width and height of the window</li></ul>            |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:snapshot([keepTransparency]) -> hs.image-object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a snapshot of the window as an `hs.image` object                                                                                         |
| **Parameters**                                       | <ul><li>keepTransparency - optional boolean value indicating if the windows alpha value (transparency) should be maintained in the resulting image or if it should be fully opaque (default).</li></ul>   |
| **Returns**                                          | <ul><li><code>hs.image</code> object of the window snapshot or nil if unable to create a snapshot</li></ul>            |
| **Notes**                                            | <ul><li>See also function <code>hs.window.snapshotForID()</code></li></ul>                 |

#### [subrole](#subrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:subrole() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the subrole of the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the subrole of the window</li></ul>            |
| **Notes**                                            | <ul><li>This typically helps to determine if a window is a special kind of window - such as a modal window, or a floating window</li></ul>                 |

#### [tabCount](#tabcount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:tabCount() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the number of tabs in the window has, or nil if the window doesn't have tabs.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the number of tabs, or nil if an error occurred</li></ul>            |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:title() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the title of the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the title of the window</li></ul>            |

#### [toggleFullScreen](#togglefullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:toggleFullScreen() -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggles the fullscreen state of the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |
| **Notes**                                            | <ul><li>Not all windows support being full-screened</li></ul>                 |

#### [toggleZoom](#togglezoom)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:toggleZoom() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggles the zoom state of the window (this is effectively equivalent to clicking the green maximize/fullscreen button at the top left of a window)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [topLeft](#topleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:topLeft() -> point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the absolute co-ordinates of the top left of the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A point-table containing the absolute co-ordinates of the top left corner of the window</li></ul>            |

#### [unminimize](#unminimize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:unminimize() -> window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Un-minimizes the window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.window</code> object</li></ul>            |

#### [windowsToEast](#windowstoeast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window:windowsToEast([candidateWindows[, frontmost[, strict]]]) -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets all windows to the east of this window                                                                                         |
| **Parameters**                                       | <ul><li>candidateWindows - (optional) a list of candidate windows to consider; if nil, all visible windows</li></ul><p>to the east are candidates.</p><ul><li>frontmost - (optional) boolean, if true unoccluded windows will be placed before occluded ones in the result list</li></ul><ul><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the</li></ul><p>eastward axis</p>   |
| **Returns**                                          | <ul><li>A list of <code>hs.window</code> objects representing all windows positioned east (i.e. right) of the window, in ascending order of distance</li></ul>            |
| **Notes**                                            | <ul><li>If you don't pass <code>candidateWindows</code>, Hammerspoon will query for the list of all visible windows</li></ul><p>every time this method is called; this can be slow, and some undesired "windows" could be included</p><p>(see the notes for <code>hs.window.allWindows()</code>); consider using the equivalent methods in</p><p><code>hs.window.filter</code> instead</p>                 |

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
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A rect-table containing the bounding frame of the zoom button, or nil if an error occured</li></ul>            |
| **Notes**                                            | <ul><li>The co-ordinates in the rect-table (i.e. the <code>x</code> and <code>y</code> values) are in absolute co-ordinates, not relative to the window the button is part of, or the screen the window is on</li></ul><ul><li>Although not perfect as such, this method can provide a useful way to find a region of the titlebar suitable for simulating mouse click events on, with <code>hs.eventtap</code></li></ul>                 |

