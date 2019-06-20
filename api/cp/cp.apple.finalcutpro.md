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
 * [cp.apple.finalcutpro.browser](cp.apple.finalcutpro.browser.md)
 * [cp.apple.finalcutpro.cmd](cp.apple.finalcutpro.cmd.md)
 * [cp.apple.finalcutpro.content](cp.apple.finalcutpro.content.md)
 * [cp.apple.finalcutpro.export](cp.apple.finalcutpro.export.md)
 * [cp.apple.finalcutpro.import](cp.apple.finalcutpro.import.md)
 * [cp.apple.finalcutpro.inspector](cp.apple.finalcutpro.inspector.md)
 * [cp.apple.finalcutpro.main](cp.apple.finalcutpro.main.md)
 * [cp.apple.finalcutpro.menu](cp.apple.finalcutpro.menu.md)
 * [cp.apple.finalcutpro.plugins](cp.apple.finalcutpro.plugins.md)
 * [cp.apple.finalcutpro.prefs](cp.apple.finalcutpro.prefs.md)
 * [cp.apple.finalcutpro.strings](cp.apple.finalcutpro.strings.md)
 * [cp.apple.finalcutpro.timeline](cp.apple.finalcutpro.timeline.md)
 * [cp.apple.finalcutpro.viewer](cp.apple.finalcutpro.viewer.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [ALLOWED_IMPORT_AUDIO_EXTENSIONS](#allowed_import_audio_extensions)
 * [ALLOWED_IMPORT_EXTENSIONS](#allowed_import_extensions)
 * [ALLOWED_IMPORT_IMAGE_EXTENSIONS](#allowed_import_image_extensions)
 * [ALLOWED_IMPORT_VIDEO_EXTENSIONS](#allowed_import_video_extensions)
 * [BLEND_MODES](#blend_modes)
 * [BUNDLE_ID](#bundle_id)
 * [CROP_TYPES](#crop_types)
 * [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
 * [EVENT_DESCRIPTION_PATH](#event_description_path)
 * [FLEXO_LANGUAGES](#flexo_languages)
 * [PASTEBOARD_UTI](#pasteboard_uti)
 * [preferences](#preferences)
 * [ROLLING_SHUTTER_AMOUNTS](#rolling_shutter_amounts)
 * [SPATIAL_CONFORM_TYPES](#spatial_conform_types)
 * [STABILIZATION_METHODS](#stabilization_methods)
 * [WORKSPACES_PATH](#workspaces_path)
* Variables - Configurable values
 * [activeCommandSet](#activecommandset)
 * [customWorkspaces](#customworkspaces)
 * [selectedWorkspace](#selectedworkspace)
* Functions - API calls offered directly by the extension
 * [commandSet](#commandset)
 * [matches](#matches)
 * [userCommandSetPath](#usercommandsetpath)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activeCommandSetPath](#activecommandsetpath)
 * [audioEnhancements](#audioenhancements)
 * [audioLanes](#audiolanes)
 * [browser](#browser)
 * [contentUI](#contentui)
 * [contentUI](#contentui)
 * [contentUI](#contentui)
 * [currentLocale](#currentlocale)
 * [deselectAll](#deselectall)
 * [effects](#effects)
 * [eventViewer](#eventviewer)
 * [inspector](#inspector)
 * [isFrontmost](#isfrontmost)
 * [isInstalled](#isinstalled)
 * [isModalDialogOpen](#ismodaldialogopen)
 * [isRunning](#isrunning)
 * [isShowing](#isshowing)
 * [isSupported](#issupported)
 * [isUnsupported](#isunsupported)
 * [libraries](#libraries)
 * [pan](#pan)
 * [preset](#preset)
 * [supportedLocales](#supportedlocales)
 * [textArea](#textarea)
 * [textLayerLeft](#textlayerleft)
 * [textLayerRight](#textlayerright)
 * [UI](#ui)
 * [version](#version)
 * [versionString](#versionstring)
 * [viewer](#viewer)
 * [volume](#volume)
 * [windowsUI](#windowsui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activeLibraryPaths](#activelibrarypaths)
 * [alert](#alert)
 * [bundleID](#bundleid)
 * [closeLibrary](#closelibrary)
 * [color](#color)
 * [colorBoard](#colorboard)
 * [commandEditor](#commandeditor)
 * [defaultCommandSetPath](#defaultcommandsetpath)
 * [doHide](#dohide)
 * [doLaunch](#dolaunch)
 * [doQuit](#doquit)
 * [doRestart](#dorestart)
 * [doSelectMenu](#doselectmenu)
 * [doShortcut](#doshortcut)
 * [doShow](#doshow)
 * [effects](#effects)
 * [exportDialog](#exportdialog)
 * [findAndReplaceTitleText](#findandreplacetitletext)
 * [fullScreenWindow](#fullscreenwindow)
 * [generators](#generators)
 * [getCommandShortcuts](#getcommandshortcuts)
 * [getPath](#getpath)
 * [hide](#hide)
 * [importXML](#importxml)
 * [isSupportedLocale](#issupportedlocale)
 * [keysWithString](#keyswithstring)
 * [keywordEditor](#keywordeditor)
 * [launch](#launch)
 * [media](#media)
 * [mediaImport](#mediaimport)
 * [menu](#menu)
 * [notifier](#notifier)
 * [openLibrary](#openlibrary)
 * [plugins](#plugins)
 * [preferencesWindow](#preferenceswindow)
 * [primaryWindow](#primarywindow)
 * [quit](#quit)
 * [scanPlugins](#scanplugins)
 * [secondaryWindow](#secondarywindow)
 * [selectLibrary](#selectlibrary)
 * [selectMenu](#selectmenu)
 * [show](#show)
 * [string](#string)
 * [timeline](#timeline)
 * [toolbar](#toolbar)
 * [transitions](#transitions)

## API Documentation

### Constants

#### [ALLOWED_IMPORT_AUDIO_EXTENSIONS](#allowed_import_audio_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.ALLOWED_IMPORT_AUDIO_EXTENSIONS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of audio file extensions Final Cut Pro can import. |

#### [ALLOWED_IMPORT_EXTENSIONS](#allowed_import_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.ALLOWED_IMPORT_EXTENSIONS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of all file extensions Final Cut Pro can import. |

#### [ALLOWED_IMPORT_IMAGE_EXTENSIONS](#allowed_import_image_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.ALLOWED_IMPORT_IMAGE_EXTENSIONS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of image file extensions Final Cut Pro can import. |

#### [ALLOWED_IMPORT_VIDEO_EXTENSIONS](#allowed_import_video_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.ALLOWED_IMPORT_VIDEO_EXTENSIONS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of video file extensions Final Cut Pro can import. |

#### [BLEND_MODES](#blend_modes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.BLEND_MODES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Blend Modes |

#### [BUNDLE_ID](#bundle_id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.BUNDLE_ID -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Final Cut Pro's Bundle ID as a `semver`. |

#### [CROP_TYPES](#crop_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.CROP_TYPES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Crop Types |

#### [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.EARLIEST_SUPPORTED_VERSION -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The earliest version of Final Cut Pro supported by this module. |

#### [EVENT_DESCRIPTION_PATH](#event_description_path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.EVENT_DESCRIPTION_PATH -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The Event Description Path. |

#### [FLEXO_LANGUAGES](#flexo_languages)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.FLEXO_LANGUAGES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of Final Cut Pro's supported Languages for the Flexo Framework |

#### [PASTEBOARD_UTI](#pasteboard_uti)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.PASTEBOARD_UTI -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Final Cut Pro's Pasteboard UTI |

#### [preferences](#preferences)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.preferences <cp.app.prefs>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The `cp.app.prefs` for Final Cut Pro. |

#### [ROLLING_SHUTTER_AMOUNTS](#rolling_shutter_amounts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.ROLLING_SHUTTER_AMOUNTS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Rolling Shutter Amounts |

#### [SPATIAL_CONFORM_TYPES](#spatial_conform_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.SPATIAL_CONFORM_TYPES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Spatial Conform Types |

#### [STABILIZATION_METHODS](#stabilization_methods)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.STABILIZATION_METHODS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Stabilisation Methods |

#### [WORKSPACES_PATH](#workspaces_path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.WORKSPACES_PATH -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The path to the custom workspaces folder. |

### Variables

#### [activeCommandSet](#activecommandset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.activeCommandSet <cp.prop: table; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Contins the 'Active Command Set' as a `table`. The result is cached, but |

#### [customWorkspaces](#customworkspaces)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:customWorkspaces <cp.prop: table; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A table containing the display names of all the user created custom workspaces. |

#### [selectedWorkspace](#selectedworkspace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.selectedWorkspace <cp.prop: string; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The currently selected workspace name. The result is cached, but updated |

### Functions

#### [commandSet](#commandset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.commandSet(path) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the Command Set at the specified path as a table. |
| **Parameters**                                       | <ul><li><code>path</code>   - The path to the Command Set.</li></ul> |
| **Returns**                                          | <ul><li>The Command Set as a table, or <code>nil</code> if there was a problem.</li></ul> |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.CommandEditor.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

#### [userCommandSetPath](#usercommandsetpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.userCommandSetPath() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the path where User Command Set files are stored. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A path as a string or <code>nil</code> if the folder doesn't exist.</li></ul> |

### Fields

#### [activeCommandSetPath](#activecommandsetpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.activeCommandSetPath <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets the 'Active Command Set' value from the Final Cut Pro preferences |

#### [audioEnhancements](#audioenhancements)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.audioEnhancements <cp.prop: PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Audio Enhancements |

#### [audioLanes](#audiolanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.audioLanes <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if audio lanes are currently showing. May be set to ensure it is showing or hidden. |

#### [browser](#browser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser <cp.apple.finalcutpro.main.Browser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Browser](cp.apple.finalcutpro.main.Browser.md) instance, whether it is in the primary or secondary window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the Browser</li></ul> |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ShareInspector.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` containing the properties rows, if available. |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` containing the properties rows, if available. |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.contentUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` containing the properties rows, if available. |

#### [currentLocale](#currentlocale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.currentLocale <cp.prop: cp.i18n.localeID; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets and sets the current locale for FCPX. |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.deselectAll <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The left text layer arrow at the bottom of the Inspector. |

#### [effects](#effects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.effects <cp.prop: PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Effects |

#### [eventViewer](#eventviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.eventViewer <cp.apple.finalcutpro.viewer.Viewer>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the [Viewer](cp.apple.finalcutpro.viewer.Viewer.md) instance, whether it is in the primary or secondary window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the Event Viewer</li></ul> |

#### [inspector](#inspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector <cp.apple.finalcutpro.inspector.Inspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the [Inspector](cp.apple.finalcutpro.inspector.Inspector.md) instance from the primary window. |

#### [isFrontmost](#isfrontmost)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:isFrontmost <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is Final Cut Pro Frontmost? |

#### [isInstalled](#isinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.isInstalled <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is any version of Final Cut Pro Installed? |

#### [isModalDialogOpen](#ismodaldialogopen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:isModalDialogOpen <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is a modal dialog currently open? |

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.isRunning <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is Final Cut Pro Running? |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.isShowing <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is Final Cut visible on screen? |

#### [isSupported](#issupported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.isSupported <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is a supported version of Final Cut Pro installed? |

#### [isUnsupported](#isunsupported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.isUnsupported <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is an unsupported version of Final Cut Pro installed? |

#### [libraries](#libraries)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.libraries <cp.apple.finalcutpro.main.LibrariesBrowser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the [LibrariesBrowser](cp.apple.finalcut.main.LibrariesBrowser.md) instance, whether it is in the primary or secondary window. |

#### [pan](#pan)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.pan <cp.prop: PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Pan |

#### [preset](#preset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.preset <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The preset popup found at the top of the inspector. |

#### [supportedLocales](#supportedlocales)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.supportedLocales <cp.prop: table of cp.i18n.localeID; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The list of supported locales for this version of FCPX. |

#### [textArea](#textarea)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.textArea <cp.ui.TextArea>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Text Inspector main Text Area. |

#### [textLayerLeft](#textlayerleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.textLayerLeft <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The left text layer arrow at the bottom of the Inspector. |

#### [textLayerRight](#textlayerright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.textLayerRight <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The left text layer arrow at the bottom of the Inspector. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.UI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Final Cut Pro `axuielement`, if available. |

#### [version](#version)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.version <cp.prop: semver; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The version number of the running or default installation of FCPX as a `semver`. |

#### [versionString](#versionstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.versionString <cp.prop: string; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The version number of the running or default installation of FCPX as a `string`. |

#### [viewer](#viewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer <cp.apple.finalcutpro.viewer.Viewer>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the [Viewer](cp.apple.finalcutpro.viewer.Viewer.md) instance, whether it is in the primary or secondary window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the Viewer</li></ul> |

#### [volume](#volume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.volume <cp.prop: PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Volume |

#### [windowsUI](#windowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.windowsUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the UI containing the list of windows in the app. |

### Methods

#### [activeLibraryPaths](#activelibrarypaths)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:activeLibraryPaths() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets a table of all the active library paths. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing any active library paths.</li></ul> |

#### [alert](#alert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:alert() -> cp.ui.Alert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Provides basic access to any 'alert' dialog windows in the app. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the <code>Alert</code> instance</li></ul> |

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:bundleID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Bundle ID for the app. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Bundle ID</li></ul> |

#### [closeLibrary](#closelibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:closeLibrary(title) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to close a library with the specified `title`. |
| **Parameters**                                       | <ul><li>title - The title of the FCP Library to close.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> if not.</li></ul> |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:color() -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the ColorInspector instance from the primary window |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the ColorInspector</li></ul> |

#### [colorBoard](#colorboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:colorBoard() -> ColorBoard` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the ColorBoard instance from the primary window |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the ColorBoard</li></ul> |

#### [commandEditor](#commandeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:commandEditor() -> commandEditor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Final Cut Pro Command Editor |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Final Cut Pro Command Editor</li></ul> |

#### [defaultCommandSetPath](#defaultcommandsetpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:defaultCommandSetPath([locale]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the path to the 'Default' Command Set. |
| **Parameters**                                       | <ul><li><code>locale</code> - The optional locale to use. Defaults to the <a href="#currentLocale">current locale</a>.</li></ul> |
| **Returns**                                          | <ul><li>The 'Default' Command Set path, or <code>nil</code> if an error occurred</li></ul> |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will hide the FCP. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute.</li></ul> |

#### [doLaunch](#dolaunch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:doLaunch() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will launch, or focus it if already running FCP. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute.</li></ul> |

#### [doQuit](#doquit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:doQuit() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will quit FCP. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute.</li></ul> |

#### [doRestart](#dorestart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:doRestart() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.cp) that will restart Final Cut Pro, if it is running. If not, nothing happens. |
| **Parameters**                                       | <ul><li>None.</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [doSelectMenu](#doselectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:doSelectMenu(path, options) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects a Menu Item based on the provided menu path. |
| **Parameters**                                       | <ul><li>path - The list of menu items you'd like to activate.</li><li>options - (optional) The table of options to apply.</li></ul> |
| **Returns**                                          | <ul><li>An <code>Observable</code> which emits the final menu item, or an error if the selection failed.</li></ul> |
| **Notes**                                            | <ul><li>The returned <code>Observable</code> will be 'hot', in that it will execute even if no subscription is made to the result. However, it will potentially be run asynchronously, so the actual execution may occur later.</li></ul> |

#### [doShortcut](#doshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:doShortcut(whichShortcut) -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Perform a Final Cut Pro Keyboard Shortcut |
| **Parameters**                                       | <ul><li>whichShortcut - As per the Command Set name</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code> that will perform the shortcut when executed.</li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will show FCP on-screen. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute.</li></ul> |

#### [effects](#effects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:effects() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the EffectsBrowser instance, whether it is in the primary or secondary window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the EffectsBrowser</li></ul> |

#### [exportDialog](#exportdialog)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:exportDialog() -> exportDialog object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Final Cut Pro Export Dialog Box |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Final Cut Pro Export Dialog Box</li></ul> |

#### [findAndReplaceTitleText](#findandreplacetitletext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:findAndReplaceTitleText() -> FindAndReplaceTitleText` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the [FindAndReplaceTitleText](cp.apple.finalcutpro.main.FindAndReplaceTitleText.md) dialog window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The window.</li></ul> |

#### [fullScreenWindow](#fullscreenwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:fullScreenWindow() -> fullScreenWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Final Cut Pro Full Screen Window |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Full Screen Playback Window</li></ul> |

#### [generators](#generators)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:generators() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the GeneratorsBrowser instance, whether it is in the primary or secondary window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the GeneratorsBrowser</li></ul> |

#### [getCommandShortcuts](#getcommandshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.getCommandShortcuts(id) -> table of hs.commands.shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds a shortcut from the Active Command Set with the specified ID and returns a table |
| **Parameters**                                       | <ul><li>id - The unique ID for the command.</li></ul> |
| **Returns**                                          | <ul><li>The array of shortcuts, or <code>nil</code> if no command exists with the specified <code>id</code>.</li></ul> |

#### [getPath](#getpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:getPath() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Path to Final Cut Pro Application |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing Final Cut Pro's filesystem path, or nil if Final Cut Pro's path could not be determined.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides Final Cut Pro |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [importXML](#importxml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:importXML(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Imports an XML file into Final Cut Pro |
| **Parameters**                                       | <ul><li>path = Path to XML File</li></ul> |
| **Returns**                                          | <ul><li>A boolean value indicating whether the AppleScript succeeded or not</li></ul> |

#### [isSupportedLocale](#issupportedlocale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:isSupportedLocale(locale) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the provided `locale` is supported by the app. |
| **Parameters**                                       | <ul><li><code>language</code>   - The <code>cp.i18n.localeID</code> or string code. E.g. "en" or "zh_CN"</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the locale is supported.</li></ul> |

#### [keysWithString](#keyswithstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:keysWithString(string[, locale]) -> {string}` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Looks up an application string and returns an array of keys that match. It will take into account current locale the app is running in, or use `locale` if provided. |
| **Parameters**                                       | <ul><li><code>key</code>    - The key to look up.</li><li><code>locale</code> - The locale (defaults to current FCPX locale).</li></ul> |
| **Returns**                                          | <ul><li>The array of keys with a matching string.</li></ul> |
| **Notes**                                            | <ul><li>This method may be very inefficient, since it has to search through every possible key/value pair to find matches. It is not recommended that this is used in production.</li></ul> |

#### [keywordEditor](#keywordeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:keywordEditor() -> keywordEditor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Final Cut Pro Keyword Editor |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Final Cut Pro Keyword Editor</li></ul> |

#### [launch](#launch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:launch([waitSeconds], [path]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Launches Final Cut Pro, or brings it to the front if it was already running. |
| **Parameters**                                       | <ul><li><code>waitSeconds</code> - If provided, the number of seconds to wait until the launch                   completes. If <code>nil</code>, it will return immediately.</li><li><code>path</code>        - An optional full path to an application without an extension                   (i.e <code>/Applications/Final Cut Pro 10.3.4</code>). This allows you to                   load previous versions of the application.</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [media](#media)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:media() -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the MediaBrowser instance, whether it is in the primary or secondary window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the MediaBrowser</li></ul> |

#### [mediaImport](#mediaimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:mediaImport() -> mediaImport object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Final Cut Pro Media Import Window |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Final Cut Pro Media Import Window</li></ul> |

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:menu() -> cp.app.menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `cp.app.menu` for FCP. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.app.menu</code> for the app.</li></ul> |

#### [notifier](#notifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:notifier() -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a notifier that is tracking the application UI element. It has already been started. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The notifier.</li></ul> |

#### [openLibrary](#openlibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:openLibrary(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to open a file at the specified absolute `path`. |
| **Parameters**                                       | <ul><li>path  - The path to the FCP Library to open.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> if not.</li></ul> |

#### [plugins](#plugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:plugins() -> cp.apple.finalcutpro.plugins` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the plugins manager for the app. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The plugins manager.</li></ul> |

#### [preferencesWindow](#preferenceswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:preferencesWindow() -> preferenceWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Final Cut Pro Preferences Window |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Preferences Window</li></ul> |

#### [primaryWindow](#primarywindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:primaryWindow() -> primaryWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Final Cut Pro Preferences Window |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Primary Window</li></ul> |

#### [quit](#quit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:quit([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Quits Final Cut Pro, if it's running. |
| **Parameters**                                       | <ul><li>waitSeconds      - The number of seconds to wait for the quit to complete.</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [scanPlugins](#scanplugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:scanPlugins() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scan Final Cut Pro Plugins |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A MenuBar object</li></ul> |

#### [secondaryWindow](#secondarywindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:secondaryWindow() -> secondaryWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Final Cut Pro Preferences Window |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Secondary Window</li></ul> |

#### [selectLibrary](#selectlibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:selectLibrary(title) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to select an open library with the specified title. |
| **Parameters**                                       | <ul><li>title - The title of the library to select.</li></ul> |
| **Returns**                                          | <ul><li>The library row <code>axuielement</code>.</li></ul> |

#### [selectMenu](#selectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:selectMenu(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects a Final Cut Pro Menu Item based on the list of menu titles in English. |
| **Parameters**                                       | <ul><li><code>path</code>       - The list of menu items you'd like to activate, for example:           select("View", "Browser", "as List")</li><li><code>options</code>    - (optional) The table of options. See <code>cp.app.menu:selectMenu(...)</code> for details.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the press was successful.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:show() -> cp.apple.finalcutpro` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Activate Final Cut Pro, if it is running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [string](#string)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:string(key[, locale[, quiet]]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Looks up an application string with the specified `key`. |
| **Parameters**                                       | <ul><li><code>key</code>    - The key to look up.</li><li><code>locale</code> - The locale code to use. Defaults to the current locale.</li><li><code>quiet</code>  - Optional boolean, defaults to <code>false</code>. If <code>true</code>, no warnings are logged for missing keys.</li></ul> |
| **Returns**                                          | <ul><li>The requested string or <code>nil</code> if the application is not running.</li></ul> |

#### [timeline](#timeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:timeline() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Timeline instance, whether it is in the primary or secondary window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the Timeline</li></ul> |

#### [toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:toolbar() -> PrimaryToolbar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Primary Toolbar - the toolbar at the top of the Primary Window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the PrimaryToolbar</li></ul> |

#### [transitions](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:transitions() -> TransitionsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the TransitionsBrowser instance, whether it is in the primary or secondary window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the TransitionsBrowser</li></ul> |

