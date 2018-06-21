# [docs](index.md) » cp.apple.finalcutpro
---

Represents the Final Cut Pro application, providing functions that allow different tasks to be accomplished.

Generally, you will `require` the `cp.apple.finalcutpro` module to import it, like so:

```lua
local fcp = require("cp.apple.finalcutpro")
```

Then, there are the `UpperCase` files, which represent the application itself:

* `MenuBar` 	            - The main menu bar.
* `prefs/PreferencesWindow` - The preferences window.
* etc...

The `fcp` variable is the root application. It has functions which allow you to perform tasks or access parts of the UI. For example, to open the `Preferences` window, you can do this:

```lua
fcp:preferencesWindow():show()
```

In general, as long as Final Cut Pro is running, actions can be performed directly, and the API will perform the required operations to achieve it. For example, to toggle the 'Create Optimized Media' checkbox in the 'Import' section of the 'Preferences' window, you can simply do this:

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
 * [cp.apple.finalcutpro.app](cp.apple.finalcutpro.app.md)
 * [cp.apple.finalcutpro.cmd](cp.apple.finalcutpro.cmd.md)
 * [cp.apple.finalcutpro.content](cp.apple.finalcutpro.content.md)
 * [cp.apple.finalcutpro.export](cp.apple.finalcutpro.export.md)
 * [cp.apple.finalcutpro.ids](cp.apple.finalcutpro.ids.md)
 * [cp.apple.finalcutpro.import](cp.apple.finalcutpro.import.md)
 * [cp.apple.finalcutpro.inspector](cp.apple.finalcutpro.inspector.md)
 * [cp.apple.finalcutpro.main](cp.apple.finalcutpro.main.md)
 * [cp.apple.finalcutpro.menu](cp.apple.finalcutpro.menu.md)
 * [cp.apple.finalcutpro.plugins](cp.apple.finalcutpro.plugins.md)
 * [cp.apple.finalcutpro.prefs](cp.apple.finalcutpro.prefs.md)
 * [cp.apple.finalcutpro.strings](cp.apple.finalcutpro.strings.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [ALLOWED_IMPORT_AUDIO_EXTENSIONS](#allowed_import_audio_extensions)
 * [ALLOWED_IMPORT_EXTENSIONS](#allowed_import_extensions)
 * [ALLOWED_IMPORT_IMAGE_EXTENSIONS](#allowed_import_image_extensions)
 * [ALLOWED_IMPORT_VIDEO_EXTENSIONS](#allowed_import_video_extensions)
 * [BUNDLE_ID](#bundle_id)
 * [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
 * [EVENT_DESCRIPTION_PATH](#event_description_path)
 * [FLEXO_LANGUAGES](#flexo_languages)
 * [PASTEBOARD_UTI](#pasteboard_uti)
* Functions - API calls offered directly by the extension
 * [commandSet](#commandset)
 * [init](#init)
 * [matches](#matches)
 * [reset](#reset)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contentUI](#contentui)
 * [contentUI](#contentui)
 * [contentUI](#contentui)
 * [contentUI](#contentui)
 * [isShowing](#isshowing)
 * [isShowing](#isshowing)
 * [isShowing](#isshowing)
 * [isShowing](#isshowing)
 * [isShowing](#isshowing)
 * [UI](#ui)
 * [UI](#ui)
 * [UI](#ui)
 * [UI](#ui)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activeCommandSet](#activecommandset)
 * [activeCommandSetPath](#activecommandsetpath)
 * [alert](#alert)
 * [browser](#browser)
 * [bundleID](#bundleid)
 * [closeLibrary](#closelibrary)
 * [color](#color)
 * [colorBoard](#colorboard)
 * [commandEditor](#commandeditor)
 * [defaultCommandSetPath](#defaultcommandsetpath)
 * [effects](#effects)
 * [eventViewer](#eventviewer)
 * [exportDialog](#exportdialog)
 * [fullScreenWindow](#fullscreenwindow)
 * [generators](#generators)
 * [getCommandShortcuts](#getcommandshortcuts)
 * [getPath](#getpath)
 * [hide](#hide)
 * [importXML](#importxml)
 * [inspector](#inspector)
 * [isSupportedLocale](#issupportedlocale)
 * [keysWithString](#keyswithstring)
 * [keywordEditor](#keywordeditor)
 * [launch](#launch)
 * [libraries](#libraries)
 * [media](#media)
 * [mediaImport](#mediaimport)
 * [menu](#menu)
 * [notifier](#notifier)
 * [openLibrary](#openlibrary)
 * [performShortcut](#performshortcut)
 * [plugins](#plugins)
 * [preferencesWindow](#preferenceswindow)
 * [primaryWindow](#primarywindow)
 * [quit](#quit)
 * [restart](#restart)
 * [scanPlugins](#scanplugins)
 * [secondaryWindow](#secondarywindow)
 * [selectLibrary](#selectlibrary)
 * [selectMenu](#selectmenu)
 * [selectMenuItem](#selectmenuitem)
 * [show](#show)
 * [string](#string)
 * [timeline](#timeline)
 * [toolbar](#toolbar)
 * [transitions](#transitions)
 * [userCommandSetPath](#usercommandsetpath)
 * [viewer](#viewer)

## API Documentation

### Constants

#### [ALLOWED_IMPORT_AUDIO_EXTENSIONS](#allowed_import_audio_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.ALLOWED_IMPORT_AUDIO_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of audio file extensions Final Cut Pro can import.                                                                                         |

#### [ALLOWED_IMPORT_EXTENSIONS](#allowed_import_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.ALLOWED_IMPORT_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of all file extensions Final Cut Pro can import.                                                                                         |

#### [ALLOWED_IMPORT_IMAGE_EXTENSIONS](#allowed_import_image_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.ALLOWED_IMPORT_IMAGE_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of image file extensions Final Cut Pro can import.                                                                                         |

#### [ALLOWED_IMPORT_VIDEO_EXTENSIONS](#allowed_import_video_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.ALLOWED_IMPORT_VIDEO_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of video file extensions Final Cut Pro can import.                                                                                         |

#### [BUNDLE_ID](#bundle_id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.BUNDLE_ID` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Final Cut Pro's Bundle ID as a `semver`.                                                                                         |

#### [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.EARLIEST_SUPPORTED_VERSION` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The earliest version of Final Cut Pro supported by this module.                                                                                         |

#### [EVENT_DESCRIPTION_PATH](#event_description_path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.EVENT_DESCRIPTION_PATH` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The Event Description Path.                                                                                         |

#### [FLEXO_LANGUAGES](#flexo_languages)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.FLEXO_LANGUAGES` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of Final Cut Pro's supported Languages for the Flexo Framework                                                                                         |

#### [PASTEBOARD_UTI](#pasteboard_uti)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.PASTEBOARD_UTI` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Final Cut Pro's Pasteboard UTI                                                                                         |

### Functions

#### [commandSet](#commandset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.commandSet(path) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the Command Set at the specified path as a table.                                                                                         |
| **Parameters**                                       |  * `path`	- The path to the Command Set.                                       |
| **Returns**                                          |  * The Command Set as a table, or `nil` if there was a problem.                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:init() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The app.                                                |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.CommandEditor.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:reset() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resets the language cache                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

### Fields

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ShareInspector.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` containing the properties rows, if available.                                                                                         |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` containing the properties rows, if available.                                                                                         |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TitleInspector.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` containing the properties rows, if available.                                                                                         |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` containing the properties rows, if available.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TitleInspector.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the TitleInspector is currently showing.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.AudioInspector.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the AudioInspector is currently showing.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ShareInspector.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the ShareInspector is currently showing.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the VideoInspector is currently showing.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the TextInspector is currently showing.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.AudioInspector.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Audio Inspector.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Video Inspector.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TitleInspector.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Title Inspector.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ShareInspector.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Share Inspector.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Text Inspector.                                                                                         |

### Methods

#### [activeCommandSet](#activecommandset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:activeCommandSet([forceReload]) -> table or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the 'Active Command Set' as a Table. The result is cached, so pass in                                                                                         |
| **Parameters**                                       |  * [forceReload]	- If `true`, require the Command Set to be reloaded.                                       |
| **Returns**                                          |  * A table of the Active Command Set's contents, or `nil` if an error occurred                                                |

#### [activeCommandSetPath](#activecommandsetpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:activeCommandSetPath() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the 'Active Command Set' value from the Final Cut Pro preferences                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The 'Active Command Set' value, or the 'Default' Command Set if this is the first time Final Cut Pro has been run.                                                |

#### [alert](#alert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:alert() -> cp.ui.Alert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Provides basic access to any 'alert' dialog windows in the app.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the `Alert` instance                                                |

#### [browser](#browser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:browser() -> Browser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Browser instance, whether it is in the primary or secondary window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the Browser                                                |

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:bundleID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Bundle ID for the app.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The Bundle ID                                                |

#### [closeLibrary](#closelibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:closeLibrary(title) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attempts to close a library with the specified `title`.                                                                                         |
| **Parameters**                                       | * title	- The title of the FCP Library to close.                                       |
| **Returns**                                          | * `true` if successful, or `false` if not.                                                |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:color() -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ColorInspector instance from the primary window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the ColorInspector                                                |

#### [colorBoard](#colorboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:colorBoard() -> ColorBoard` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ColorBoard instance from the primary window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the ColorBoard                                                |

#### [commandEditor](#commandeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:commandEditor() -> commandEditor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro Command Editor                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Final Cut Pro Command Editor                                                |

#### [defaultCommandSetPath](#defaultcommandsetpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:defaultCommandSetPath([locale]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the path to the 'Default' Command Set.                                                                                         |
| **Parameters**                                       |  * `locale`	- The optional locale to use. Defaults to the [current locale](#currentLocale).                                       |
| **Returns**                                          |  * The 'Default' Command Set path, or `nil` if an error occurred                                                |

#### [effects](#effects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:effects() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the EffectsBrowser instance, whether it is in the primary or secondary window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the EffectsBrowser                                                |

#### [eventViewer](#eventviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:eventViewer() -> Event Viewer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Event Viewer instance, whether it is in the primary or secondary window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the Event Viewer                                                |

#### [exportDialog](#exportdialog)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:exportDialog() -> exportDialog object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro Export Dialog Box                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Final Cut Pro Export Dialog Box                                                |

#### [fullScreenWindow](#fullscreenwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:fullScreenWindow() -> fullScreenWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro Full Screen Window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Full Screen Playback Window                                                |

#### [generators](#generators)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:generators() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the GeneratorsBrowser instance, whether it is in the primary or secondary window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the GeneratorsBrowser                                                |

#### [getCommandShortcuts](#getcommandshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.getCommandShortcuts(id) -> table of hs.commands.shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a shortcut from the Active Command Set with the specified ID and returns a table                                                                                         |
| **Parameters**                                       |  * id - The unique ID for the command.                                       |
| **Returns**                                          |  * The array of shortcuts, or `nil` if no command exists with the specified `id`.                                                |

#### [getPath](#getpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:getPath() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Path to Final Cut Pro Application                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A string containing Final Cut Pro's filesystem path, or nil if Final Cut Pro's path could not be determined.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides Final Cut Pro                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The FCP instance.                                                |

#### [importXML](#importxml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:importXML(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Imports an XML file into Final Cut Pro                                                                                         |
| **Parameters**                                       |  * path = Path to XML File                                       |
| **Returns**                                          |  * A boolean value indicating whether the AppleScript succeeded or not                                                |

#### [inspector](#inspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:inspector() -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Inspector instance from the primary window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the Inspector                                                |

#### [isSupportedLocale](#issupportedlocale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:isSupportedLocale(locale) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the provided `locale` is supported by the app.                                                                                         |
| **Parameters**                                       |  * `language`	- The `cp.i18n.localeID` or string code. E.g. "en" or "zh_CN"                                       |
| **Returns**                                          |  * `true` if the locale is supported.                                                |

#### [keysWithString](#keyswithstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:keysWithString(string[, lang]) -> {string}` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Looks up an application string and returns an array of keys that match. It will take into account current language the app is running in, or use `lang` if provided.                                                                                         |
| **Parameters**                                       |  * `string`	- The string to look up. * `lang`	- The language (defaults to current FCPX language).                                       |
| **Returns**                                          |  * The array of keys with a matching string.                                                |
| **Notes**                                            |  * This method may be very inefficient, since it has to search through every possible key/value pair to find matches. It is not recommended that this is used in production.                                                      |

#### [keywordEditor](#keywordeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:keywordEditor() -> keywordEditor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro Keyword Editor                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Final Cut Pro Keyword Editor                                                |

#### [launch](#launch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:launch([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Launches Final Cut Pro, or brings it to the front if it was already running.                                                                                         |
| **Parameters**                                       |  * waitSeconds  - if provided, we will wait for up to the specified seconds for the launch to complete.                                       |
| **Returns**                                          |  * The FCP instance.                                                |

#### [libraries](#libraries)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:libraries() -> LibrariesBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the LibrariesBrowser instance, whether it is in the primary or secondary window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the LibrariesBrowser                                                |

#### [media](#media)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:media() -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the MediaBrowser instance, whether it is in the primary or secondary window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the MediaBrowser                                                |

#### [mediaImport](#mediaimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:mediaImport() -> mediaImport object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro Media Import Window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Final Cut Pro Media Import Window                                                |

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:menu() -> cp.app.menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.app.menu` for FCP.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.app.menu` for the app.                                                |

#### [notifier](#notifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:notifier() -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a notifier that is tracking the application UI element. It has already been started.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The notifier.                                                |

#### [openLibrary](#openlibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:openLibrary(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attempts to open a file at the specified absolute `path`.                                                                                         |
| **Parameters**                                       | * path	- The path to the FCP Library to open.                                       |
| **Returns**                                          | * `true` if successful, or `false` if not.                                                |

#### [performShortcut](#performshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:performShortcut(whichShortcut) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Performs a Final Cut Pro Shortcut                                                                                         |
| **Parameters**                                       |  * whichShortcut - As per the Command Set name                                       |
| **Returns**                                          |  * true if successful otherwise false                                                |

#### [plugins](#plugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:plugins() -> cp.apple.finalcutpro.plugins` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the plugins manager for the app.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The plugins manager.                                                |

#### [preferencesWindow](#preferenceswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:preferencesWindow() -> preferenceWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro Preferences Window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Preferences Window                                                |

#### [primaryWindow](#primarywindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:primaryWindow() -> primaryWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro Preferences Window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Primary Window                                                |

#### [quit](#quit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:quit([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Quits Final Cut Pro, if it's running.                                                                                         |
| **Parameters**                                       |  * waitSeconds      - The number of seconds to wait for the quit to complete.                                       |
| **Returns**                                          |  * The FCP instance.                                                |

#### [restart](#restart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:restart([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Restart Final Cut Pro, if it is running. If not, nothing happens.                                                                                         |
| **Parameters**                                       |  * `waitSeconds`	- If provided, the number of seconds to wait for the restart to complete.                                       |
| **Returns**                                          |  * The FCP instance.                                                |

#### [scanPlugins](#scanplugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:scanPlugins() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Scan Final Cut Pro Plugins                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A MenuBar object                                                |

#### [secondaryWindow](#secondarywindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:secondaryWindow() -> secondaryWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro Preferences Window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Secondary Window                                                |

#### [selectLibrary](#selectlibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:selectLibrary(title) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attempts to select an open library with the specified title.                                                                                         |
| **Parameters**                                       | * title - The title of the library to select.                                       |
| **Returns**                                          | * The library row `axuielement`.                                                |

#### [selectMenu](#selectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:selectMenu(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a Final Cut Pro Menu Item based on the list of menu titles in English.                                                                                         |
| **Parameters**                                       |  * `path`	    - The list of menu items you'd like to activate, for example:           select("View", "Browser", "as List") * `options`    - (optional) The table of options. See `cp.app.menu:selectMenu(...)` for details.                                       |
| **Returns**                                          |  * `true` if the press was successful.                                                |

#### [selectMenuItem](#selectmenuitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:selectMenuItem(path, options) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a Menu Item based on the provided menu path.                                                                                         |
| **Parameters**                                       |  * path - The list of menu items you'd like to activate. * options - (optional) The table of options to apply.                                       |
| **Returns**                                          |  * An `Observable` which emits the final menu item, or an error if the selection failed.                                                |
| **Notes**                                            |  * The returned `Observable` will be 'hot', in that it will execute even if no subscription is made to the result. However, it will potentially be run asynchronously, so the actual execution may occur later.                                                      |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:show() -> cp.apple.finalcutpro` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Activate Final Cut Pro, if it is running.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The FCP instance.                                                |

#### [string](#string)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:string(key[, locale][, quiet]]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Looks up an application string with the specified `key`.                                                                                         |
| **Parameters**                                       |  * `key`	- The key to look up. * `locale` - Optional locale to retrieve the key for, if available. May be a `string` or `cp.i18n.localeID`. * `quiet`	- Optional boolean, defaults to `false`. If `true`, no warnings are logged for missing keys.                                       |
| **Returns**                                          |  * The requested string or `nil` if the application is not running.                                                |

#### [timeline](#timeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:timeline() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Timeline instance, whether it is in the primary or secondary window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the Timeline                                                |

#### [toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:toolbar() -> PrimaryToolbar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Primary Toolbar - the toolbar at the top of the Primary Window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the PrimaryToolbar                                                |

#### [transitions](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:transitions() -> TransitionsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the TransitionsBrowser instance, whether it is in the primary or secondary window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the TransitionsBrowser                                                |

#### [userCommandSetPath](#usercommandsetpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.userCommandSetPath() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the path where User Command Set files are stored.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A path as a string or `nil` if the folder doesn't exist.                                                |

#### [viewer](#viewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:viewer() -> Viewer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Viewer instance, whether it is in the primary or secondary window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the Viewer                                                |

