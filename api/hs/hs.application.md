# [docs](index.md) » hs.application
---

Manipulate running applications

## Submodules
 * [hs.application.watcher](hs.application.watcher.md)

## API Overview
* Variables - Configurable values
 * [menuGlyphs](#menuglyphs)
* Functions - API calls offered directly by the extension
 * [applicationForPID](#applicationforpid)
 * [applicationsForBundleID](#applicationsforbundleid)
 * [enableSpotlightForNameSearches](#enablespotlightfornamesearches)
 * [frontmostApplication](#frontmostapplication)
 * [infoForBundleID](#infoforbundleid)
 * [infoForBundlePath](#infoforbundlepath)
 * [launchOrFocus](#launchorfocus)
 * [launchOrFocusByBundleID](#launchorfocusbybundleid)
 * [nameForBundleID](#nameforbundleid)
 * [pathForBundleID](#pathforbundleid)
 * [runningApplications](#runningapplications)
* Constructors - API calls which return an object, typically one that offers API methods
 * [find](#find)
 * [get](#get)
 * [open](#open)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activate](#activate)
 * [allWindows](#allwindows)
 * [bundleID](#bundleid)
 * [findMenuItem](#findmenuitem)
 * [findWindow](#findwindow)
 * [focusedWindow](#focusedwindow)
 * [getMenuItems](#getmenuitems)
 * [getWindow](#getwindow)
 * [hide](#hide)
 * [isFrontmost](#isfrontmost)
 * [isHidden](#ishidden)
 * [isRunning](#isrunning)
 * [kill](#kill)
 * [kill9](#kill9)
 * [kind](#kind)
 * [mainWindow](#mainwindow)
 * [name](#name)
 * [path](#path)
 * [pid](#pid)
 * [selectMenuItem](#selectmenuitem)
 * [title](#title)
 * [unhide](#unhide)
 * [visibleWindows](#visiblewindows)

## API Documentation

### Variables

#### [menuGlyphs](#menuglyphs)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.menuGlyphs` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | A table containing UTF8 representations of the defined key glyphs used in Menus for keybaord shortcuts which are presented pictorially rather than as text (arrow keys, return key, etc.)                                                                                         |
| **Notes**                                            | <ul><li>a `__tostring` metamethod is provided for this table so you can view its current contents by typing `hs.application.menuGlyphs` into the Hammerspoon console.</li><li>This table is provided as a variable so that you can change any representation if you feel you know of a better or more appropriate one for you usage at runtime.</li></ul>                |

### Functions

#### [applicationForPID](#applicationforpid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.applicationForPID(pid) -> hs.application object or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the running app for the given pid, if it exists.                                                                                         |
| **Parameters**                                       | <ul><li>pid - a UNIX process id (i.e. a number)</li></ul> |
| **Returns**                                          | <ul><li>An hs.application object if one can be found, otherwise nil</li></ul>          |

#### [applicationsForBundleID](#applicationsforbundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.applicationsForBundleID(bundleID) -> list of hs.application objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns any running apps that have the given bundleID.                                                                                         |
| **Parameters**                                       | <ul><li>bundleID - An OSX application bundle indentifier</li></ul> |
| **Returns**                                          | <ul><li>A table of zero or more hs.application objects that match the given identifier</li></ul>          |

#### [enableSpotlightForNameSearches](#enablespotlightfornamesearches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.enableSpotlightForNameSearches([state]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get or set whether Spotlight should be used to find alternate names for applications.                                                                                         |
| **Parameters**                                       | <ul><li>`state` - an optional boolean specifying whether or not Spotlight should be used to try and determine alternate application names for `hs.application.find` and similar functions.</li></ul> |
| **Returns**                                          | <ul><li>the current, possibly changed, state</li></ul>          |
| **Notes**                                            | <ul><li>This setting is persistent across reloading and restarting Hammerspoon.</li><li>If this was set to true and you set it to true again, it will purge the alternate name map and rebuild it from scratch.</li><li>You can disable Spotlight alternate name mapping by setting this value to false or nil. If you set this to false, then the notifications indicating that more results might be possible if Spotlight is enabled will be suppressed.</li></ul>                |

#### [frontmostApplication](#frontmostapplication)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.frontmostApplication() -> hs.application object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the application object for the frontmost (active) application.  This is the application which currently receives input events.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An hs.application object</li></ul>          |

#### [infoForBundleID](#infoforbundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.infoForBundleID(bundleID) -> table or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the metadata of an application from its bundle identifier                                                                                         |
| **Parameters**                                       | <ul><li>bundleID - A string containing an application bundle identifier (e.g. "com.apple.Safari")</li></ul> |
| **Returns**                                          | <ul><li>A table containing information about the application, or nil if the bundle identifier could not be located</li></ul>          |

#### [infoForBundlePath](#infoforbundlepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.infoForBundlePath(bundlePath) -> table or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the metadata of an application from its path on disk                                                                                         |
| **Parameters**                                       | <ul><li>bundlePath - A string containing the path to an application bundle (e.g. "/Applications/Safari.app")</li></ul> |
| **Returns**                                          | <ul><li>A table containing information about the application, or nil if the bundle could not be located</li></ul>          |

#### [launchOrFocus](#launchorfocus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.launchOrFocus(name) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Launches the app with the given name, or activates it if it's already running                                                                                         |
| **Parameters**                                       | <ul><li>name - A string containing the name of the application to either launch or focus. This can also be the full path to an application (including the `.app` suffix) if you need to uniquely distinguish between applications in different locations that share the same name</li></ul> |
| **Returns**                                          | <ul><li>True if the application was either launched or focused, otherwise false (e.g. if the application doesn't exist)</li></ul>          |
| **Notes**                                            | <ul><li>The name parameter should match the name of the application on disk, e.g. "IntelliJ IDEA", rather than "IntelliJ"</li></ul>                |

#### [launchOrFocusByBundleID](#launchorfocusbybundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.launchOrFocusByBundleID(bundleID) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Launches the app with the given bundle ID, or activates it if it's already running                                                                                         |
| **Parameters**                                       | <ul><li>bundleID - A string containing the bundle ID of the application to either launch or focus.</li></ul> |
| **Returns**                                          | <ul><li>True if the application was either launched or focused, otherwise false (e.g. if the application doesn't exist)</li></ul>          |
| **Notes**                                            | <ul><li>Bundle identifiers typically take the form of `com.company.ApplicationName`</li></ul>                |

#### [nameForBundleID](#nameforbundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.nameForBundleID(bundleID) -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of an application from its bundle identifier                                                                                         |
| **Parameters**                                       | <ul><li>bundleID - A string containing an application bundle identifier (e.g. "com.apple.Safari")</li></ul> |
| **Returns**                                          | <ul><li>A string containing the application name, or nil if the bundle identifier could not be located</li></ul>          |

#### [pathForBundleID](#pathforbundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.pathForBundleID(bundleID) -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the filesystem path of an application from its bundle identifier                                                                                         |
| **Parameters**                                       | <ul><li>bundleID - A string containing an application bundle identifier (e.g. "com.apple.Safari")</li></ul> |
| **Returns**                                          | <ul><li>A string containing the app bundle's filesystem path, or nil if the bundle identifier could not be located</li></ul>          |

#### [runningApplications](#runningapplications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.runningApplications() -> list of hs.application objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns all running apps.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing zero or more hs.application objects currently running on the system</li></ul>          |

### Constructors

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.find(hint) -> hs.application object(s)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Finds running applications                                                                                         |
| **Parameters**                                       | <ul><li>hint - search criterion for the desired application(s); it can be:</li><li>   - a pid number as per `hs.application:pid()`</li><li>   - a bundle ID string as per `hs.application:bundleID()`</li><li>   - a string pattern that matches (via `string.find`) the application name as per `hs.application:name()` (for convenience, the matching will be done on lowercased strings)</li><li>   - a string pattern that matches (via `string.find`) the application's window title per `hs.window:title()` (for convenience, the matching will be done on lowercased strings)</li></ul> |
| **Returns**                                          | <ul><li>one or more hs.application objects for running applications that match the supplied search criterion, or `nil` if none found</li></ul>          |
| **Notes**                                            | <ul><li>If multiple results are found, this function will return multiple values. See [https://www.lua.org/pil/5.1.html](https://www.lua.org/pil/5.1.html) for more information on how to work with this</li><li>for convenience you can call this as `hs.application(hint)`</li><li>use this function when you don't know the exact name of an application you're interested in, i.e.</li><li>   from the console: `hs.application'term' --> hs.application: iTerm2 (0x61000025fb88)  hs.application: Terminal (0x618000447588)`.</li><li>   But be careful when using it in your `init.lua`: `terminal=hs.application'term'` will assign either "Terminal" or "iTerm2" arbitrarily (or even,</li><li>   if neither are running, any other app with a window that happens to have "term" in its title); to make sure you get the right app in your scripts,</li><li>   use `hs.application.get` with the exact name: `terminal=hs.application.get'Terminal' --> "Terminal" app, or nil if it's not running`</li></ul>                |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.get(hint) -> hs.application object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Gets a running application                                                                                         |
| **Parameters**                                       | <ul><li>hint - search criterion for the desired application; it can be:</li><li>   - a pid number as per `hs.application:pid()`</li><li>   - a bundle ID string as per `hs.application:bundleID()`</li><li>   - an application name string as per `hs.application:name()`</li></ul> |
| **Returns**                                          | <ul><li>an hs.application object for a running application that matches the supplied search criterion, or `nil` if not found</li></ul>          |
| **Notes**                                            | <ul><li>see also `hs.application.find`</li></ul>                |

#### [open](#open)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.open(app[, wait, [waitForFirstWindow]]) -> hs.application object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Launches an application, or activates it if it's already running                                                                                         |
| **Parameters**                                       | <ul><li>app - a string describing the application to open; it can be:</li><li>   - the application's name as per `hs.application:name()`</li><li>   - the full path to an application on disk (including the `.app` suffix)</li><li>   - the application's bundle ID as per `hs.application:bundleID()`</li><li>wait - (optional) the maximum number of seconds to wait for the app to be launched, if not already running; if omitted, defaults to 0;</li><li>  if the app takes longer than this to launch, this function will return `nil`, but the app will still launch</li><li>waitForFirstWindow - (optional) if `true`, additionally wait until the app has spawned its first window (which usually takes a bit longer)</li></ul> |
| **Returns**                                          | <ul><li>the `hs.application` object for the launched or activated application; `nil` if not found</li></ul>          |
| **Notes**                                            | <ul><li>the `wait` parameter will *block all Hammerspoon activity* in order to return the application object "synchronously"; only use it if you</li><li>   a) have no time-critical event processing happening elsewhere in your `init.lua` and b) need to act on the application object, or on</li><li>   its window(s), right away</li><li>when launching a "windowless" app (background daemon, menulet, etc.) make sure to omit `waitForFirstWindow`</li></ul>                |

### Methods

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:activate([allWindows]) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Tries to activate the app (make its key window focused) and returns whether it succeeded; if allWindows is true, all windows of the application are brought forward as well.                                                                                         |
| **Parameters**                                       | <ul><li>allWindows - If true, all windows of the application will be brought to the front. Otherwise, only the application's key window will. Defaults to false.</li></ul> |
| **Returns**                                          | <ul><li>A boolean value indicating whether or not the application could be activated</li></ul>          |

#### [allWindows](#allwindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:allWindows() -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns all open windows owned by the given app.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of zero or more hs.window objects owned by the application</li></ul>          |
| **Notes**                                            | <ul><li>This function can only return windows in the current Mission Control Space; if you need to address windows across</li><li>   different Spaces you can use the `hs.window.filter` module</li><li>   - if `Displays have separate Spaces` is *on* (in System Preferences>Mission Control) the current Space is defined</li><li>     as the union of all currently visible Spaces</li><li>   - minimized windows and hidden windows (i.e. belonging to hidden apps, e.g. via cmd-h) are always considered</li><li>     to be in the current Space</li></ul>                |

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:bundleID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the bundle identifier of the app.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the bundle identifier of the application</li></ul>          |

#### [findMenuItem](#findmenuitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:findMenuItem(menuItem[, isRegex]) -> table or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Searches the application for a menu item                                                                                         |
| **Parameters**                                       | <ul><li>menuItem - This can either be a string containing the text of a menu item (e.g. `"Messages"`) or a table representing the hierarchical path of a menu item (e.g. `{"File", "Share", "Messages"}`). In the string case, all of the application's menus will be searched until a match is found (with no specified behaviour if multiple menu items exist with the same name). In the table case, the whole menu structure will not be searched, because a precise path has been specified.</li><li>isRegex - An optional boolean, defaulting to false, which is only used if `menuItem` is a string. If set to true, `menuItem` will be treated as a regular expression rather than a strict string to match against</li></ul> |
| **Returns**                                          | <ul><li>Returns nil if the menu item cannot be found. If it does exist, returns a table with two keys:</li><li> enabled - whether the menu item can be selected/ticked. This will always be false if the application is not currently focussed</li><li> ticked - whether the menu item is ticked or not (obviously this value is meaningless for menu items that can't be ticked)</li></ul>          |
| **Notes**                                            | <ul><li>This can only search for menu items that don't have children - i.e. you can't search for the name of a submenu</li></ul>                |

#### [findWindow](#findwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:findWindow(titlePattern) -> hs.window object(s)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds windows from this application                                                                                         |
| **Parameters**                                       | <ul><li>titlePattern - a string pattern that matches (via `string.find`) the window title(s) as per `hs.window:title()` (for convenience, the matching will be done on lowercased strings)</li></ul> |
| **Returns**                                          | <ul><li>one or more hs.window objects belonging to this application that match the supplied search criterion, or `nil` if none found</li></ul>          |

#### [focusedWindow](#focusedwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:focusedWindow() -> hs.window object or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the currently focused window of the application, or nil                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An hs.window object representing the window of the application that currently has focus, or nil if there are none</li></ul>          |

#### [getMenuItems](#getmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:getMenuItems([fn]) -> table or nil | hs.application object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the menu structure of the application                                                                                         |
| **Parameters**                                       | <ul><li>fn - an optional callback function.  If provided, the function will receive a single argument and return none.</li></ul> |
| **Returns**                                          | <ul><li>If no argument is provided, returns a table containing the menu structure of the application, or nil if an error occurred. If a callback function is provided, the callback function will receive this table (or nil) and this method will return the application object this method was invoked on.</li></ul>          |
| **Notes**                                            | <ul><li>In some applications, this can take a little while to complete, because quite a large number of round trips are required to the source application, to get the information. When this method is invoked without a callback function, Hammerspoon will block while creating the menu structure table.  When invoked with a callback function, the menu structure is built in a background thread.</li></ul>                |

#### [getWindow](#getwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:getWindow(title) -> hs.window object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a specific window from this application                                                                                         |
| **Parameters**                                       | <ul><li>title - the desired window's title string as per `hs.window:title()`</li></ul> |
| **Returns**                                          | <ul><li>the desired hs.window object belonging to this application, or `nil` if not found</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:hide() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the app (and all its windows).                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean indicating whether the application was successfully hidden</li></ul>          |

#### [isFrontmost](#isfrontmost)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:isFrontmost() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether the app is the frontmost (i.e. is the currently active application)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if the application is the frontmost application, otherwise false</li></ul>          |

#### [isHidden](#ishidden)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:isHidden() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether the app is currently hidden.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean indicating whether the application is hidden or not</li></ul>          |

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:isRunning() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the application is still running                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the application is running, false if not</li></ul>          |
| **Notes**                                            | <ul><li>If an application is terminated and re-launched, this method will still return false, as `hs.application` objects are tied to a specific instance of an application (i.e. its PID)</li></ul>                |

#### [kill](#kill)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:kill()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Tries to terminate the app gracefully.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [kill9](#kill9)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:kill9()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Tries to terminate the app forcefully.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [kind](#kind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:kind() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Identify the application's GUI state                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number that is either 1 if the app is in the dock, 0 if it is not, or -1 if the application is prohibited from having GUI elements</li></ul>          |

#### [mainWindow](#mainwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:mainWindow() -> hs.window object or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the main window of the given app, or nil.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An hs.window object representing the main window of the application, or nil if it has no windows</li></ul>          |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:name()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Alias for `hs.application:title()`                                                                                         |

#### [path](#path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:path() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the filesystem path of the app.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the filesystem path of the application or nil if the path could not be determined (e.g. if the application has terminated).</li></ul>          |

#### [pid](#pid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:pid() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app's process identifier.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The UNIX process identifier of the application (i.e. a number)</li></ul>          |

#### [selectMenuItem](#selectmenuitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:selectMenuItem(menuitem[, isRegex]) -> true or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a menu item (i.e. simulates clicking on the menu item)                                                                                         |
| **Parameters**                                       | <ul><li>menuitem - The menu item to select, specified as either a string or a table. See the `menuitem` parameter of `hs.application:findMenuItem()` for more information.</li><li>isRegex - An optional boolean, defaulting to false, which is only used if `menuItem` is a string. If set to true, `menuItem` will be treated as a regular expression rather than a strict string to match against</li></ul> |
| **Returns**                                          | <ul><li>True if the menu item was found and selected, or nil if it wasn't (e.g. because the menu item couldn't be found)</li></ul>          |
| **Notes**                                            | <ul><li>Depending on the type of menu item involved, this will either activate or tick/untick the menu item</li></ul>                |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:title() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the localized name of the app (in UTF8).                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the name of the application</li></ul>          |

#### [unhide](#unhide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:unhide() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Unhides the app (and all its windows) if it's hidden.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean indicating whether the application was successfully unhidden</li></ul>          |

#### [visibleWindows](#visiblewindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application:visibleWindows() -> win[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns only the app's windows that are visible.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing zero or more hs.window objects</li></ul>          |

