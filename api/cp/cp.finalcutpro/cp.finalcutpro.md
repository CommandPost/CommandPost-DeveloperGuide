# [docs](index.md) » cp.finalcutpro
---

Represents the Final Cut Pro X application, providing functions that allow different tasks to be accomplished.

This module provides an API to work with the FCPX application. There are a couple of types of files:

* `init.lua` - the main module that gets imported.
* `axutils.lua` - some utility functions for working with `axuielement` objects.
* `test.lua` - some support functions for testing. TODO: Make this better.

Generally, you will `require` the `cp.finalcutpro` module to import it, like so:

```lua
local fcp = require("cp.finalcutpro")
```

Then, there are the `UpperCase` files, which represent the application itself:

* `MenuBar` 	- The main menu bar.
* `prefs/PreferencesWindow` - The preferences window.
* etc...

The `fcp` variable is the root application. It has functions which allow you to perform tasks or access parts of the UI. For example, to open the `Preferences` window, you can do this:

```lua
fcp:preferencesWindow():show()
```

In general, as long as FCPX is running, actions can be performed directly, and the API will perform the required operations to achieve it. For example, to toggle the 'Create Optimized Media' checkbox in the 'Import' section of the 'Preferences' window, you can simply do this:

```lua
fcp:preferencesWindow():importPanel():toggleCreateOptimizedMedia()
```

The API will automatically open the `Preferences` window, navigate to the 'Import' panel and toggle the checkbox.

The `UpperCase` classes also have a variety of `UI` methods. These will return the `axuielement` for the relevant GUI element, if it is accessible. If not, it will return `nil`. These allow direct interaction with the GUI if necessary. It's most useful when adding new functions to `UpperCase` files for a particular element.

This can also be used to 'wait' for an element to be visible before performing a task. For example, if you need to wait for the `Preferences` window to finish loading before doing something else, you can do this with the `cp.just` library:

```lua
local just = require("cp.just")

local prefsWindow = fcp:preferencesWindow()

local prefsUI = just.doUntil(function() return prefsWindow:UI() end)

if prefsUI then
	-- it's open!
else
	-- it's closed!
end
```

By using the `just` library, we can do a loop waiting until the function returns a result that will give up after a certain time period (10 seconds by default).

Of course, we have a specific support function for that already, so you could do this instead:

```lua
if fcp:preferencesWindow():isShowing() then
	-- it's open!
else
	-- it's closed!
end
```

