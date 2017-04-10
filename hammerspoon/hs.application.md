# [docs](index.md) » hs.application
---

Manipulate running applications

## Submodules
 * [hs.application.watcher](hs.application.watcher.md)

## API Overview
* Variables - Configurable values
 * [menuGlyphs](#menuGlyphs)
* Functions - API calls offered directly by the extension
 * [applicationForPID](#applicationForPID)
 * [applicationsForBundleID](#applicationsForBundleID)
 * [enableSpotlightForNameSearches](#enableSpotlightForNameSearches)
 * [frontmostApplication](#frontmostApplication)
 * [infoForBundleID](#infoForBundleID)
 * [launchOrFocus](#launchOrFocus)
 * [launchOrFocusByBundleID](#launchOrFocusByBundleID)
 * [nameForBundleID](#nameForBundleID)
 * [pathForBundleID](#pathForBundleID)
 * [runningApplications](#runningApplications)
* Constructors - API calls which return an object, typically one that offers API methods
 * [find](#find)
 * [get](#get)
 * [open](#open)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activate](#activate)
 * [allWindows](#allWindows)
 * [bundleID](#bundleID)
 * [findMenuItem](#findMenuItem)
 * [findWindow](#findWindow)
 * [focusedWindow](#focusedWindow)
 * [getMenuItems](#getMenuItems)
 * [getWindow](#getWindow)
 * [hide](#hide)
 * [isFrontmost](#isFrontmost)
 * [isHidden](#isHidden)
 * [isRunning](#isRunning)
 * [kill](#kill)
 * [kill9](#kill9)
 * [kind](#kind)
 * [mainWindow](#mainWindow)
 * [name](#name)
 * [path](#path)
 * [pid](#pid)
 * [selectMenuItem](#selectMenuItem)
 * [title](#title)
 * [unhide](#unhide)
 * [visibleWindows](#visibleWindows)

## API Documentation
### Variables

#### [menuGlyphs](#menuGlyphs)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.menuGlyphs  |
| Type        | Variable |
| Description | A table containing UTF8 representations of the defined key glyphs used in Menus for keybaord shortcuts which are presented pictorially rather than as text (arrow keys, return key, etc.) |
| Notes |  * a `__tostring` metamethod is provided for this table so you can view its current contents by typing `hs.application.menuGlyphs` into the Hammerspoon console. * This table is provided as a variable so that you can change any representation if you feel you know of a better or more appropriate one for you usage at runtime. |

### Functions

#### [applicationForPID](#applicationForPID)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.applicationForPID(pid) -> hs.application object or nil  |
| Type        | Function |
| Description | Returns the running app for the given pid, if it exists. |
| Parameters |  * pid - a UNIX process id (i.e. a number) |
| Returns |  * An hs.application object if one can be found, otherwise nil |


#### [applicationsForBundleID](#applicationsForBundleID)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.applicationsForBundleID(bundleID) -> list of hs.application objects  |
| Type        | Function |
| Description | Returns any running apps that have the given bundleID. |
| Parameters |  * bundleID - An OSX application bundle indentifier |
| Returns |  * A table of zero or more hs.application objects that match the given identifier |


#### [enableSpotlightForNameSearches](#enableSpotlightForNameSearches)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.enableSpotlightForNameSearches([state]) -> boolean  |
| Type        | Function |
| Description | Get or set whether Spotlight should be used to find alternate names for applications. |
| Parameters |  * `state` - an optional boolean specifying whether or not Spotlight should be used to try and determine alternate application names for `hs.application.find` and similar functions. |
| Returns |  * the current, possibly changed, state |
| Notes |  * This setting is persistent across reloading and restarting Hammerspoon. * If this was set to true and you set it to true again, it will purge the alternate name map and rebuild it from scratch. * You can disable Spotlight alternate name mapping by setting this value to false or nil. If you set this to false, then the notifications indicating that more results might be possible if Spotlight is enabled will be suppressed.

#### [frontmostApplication](#frontmostApplication)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.frontmostApplication() -> hs.application object  |
| Type        | Function |
| Description | Returns the application object for the frontmost (active) application.  This is the application which currently receives input events. |
| Parameters |  * None |
| Returns |  * An hs.application object |


#### [infoForBundleID](#infoForBundleID)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.infoForBundleID(bundleID) -> table or nil  |
| Type        | Function |
| Description | Gets the metadata of an application from its bundle identifier |
| Parameters |  * bundleID - A string containing an application bundle identifier (e.g. "com.apple.Safari") |
| Returns |  * A table containing information about the application, or nil if the bundle identifier could not be located |


#### [launchOrFocus](#launchOrFocus)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.launchOrFocus(name) -> boolean  |
| Type        | Function |
| Description | Launches the app with the given name, or activates it if it's already running |
| Parameters |  * name - A string containing the name of the application to either launch or focus. This can also be the full path to an application (including the `.app` suffix) if you need to uniquely distinguish between applications in different locations that share the same name |
| Returns |  * True if the application was either launched or focused, otherwise false (e.g. if the application doesn't exist) |
| Notes |  * The name parameter should match the name of the application on disk, e.g. "IntelliJ IDEA", rather than "IntelliJ"

#### [launchOrFocusByBundleID](#launchOrFocusByBundleID)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.launchOrFocusByBundleID(bundleID) -> boolean  |
| Type        | Function |
| Description | Launches the app with the given bundle ID, or activates it if it's already running |
| Parameters |  * bundleID - A string containing the bundle ID of the application to either launch or focus. |
| Returns |  * True if the application was either launched or focused, otherwise false (e.g. if the application doesn't exist) |
| Notes |  * Bundle identifiers typically take the form of `com.company.ApplicationName`

#### [nameForBundleID](#nameForBundleID)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.nameForBundleID(bundleID) -> string or nil  |
| Type        | Function |
| Description | Gets the name of an application from its bundle identifier |
| Parameters |  * bundleID - A string containing an application bundle identifier (e.g. "com.apple.Safari") |
| Returns |  * A string containing the application name, or nil if the bundle identifier could not be located |


#### [pathForBundleID](#pathForBundleID)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.pathForBundleID(bundleID) -> string or nil  |
| Type        | Function |
| Description | Gets the filesystem path of an application from its bundle identifier |
| Parameters |  * bundleID - A string containing an application bundle identifier (e.g. "com.apple.Safari") |
| Returns |  * A string containing the app bundle's filesystem path, or nil if the bundle identifier could not be located |


#### [runningApplications](#runningApplications)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.runningApplications() -> list of hs.application objects  |
| Type        | Function |
| Description | Returns all running apps. |
| Parameters |  * None |
| Returns |  * A table containing zero or more hs.application objects currently running on the system |
 |

### Constructors

#### [find](#find)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.find(hint) -> hs.application object(s)  |
| Type        | Constructor |
| Description | Finds running applications |
| Parameters |  * hint - search criterion for the desired application(s); it can be:   - a pid number as per `hs.application:pid()`   - a bundle ID string as per `hs.application:bundleID()`   - a string pattern that matches (via `string.find`) the application name as per `hs.application:name()` (for convenience, the matching will be done on lowercased strings)   - a string pattern that matches (via `string.find`) the application's window title per `hs.window:title()` (for convenience, the matching will be done on lowercased strings) |
| Returns |  * one or more hs.application objects for running applications that match the supplied search criterion, or `nil` if none found |
| Notes |  * for convenience you can call this as `hs.application(hint)` * use this function when you don't know the exact name of an application you're interested in, i.e.   from the console: `hs.application'term' --> hs.application: iTerm2 (0x61000025fb88)  hs.application: Terminal (0x618000447588)`.   But be careful when using it in your `init.lua`: `terminal=hs.application'term'` will assign either "Terminal" or "iTerm2" arbitrarily (or even,   if neither are running, any other app with a window that happens to have "term" in its title); to make sure you get the right app in your scripts,   use `hs.application.get` with the exact name: `terminal=hs.application.get'Terminal' --> "Terminal" app, or nil if it's not running`

#### [get](#get)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.get(hint) -> hs.application object  |
| Type        | Constructor |
| Description | Gets a running application |
| Parameters |  * hint - search criterion for the desired application; it can be:   - a pid number as per `hs.application:pid()`   - a bundle ID string as per `hs.application:bundleID()`   - an application name string as per `hs.application:name()` |
| Returns |  * an hs.application object for a running application that matches the supplied search criterion, or `nil` if not found |
| Notes |  * see also `hs.application.find`

#### [open](#open)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application.open(app[, wait, [waitForFirstWindow]]) -> hs.application object  |
| Type        | Constructor |
| Description | Launches an application, or activates it if it's already running |
| Parameters |  * app - a string describing the application to open; it can be:   - the application's name as per `hs.application:name()`   - the full path to an application on disk (including the `.app` suffix)   - the application's bundle ID as per `hs.application:bundleID()` * wait - (optional) the maximum number of seconds to wait for the app to be launched, if not already running; if omitted, defaults to 0;  if the app takes longer than this to launch, this function will return `nil`, but the app will still launch * waitForFirstWindow - (optional) if `true`, additionally wait until the app has spawned its first window (which usually takes a bit longer) |
| Returns |  * the `hs.application` object for the launched or activated application; `nil` if not found |
| Notes |  * the `wait` parameter will *block all Hammerspoon activity* in order to return the application object "synchronously"; only use it if you   a) have no time-critical event processing happening elsewhere in your `init.lua` and b) need to act on the application object, or on   its window(s), right away * when launching a "windowless" app (background daemon, menulet, etc.) make sure to omit `waitForFirstWindow` |

### Methods

#### [activate](#activate)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:activate([allWindows]) -> bool  |
| Type        | Method |
| Description | Tries to activate the app (make its key window focused) and returns whether it succeeded; if allWindows is true, all windows of the application are brought forward as well. |
| Parameters |  * allWindows - If true, all windows of the application will be brought to the front. Otherwise, only the application's key window will. Defaults to false. |
| Returns |  * A boolean value indicating whether or not the application could be activated |


#### [allWindows](#allWindows)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:allWindows() -> list of hs.window objects  |
| Type        | Method |
| Description | Returns all open windows owned by the given app. |
| Parameters |  * None |
| Returns |  * A table of zero or more hs.window objects owned by the application |
| Notes |  * This function can only return windows in the current Mission Control Space; if you need to address windows across   different Spaces you can use the `hs.window.filter` module   - if `Displays have separate Spaces` is *on* (in System Preferences>Mission Control) the current Space is defined     as the union of all currently visible Spaces   - minimized windows and hidden windows (i.e. belonging to hidden apps, e.g. via cmd-h) are always considered     to be in the current Space

#### [bundleID](#bundleID)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:bundleID() -> string  |
| Type        | Method |
| Description | Returns the bundle identifier of the app. |
| Parameters |  * None |
| Returns |  * A string containing the bundle identifier of the application |


#### [findMenuItem](#findMenuItem)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:findMenuItem(menuItem[, isRegex]) -> table or nil  |
| Type        | Method |
| Description | Searches the application for a menu item |
| Parameters |  * menuItem - This can either be a string containing the text of a menu item (e.g. `"Messages"`) or a table representing the hierarchical path of a menu item (e.g. `{"File", "Share", "Messages"}`). In the string case, all of the application's menus will be searched until a match is found (with no specified behaviour if multiple menu items exist with the same name). In the table case, the whole menu structure will not be searched, because a precise path has been specified. * isRegex - An optional boolean, defaulting to false, which is only used if `menuItem` is a string. If set to true, `menuItem` will be treated as a regular expression rather than a strict string to match against |
| Returns |  * Returns nil if the menu item cannot be found. If it does exist, returns a table with two keys:  * enabled - whether the menu item can be selected/ticked. This will always be false if the application is not currently focussed  * ticked - whether the menu item is ticked or not (obviously this value is meaningless for menu items that can't be ticked) |
| Notes |  * This can only search for menu items that don't have children - i.e. you can't search for the name of a submenu

#### [findWindow](#findWindow)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:findWindow(titlePattern) -> hs.window object(s)  |
| Type        | Method |
| Description | Finds windows from this application |
| Parameters |  * titlePattern - a string pattern that matches (via `string.find`) the window title(s) as per `hs.window:title()` (for convenience, the matching will be done on lowercased strings) |
| Returns |  * one or more hs.window objects belonging to this application that match the supplied search criterion, or `nil` if none found |


#### [focusedWindow](#focusedWindow)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:focusedWindow() -> hs.window object or nil  |
| Type        | Method |
| Description | Returns the currently focused window of the application, or nil |
| Parameters |  * None |
| Returns |  * An hs.window object representing the window of the application that currently has focus, or nil if there are none |


#### [getMenuItems](#getMenuItems)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:getMenuItems() -> table or nil  |
| Type        | Method |
| Description | Gets the menu structure of the application |
| Parameters |  * None |
| Returns |  * A table containing the menu structure of the application, or nil if an error occurred |
| Notes |  * In some applications, this can take a little while to complete, because quite a large number of round trips are required to the source application, to get the information. Take care! * The table is nested with the same structure as the menus of the application. Each item has several keys containing information about the menu item. Not all keys will appear for all items. The possible keys are:  * AXTitle - A string containing the text of the menu item (entries which have no title are menu separators)  * AXEnabled - A boolean, 1 if the menu item is clickable, 0 if not  * AXRole - A string containing the role of the menu item - this will be either AXMenuBarItem for a top level menu, or AXMenuItem for an item in a menu  * AXMenuItemMarkChar - A string containing the "mark" character for a menu item. This is for toggleable menu items and will usually be an empty string or a Unicode tick character (✓)  * AXMenuItemCmdModifiers - A table containing string representations of the keyboard modifiers for the menu item's keyboard shortcut, or nil if no modifiers are present  * AXMenuItemCmdChar - A string containing the key for the menu item's keyboard shortcut, or an empty string if no shortcut is present  * AXMenuItemCmdGlyph - An integer, corresponding to one of the defined glyphs in `hs.application.menuGlyphs` if the keyboard shortcut is a special character usually represented by a pictorial representation (think arrow keys, return, etc), or an empty string if no glyph is used in presenting the keyboard shortcut. * Using `hs.inspect()` on these tables, while useful for exploration, can be extremely slow, taking several minutes to correctly render very complex menus

#### [getWindow](#getWindow)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:getWindow(title) -> hs.window object  |
| Type        | Method |
| Description | Gets a specific window from this application |
| Parameters |  * title - the desired window's title string as per `hs.window:title()` |
| Returns |  * the desired hs.window object belonging to this application, or `nil` if not found |


#### [hide](#hide)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:hide() -> boolean  |
| Type        | Method |
| Description | Hides the app (and all its windows). |
| Parameters |  * None |
| Returns |  * A boolean indicating whether the application was successfully hidden |


#### [isFrontmost](#isFrontmost)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:isFrontmost() -> boolean  |
| Type        | Method |
| Description | Returns whether the app is the frontmost (i.e. is the currently active application) |
| Parameters |  * None |
| Returns |  * True if the application is the frontmost application, otherwise false |


#### [isHidden](#isHidden)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:isHidden() -> boolean  |
| Type        | Method |
| Description | Returns whether the app is currently hidden. |
| Parameters |  * None |
| Returns |  * A boolean indicating whether the application is hidden or not |


#### [isRunning](#isRunning)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:isRunning() -> boolean  |
| Type        | Method |
| Description | Checks if the application is still running |
| Parameters |  * None |
| Returns |  * A boolean, true if the application is running, false if not |
| Notes |  * If an application is terminated and re-launched, this method will still return false, as `hs.application` objects are tied to a specific instance of an application (i.e. its PID)

#### [kill](#kill)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:kill()  |
| Type        | Method |
| Description | Tries to terminate the app gracefully. |
| Parameters |  * None |
| Returns |  * None |


#### [kill9](#kill9)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:kill9()  |
| Type        | Method |
| Description | Tries to terminate the app forcefully. |
| Parameters |  * None |
| Returns |  * None |


#### [kind](#kind)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:kind() -> number  |
| Type        | Method |
| Description | Identify the application's GUI state |
| Parameters |  * None |
| Returns |  * A number that is either 1 if the app is in the dock, 0 if it is not, or -1 if the application is prohibited from having GUI elements |


#### [mainWindow](#mainWindow)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:mainWindow() -> hs.window object or nil  |
| Type        | Method |
| Description | Returns the main window of the given app, or nil. |
| Parameters |  * None |
| Returns |  * An hs.window object representing the main window of the application, or nil if it has no windows |


#### [name](#name)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:name()  |
| Type        | Method |
| Description | Alias for `hs.application:title()` |


#### [path](#path)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:path() -> string  |
| Type        | Method |
| Description | Returns the filesystem path of the app. |
| Parameters |  * None |
| Returns |  * A string containing the filesystem path of the application |


#### [pid](#pid)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:pid() -> number  |
| Type        | Method |
| Description | Returns the app's process identifier. |
| Parameters |  * None |
| Returns |  * The UNIX process identifier of the application (i.e. a number) |


#### [selectMenuItem](#selectMenuItem)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:selectMenuItem(menuitem) -> true or nil  |
| Type        | Method |
| Description | Selects a menu item (i.e. simulates clicking on the menu item) |
| Parameters |  * menuitem - The menu item to select, specified as either a string or a table. See the `menuitem` parameter of `hs.application:findMenuItem()` for more information. * isRegex - An optional boolean, defaulting to false, which is only used if `menuItem` is a string. If set to true, `menuItem` will be treated as a regular expression rather than a strict string to match against |
| Returns |  * True if the menu item was found and selected, or nil if it wasn't (e.g. because the menu item couldn't be found) |
| Notes |  * Depending on the type of menu item involved, this will either activate or tick/untick the menu item

#### [title](#title)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:title() -> string  |
| Type        | Method |
| Description | Returns the localized name of the app (in UTF8). |
| Parameters |  * None |
| Returns |  * A string containing the name of the application |


#### [unhide](#unhide)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:unhide() -> boolean  |
| Type        | Method |
| Description | Unhides the app (and all its windows) if it's hidden. |
| Parameters |  * None |
| Returns |  * A boolean indicating whether the application was successfully unhidden |


#### [visibleWindows](#visibleWindows)
|             |                 |
| ------------|-----------------|
| Signature   | hs.application:visibleWindows() -> win[]  |
| Type        | Method |
| Description | Returns only the app's windows that are visible. |
| Parameters |  * None |
| Returns |  * A table containing zero or more hs.window objects |
 |