## Submodules
 * [cp.finalcutpro.MenuBar](cp.finalcutpro.MenuBar.md)
 * [cp.finalcutpro.axutils](cp.finalcutpro.axutils.md)
 * [cp.finalcutpro.cmd](cp.finalcutpro.cmd.md)
 * [cp.finalcutpro.destinations](cp.finalcutpro.destinations.md)
 * [cp.finalcutpro.export](cp.finalcutpro.export.md)
 * [cp.finalcutpro.import](cp.finalcutpro.import.md)
 * [cp.finalcutpro.keycodes](cp.finalcutpro.keycodes.md)
 * [cp.finalcutpro.main](cp.finalcutpro.main.md)
 * [cp.finalcutpro.prefs](cp.finalcutpro.prefs.md)
 * [cp.finalcutpro.ui](cp.finalcutpro.ui.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [BUNDLE_ID](#BUNDLE_ID)
 * [FLEXO_LANGUAGES](#FLEXO_LANGUAGES)
 * [PASTEBOARD_UTI](#PASTEBOARD_UTI)
 * [PREFS_PLIST_PATH](#PREFS_PLIST_PATH)
 * [SUPPORTED_LANGUAGES](#SUPPORTED_LANGUAGES)
* Functions - API calls offered directly by the extension
 * [application](#application)
 * [browser](#browser)
 * [colorBoard](#colorBoard)
 * [commandEditor](#commandEditor)
 * [effects](#effects)
 * [eventViewer](#eventViewer)
 * [exportDialog](#exportDialog)
 * [fullScreenWindow](#fullScreenWindow)
 * [generators](#generators)
 * [getActiveCommandSet](#getActiveCommandSet)
 * [getActiveCommandSetPath](#getActiveCommandSetPath)
 * [getBundleID](#getBundleID)
 * [getCommandSet](#getCommandSet)
 * [getCommandShortcuts](#getCommandShortcuts)
 * [getCurrentLanguage](#getCurrentLanguage)
 * [getDefaultCommandSetPath](#getDefaultCommandSetPath)
 * [getFlexoLanguages](#getFlexoLanguages)
 * [getPasteboardUTI](#getPasteboardUTI)
 * [getPreference](#getPreference)
 * [getPreferences](#getPreferences)
 * [getSupportedLanguages](#getSupportedLanguages)
 * [getVersion](#getVersion)
 * [hide](#hide)
 * [importXML](#importXML)
 * [inspector](#inspector)
 * [isFrontmost](#isFrontmost)
 * [isInstalled](#isInstalled)
 * [isRunning](#isRunning)
 * [launch](#launch)
 * [libraries](#libraries)
 * [media](#media)
 * [mediaImport](#mediaImport)
 * [menuBar](#menuBar)
 * [new](#new)
 * [path](#path)
 * [performShortcut](#performShortcut)
 * [preferencesWindow](#preferencesWindow)
 * [primaryWindow](#primaryWindow)
 * [quit](#quit)
 * [restart](#restart)
 * [secondaryWindow](#secondaryWindow)
 * [selectMenu](#selectMenu)
 * [setPreference](#setPreference)
 * [show](#show)
 * [timeline](#timeline)
 * [transitions](#transitions)
 * [viewer](#viewer)
 * [windowsUI](#windowsUI)
* Methods - API calls which can only be made on an object returned by a constructor
 * [unwatch](#unwatch)
 * [watch](#watch)

## API Documentation

### Constants

| [BUNDLE_ID](#BUNDLE_ID)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.BUNDLE_ID`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Final Cut Pro's Bundle ID                                                                     |

| [FLEXO_LANGUAGES](#FLEXO_LANGUAGES)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.FLEXO_LANGUAGES`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Table of Final Cut Pro's supported Languages for the Flexo Framework                                                                     |

| [PASTEBOARD_UTI](#PASTEBOARD_UTI)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.PASTEBOARD_UTI`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Final Cut Pro's Pasteboard UTI                                                                     |

| [PREFS_PLIST_PATH](#PREFS_PLIST_PATH)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.PREFS_PLIST_PATH`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Final Cut Pro's Preferences Path                                                                     |

| [SUPPORTED_LANGUAGES](#SUPPORTED_LANGUAGES)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.SUPPORTED_LANGUAGES`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Table of Final Cut Pro's supported Languages                                                                     |

### Functions

| [application](#application)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:application() -> hs.application`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the hs.application for Final Cut Pro X.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>The hs.application, or nil if the application is not installed.</li></ul>          |

| [browser](#browser)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:browser() -> Browser`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Browser instance, whether it is in the primary or secondary window.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the Browser</li></ul>          |

| [colorBoard](#colorBoard)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:colorBoard() -> ColorBoard`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the ColorBoard instance from the primary window                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the ColorBoard</li></ul>          |

| [commandEditor](#commandEditor)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:commandEditor() -> commandEditor object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro Command Editor                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The Final Cut Pro Command Editor</li></ul>          |

| [effects](#effects)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:effects() -> EffectsBrowser`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the EffectsBrowser instance, whether it is in the primary or secondary window.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the EffectsBrowser</li></ul>          |

| [eventViewer](#eventViewer)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:eventViewer() -> Event Viewer`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Event Viewer instance, whether it is in the primary or secondary window.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the Event Viewer</li></ul>          |

| [exportDialog](#exportDialog)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:exportDialog() -> exportDialog object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro Export Dialog Box                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The Final Cut Pro Export Dialog Box</li></ul>          |

| [fullScreenWindow](#fullScreenWindow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:fullScreenWindow() -> fullScreenWindow object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro Full Screen Window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The Full Screen Playback Window</li></ul>          |

| [generators](#generators)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:generators() -> GeneratorsBrowser`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the GeneratorsBrowser instance, whether it is in the primary or secondary window.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the GeneratorsBrowser</li></ul>          |

| [getActiveCommandSet](#getActiveCommandSet)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getActiveCommandSet([forceReload]) -> table or nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the 'Active Command Set' as a Table. The result is cached, so pass in                                                                     |
| **Parameters**                              | <ul><li>forceReload	- (optional) If `true`, require the Command Set to be reloaded.</li></ul> |
| **Returns**                                 | <ul><li>A table of the Active Command Set's contents, or `nil` if an error occurred</li></ul>          |

| [getActiveCommandSetPath](#getActiveCommandSetPath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getActiveCommandSetPath() -> string or nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the 'Active Command Set' value from the Final Cut Pro preferences                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The 'Active Command Set' value, or the 'Default' command set if none is set.</li></ul>          |

| [getBundleID](#getBundleID)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getBundleID() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro Bundle ID                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>A string of the Final Cut Pro Bundle ID</li></ul>          |

| [getCommandSet](#getCommandSet)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getCommandSet(path) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Loads the Command Set at the specified path into a table.                                                                     |
| **Parameters**                              | <ul><li>`path`	- The path to the command set.</li></ul> |
| **Returns**                                 | <ul><li>The Command Set as a table, or `nil` if there was a problem.</li></ul>          |

| [getCommandShortcuts](#getCommandShortcuts)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.getCommandShortcuts(id) -> table of hs.commands.shortcut`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Finds a shortcut from the Active Command Set with the specified ID and returns a table                                                                     |
| **Parameters**                              | <ul><li>id - The unique ID for the command.</li></ul> |
| **Returns**                                 | <ul><li>The array of shortcuts, or `nil` if no command exists with the specified `id`.</li></ul>          |

| [getCurrentLanguage](#getCurrentLanguage)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getCurrentLanguage() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the language Final Cut Pro is currently using.                                                                     |
| **Parameters**                              | <ul><li>none</li></ul> |
| **Returns**                                 | <ul><li>Returns the current language as string (or 'en' if unknown).</li></ul>          |

| [getDefaultCommandSetPath](#getDefaultCommandSetPath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getDefaultCommandSetPath([langauge]) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the path to the 'Default' Command Set.                                                                     |
| **Parameters**                              | <ul><li>`language`	- (optional) The language code to use. Defaults to the current FCPX language.</li></ul> |
| **Returns**                                 | <ul><li>The 'Default' Command Set path, or `nil` if an error occurred</li></ul>          |

| [getFlexoLanguages](#getFlexoLanguages)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getFlexoLanguages() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table of languages Final Cut Pro's Flexo Framework supports                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table of languages Final Cut Pro supports</li></ul>          |

| [getPasteboardUTI](#getPasteboardUTI)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getPasteboardUTI() -> axuielementObject`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro axuielementObject                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>A axuielementObject of Final Cut Pro</li></ul>          |

| [getPreference](#getPreference)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.getPreference(value, default, forceReload) -> string or nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get an individual Final Cut Pro preference                                                                     |
| **Parameters**                              | <ul><li>value 			- The preference you want to return</li><li>default			- (optional) The default value to return if the preference is not set.</li><li>forceReload		= (optional) If true, forces a reload of the app's preferences.</li></ul> |
| **Returns**                                 | <ul><li>A string with the preference value, or nil if an error occurred</li></ul>          |

| [getPreferences](#getPreferences)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getPreferences() -> table or nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets Final Cut Pro's Preferences as a table. It checks if the preferences                                                                     |
| **Parameters**                              | <ul><li>forceReload	- (optional) if true, a reload will be forced even if the file hasn't been modified.</li><li>preventMultipleReloads - (optional) if true, adds a 0.01 delay before reloading preferences (for use with the watcher)</li></ul> |
| **Returns**                                 | <ul><li>A table with all of Final Cut Pro's preferences, or nil if an error occurred</li></ul>          |

| [getSupportedLanguages](#getSupportedLanguages)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getSupportedLanguages() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table of languages Final Cut Pro supports                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table of languages Final Cut Pro supports</li></ul>          |

| [getVersion](#getVersion)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:getVersion() -> string or nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Version of Final Cut Pro                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>Version as string or nil if an error occurred</li></ul>          |

| [hide](#hide)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:hide() -> cp.finalcutpro object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Hides Final Cut Pro                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An cp.finalcutpro object otherwise nil</li></ul>          |

| [importXML](#importXML)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:importXML() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Imports an XML file into Final Cut Pro                                                                     |
| **Parameters**                              | <ul><li>path = Path to XML File</li></ul> |
| **Returns**                                 | <ul><li>A boolean value indicating whether the AppleScript succeeded or not</li></ul>          |

| [inspector](#inspector)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:inspector() -> Inspector`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Inspector instance from the primary window                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the Inspector</li></ul>          |

| [isFrontmost](#isFrontmost)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:isFrontmost() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Is Final Cut Pro X Frontmost?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if Final Cut Pro is Frontmost.</li></ul>          |

| [isInstalled](#isInstalled)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:isInstalled() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Is Final Cut Pro X Installed?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if a version of FCPX is installed.</li></ul>          |

| [isRunning](#isRunning)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:isRunning() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Is Final Cut Pro Running?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>True if Final Cut Pro is running otherwise False</li></ul>          |

| [launch](#launch)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:launch() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Launches Final Cut Pro, or brings it to the front if it was already running.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if Final Cut Pro was either launched or focused, otherwise false (e.g. if Final Cut Pro doesn't exist)</li></ul>          |

| [libraries](#libraries)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:libraries() -> LibrariesBrowser`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the LibrariesBrowser instance, whether it is in the primary or secondary window.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the LibrariesBrowser</li></ul>          |

| [media](#media)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:media() -> MediaBrowser`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the MediaBrowser instance, whether it is in the primary or secondary window.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the MediaBrowser</li></ul>          |

| [mediaImport](#mediaImport)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:mediaImport() -> mediaImport object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro Media Import Window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The Final Cut Pro Media Import Window</li></ul>          |

| [menuBar](#menuBar)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:menuBar() -> menuBar object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro Menu Bar                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A menuBar object</li></ul>          |

| [new](#new)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:new() -> App`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Creates a new App instance representing Final Cut Pro                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>True is successful otherwise Nil</li></ul>          |

| [path](#path)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:path() -> string or nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Path to Final Cut Pro Application                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing Final Cut Pro's filesystem path, or nil if the bundle identifier could not be located</li></ul>          |

| [performShortcut](#performShortcut)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.performShortcut() -> Boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Performs a Final Cut Pro Shortcut                                                                     |
| **Parameters**                              | <ul><li>whichShortcut - As per the Command Set name</li></ul> |
| **Returns**                                 | <ul><li>true if successful otherwise false</li></ul>          |

| [preferencesWindow](#preferencesWindow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:preferencesWindow() -> preferenceWindow object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro Preferences Window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The Preferences Window</li></ul>          |

| [primaryWindow](#primaryWindow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:primaryWindow() -> primaryWindow object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro Preferences Window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The Primary Window</li></ul>          |

| [quit](#quit)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:quit() -> cp.finalcutpro object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Quits Final Cut Pro                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An cp.finalcutpro object otherwise nil</li></ul>          |

| [restart](#restart)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:restart() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Restart Final Cut Pro X                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if Final Cut Pro X was running and restarted successfully.</li></ul>          |

| [secondaryWindow](#secondaryWindow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:secondaryWindow() -> secondaryWindow object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Final Cut Pro Preferences Window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The Secondary Window</li></ul>          |

| [selectMenu](#selectMenu)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:selectMenu(...) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Selects a Final Cut Pro Menu Item based on the list of menu titles in English.                                                                     |
| **Parameters**                              | <ul><li>... - The list of menu items you'd like to activate, for example:</li><li>           select("View", "Browser", "as List")</li></ul> |
| **Returns**                                 | <ul><li>`true` if the press was successful.</li></ul>          |

| [setPreference](#setPreference)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:setPreference(key, value) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets an individual Final Cut Pro preference                                                                     |
| **Parameters**                              | <ul><li>key - The preference you want to change</li><li>value - The value you want to set for that preference</li></ul> |
| **Returns**                                 | <ul><li>True if executed successfully otherwise False</li></ul>          |

| [show](#show)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:show() -> cp.finalcutpro object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Activate Final Cut Pro                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An cp.finalcutpro object otherwise nil</li></ul>          |

| [timeline](#timeline)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:timeline() -> Timeline`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Timeline instance, whether it is in the primary or secondary window.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the Timeline</li></ul>          |

| [transitions](#transitions)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:transitions() -> TransitionsBrowser`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the TransitionsBrowser instance, whether it is in the primary or secondary window.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the TransitionsBrowser</li></ul>          |

| [viewer](#viewer)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:viewer() -> Viewer`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Viewer instance, whether it is in the primary or secondary window.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the Viewer</li></ul>          |

| [windowsUI](#windowsUI)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:windowsUI() -> axuielement`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the UI containing the list of windows in the app.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>The axuielement, or nil if the application is not running.</li></ul>          |

### Methods

| [unwatch](#unwatch)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:unwatch() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Stop watching for events that happen in the application for the specified ID.                                                                     |
| **Parameters**                              | <ul><li>* `id` 	- The ID object which was returned from the `watch(...)` function.</li></ul> |
| **Returns**                                 | <ul><li>* `true` if the ID was watching and has been removed.</li></ul>          |

| [watch](#watch)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro:watch() -> string`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Watch for events that happen in the application.                                                                     |
| **Parameters**                              | <ul><li>* `events` - A table of functions with to watch. These may be:</li><li>	* `active()`		- Triggered when the application is the active application.</li><li>	* `inactive()`		- Triggered when the application is no longer the active application.</li><li>   `move()` 	 		- Triggered when the application window is moved.</li><li>	* `preferences()`	- Triggered when the application preferences are updated.</li></ul> |
| **Returns**                                 | <ul><li>* An ID which can be passed to `unwatch` to stop watching.</li></ul>          |

