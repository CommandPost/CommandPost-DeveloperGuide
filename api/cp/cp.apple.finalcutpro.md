# [docs](index.md) » cp.apple.finalcutpro
---

Represents the Final Cut Pro application, providing functions that allow different tasks to be accomplished.

Generally, you will `require` the `cp.apple.finalcutpro` module to import it, like so:

```lua
local fcp = require "cp.apple.finalcutpro"
```

Then, there are the `UpperCase` files, which represent the application itself:

* `MenuBar` 	            - The main menu bar.
* `prefs/PreferencesWindow` - The preferences window.
* etc...

The `fcp` variable is the root application. It has functions which allow you to perform tasks or access parts of the UI. For example, to open the `Preferences` window, you can do this:

```lua
fcp.preferencesWindow:show()
```

In general, as long as Final Cut Pro is running, actions can be performed directly, and the API will perform the required operations to achieve it. For example, to toggle the 'Create Optimized Media' checkbox in the 'Import' section of the 'Preferences' window, you can simply do this:

```lua
fcp.preferencesWindow.importPanel:toggleCreateOptimizedMedia()
```

The API will automatically open the `Preferences` window, navigate to the 'Import' panel and toggle the checkbox.

The `UpperCase` classes also have a variety of `UI` methods. These will return the `axuielement` for the relevant GUI element, if it is accessible. If not, it will return `nil`. These allow direct interaction with the GUI if necessary. It's most useful when adding new functions to `UpperCase` files for a particular element.

This can also be used to 'wait' for an element to be visible before performing a task. For example, if you need to wait for the `Preferences` window to finish loading before doing something else, you can do this with the [just](cp.just.md) library:

```lua
local just = require "cp.just"

local prefsWindow = fcp.preferencesWindow

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
if fcp.preferencesWindow:isShowing() then
	-- it's open!
else
	-- it's closed!
end
```

**Delegates to:** [app](cp.apple.finalcutpro.app.md), [menu](cp.app.menu.md)

Note: All values/methods/props from delegates can be accessed directly from the `cp.apple.finalcutpro` instance. For example:

```lua
fcp.app:UI() == fcp:UI() -- the same `cp.prop` result.
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
 * [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
 * [EVENT_DESCRIPTION_PATH](#event_description_path)
 * [FLEXO_LANGUAGES](#flexo_languages)
 * [PASTEBOARD_UTI](#pasteboard_uti)
 * [preferences](#preferences)
 * [WORKSPACES_PATH](#workspaces_path)
* Variables - Configurable values
 * [activeCommandSet](#activecommandset)
 * [customWorkspaces](#customworkspaces)
 * [openAndSavePanelDefaultPath](#openandsavepaneldefaultpath)
 * [selectedWorkspace](#selectedworkspace)
* Functions - API calls offered directly by the extension
 * [commandSet](#commandset)
 * [matches](#matches)
 * [matches](#matches)
 * [userCommandSetPath](#usercommandsetpath)
 * [workflowExtensions](#workflowextensions)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Color](#color)
 * [TranscodeMedia](#transcodemedia)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activeCommandSetPath](#activecommandsetpath)
 * [alert](#alert)
 * [audioEnhancements](#audioenhancements)
 * [audioLanes](#audiolanes)
 * [backgroundTasksDialog](#backgroundtasksdialog)
 * [browser](#browser)
 * [color](#color)
 * [colorBoard](#colorboard)
 * [colorCorrection](#colorcorrection)
 * [commandEditor](#commandeditor)
 * [contentUI](#contentui)
 * [contentUI](#contentui)
 * [deselectAll](#deselectall)
 * [effects](#effects)
 * [effects](#effects)
 * [eventViewer](#eventviewer)
 * [exportDialog](#exportdialog)
 * [findAndReplaceTitleText](#findandreplacetitletext)
 * [fullScreenWindow](#fullscreenwindow)
 * [generators](#generators)
 * [inspector](#inspector)
 * [inspectorUnits](#inspectorunits)
 * [isFrontmost](#isfrontmost)
 * [isInstalled](#isinstalled)
 * [isModalDialogOpen](#ismodaldialogopen)
 * [isPlaying](#isplaying)
 * [isPlaying](#isplaying)
 * [isRunning](#isrunning)
 * [isShowing](#isshowing)
 * [isSupported](#issupported)
 * [isUnsupported](#isunsupported)
 * [keywordEditor](#keywordeditor)
 * [libraries](#libraries)
 * [media](#media)
 * [mediaImport](#mediaimport)
 * [pan](#pan)
 * [preferencesWindow](#preferenceswindow)
 * [preset](#preset)
 * [primaryWindow](#primarywindow)
 * [resetDialogWarnings](#resetdialogwarnings)
 * [secondaryWindow](#secondarywindow)
 * [textArea](#textarea)
 * [textLayerLeft](#textlayerleft)
 * [textLayerRight](#textlayerright)
 * [timeDisplay](#timedisplay)
 * [timeline](#timeline)
 * [toolbar](#toolbar)
 * [transcodeMedia](#transcodemedia)
 * [transitions](#transitions)
 * [UI](#ui)
 * [validateAudioUnits](#validateaudiounits)
 * [viewer](#viewer)
 * [volume](#volume)
 * [windowsUI](#windowsui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activeLibraryPaths](#activelibrarypaths)
 * [closeLibrary](#closelibrary)
 * [defaultCommandSetPath](#defaultcommandsetpath)
 * [doShortcut](#doshortcut)
 * [getCommandShortcuts](#getcommandshortcuts)
 * [getPath](#getpath)
 * [hide](#hide)
 * [importXML](#importxml)
 * [isSupportedLocale](#issupportedlocale)
 * [keysWithString](#keyswithstring)
 * [launch](#launch)
 * [openLibrary](#openlibrary)
 * [plugins](#plugins)
 * [quit](#quit)
 * [recentLibraryNames](#recentlibrarynames)
 * [recentLibraryPaths](#recentlibrarypaths)
 * [scanPlugins](#scanplugins)
 * [selectLibrary](#selectlibrary)
 * [show](#show)
 * [string](#string)
 * [userCommandSets](#usercommandsets)

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

#### [openAndSavePanelDefaultPath](#openandsavepaneldefaultpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:openAndSavePanelDefaultPath <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A string containing the default open/save panel path. |

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

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.TranscodeMedia.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is an `TranscodeMedia` instance. |
| **Parameters**                                       | <ul><li>element       - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches the pattern for a <code>Viewer</code> <code>TranscodeMedia</code>.</li></ul> |

#### [userCommandSetPath](#usercommandsetpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.userCommandSetPath() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the path where User Command Set files are stored. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A path as a string or <code>nil</code> if the folder doesn't exist.</li></ul> |

#### [workflowExtensions](#workflowextensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.workflowExtensions() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the names of all the installed Workflow Extensions. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of Workflow Extension names</li></ul> |

### Constructors

#### [Color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Color(app) -> Color` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Color` instance. |
| **Parameters**                                       | <ul><li>app - The Final Cut Pro app instance.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Color</code>.</li></ul> |

#### [TranscodeMedia](#transcodemedia)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.TranscodeMedia(viewer)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `TranscodeMedia` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>TranscodeMedia</code>.</li></ul> |

### Fields

#### [activeCommandSetPath](#activecommandsetpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.activeCommandSetPath <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets the 'Active Command Set' value from the Final Cut Pro preferences |

#### [alert](#alert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.alert <cp.ui.Alert>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Provides basic access to any 'alert' dialog windows in the app. |

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

#### [backgroundTasksDialog](#backgroundtasksdialog)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.backgroundTasksDialog <cp.apple.finalcutpro.main.BackgroundTasksDialog>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [BackgroundTasksDialog](cp.apple.finalcutpro.main.BackgroundTasksDialog.md) dialog window. |

#### [browser](#browser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser <cp.apple.finalcutpro.main.Browser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Browser](cp.apple.finalcutpro.main.Browser.md) instance, whether it is in the primary or secondary window. |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.color <ColorInspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The ColorInspector instance from the primary window |

#### [colorBoard](#colorboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.colorBoard <ColorBoard>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The ColorBoard instance from the primary window |

#### [colorCorrection](#colorcorrection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.presfs.GeneralPanel.colorCorrection <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Color Correction" `PopUpButton`. |

#### [commandEditor](#commandeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.commandEditor <CommandEditor>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Final Cut Pro Command Editor |

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

#### [effects](#effects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.effects <cp.apple.finalcutpro.main.EffectsBrowser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The EffectsBrowser instance, whether it is in the primary or secondary window. |

#### [eventViewer](#eventviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.eventViewer <cp.apple.finalcutpro.viewer.Viewer>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Event [Viewer](cp.apple.finalcutpro.viewer.Viewer.md) instance, whether it is in the primary or secondary window. |

#### [exportDialog](#exportdialog)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.exportDialog <cp.apple.finalcutpro.main.ExportDialog>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Final Cut Pro Export Dialog Box |

#### [findAndReplaceTitleText](#findandreplacetitletext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.findAndReplaceTitleText <cp.apple.finalcutpro.main.FindAndReplaceTitleText>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [FindAndReplaceTitleText](cp.apple.finalcutpro.main.FindAndReplaceTitleText.md) dialog window. |

#### [fullScreenWindow](#fullscreenwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.fullScreenWindow <FullScreenWindow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the Final Cut Pro Full Screen Window (usually triggered by Cmd+Shift+F) |

#### [generators](#generators)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.generators <cp.apple.finalcutpro.main.GeneratorsBrowser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The GeneratorsBrowser instance, whether it is in the primary or secondary window. |

#### [inspector](#inspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector <cp.apple.finalcutpro.inspector.Inspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Inspector](cp.apple.finalcutpro.inspector.Inspector.md) instance from the primary window. |

#### [inspectorUnits](#inspectorunits)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.presfs.GeneralPanel.inspectorUnits <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Inspector Units" `PopUpButton`. |

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

#### [isPlaying](#isplaying)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer.isPlaying <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The 'playing' status of the viewer. If true, it is playing, if not it is paused. |

#### [isPlaying](#isplaying)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.ControlBar.isPlaying <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The 'playing' status of the viewer. If true, it is playing, if not it is paused. |

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

#### [keywordEditor](#keywordeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.keywordEditor <KeywordEditor>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Final Cut Pro Keyword Editor |

#### [libraries](#libraries)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.libraries <cp.apple.finalcutpro.main.LibrariesBrowser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [LibrariesBrowser](cp.apple.finalcutpro.main.LibrariesBrowser.md) instance, whether it is in the primary or secondary window. |

#### [media](#media)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.media <cp.apple.finalcutpro.main.MediaBrowser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The MediaBrowser instance, whether it is in the primary or secondary window. |

#### [mediaImport](#mediaimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.mediaImport <MediaImport>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Final Cut Pro Media Import Window |

#### [pan](#pan)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.VideoInspector.pan <cp.prop: PropertyRow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Pan |

#### [preferencesWindow](#preferenceswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.preferencesWindow <PreferencesWindow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Final Cut Pro Preferences Window |

#### [preset](#preset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.TextInspector.preset <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The preset popup found at the top of the inspector. |

#### [primaryWindow](#primarywindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.primaryWindow <cp.apple.finalcutpro.main.PrimaryWindow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Final Cut Pro Primary Window |

#### [resetDialogWarnings](#resetdialogwarnings)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.presfs.GeneralPanel.resetDialogWarnings <cp.ui.Buton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Reset Dialog warnings" `Button`. |

#### [secondaryWindow](#secondarywindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.secondaryWindow <cp.apple.finalcutpro.main.SecondaryWindow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Final Cut Pro Preferences Window |

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

#### [timeDisplay](#timedisplay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.presfs.GeneralPanel.timeDisplay <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Time Display" `PopUpButton`. |

#### [timeline](#timeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline <Timeline>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Timeline instance, whether it is in the primary or secondary window. |

#### [toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.toolbar <cp.apple.finalcutpro.main.PrimaryToolbar>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Primary Toolbar - the toolbar at the top of the Primary Window. |

#### [transcodeMedia](#transcodemedia)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.transcodeMedia <cp.apple.finalcutpro.main.TranscodeMedia>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [TranscodeMedia](cp.apple.finalcutpro.main.TranscodeMedia.md) sheet. |

#### [transitions](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.transitions <cp.apple.finalcutpro.main.EffectsBrowser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Transitions `EffectsBrowser` instance, whether it is in the primary or secondary window. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.UI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Final Cut Pro `axuielement`, if available. |

#### [validateAudioUnits](#validateaudiounits)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.presfs.GeneralPanel.validateAudioUnits <cp.ui.Buton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Validate Audio Units" `Button`. |

#### [viewer](#viewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer <cp.apple.finalcutpro.viewer.Viewer>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Viewer](cp.apple.finalcutpro.viewer.Viewer.md) instance, whether it is in the primary or secondary window. |

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

#### [closeLibrary](#closelibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:closeLibrary(title) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to close a library with the specified `title`. |
| **Parameters**                                       | <ul><li>title - The title of the FCP Library to close.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> if not.</li></ul> |

#### [defaultCommandSetPath](#defaultcommandsetpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:defaultCommandSetPath([locale]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the path to the 'Default' Command Set. |
| **Parameters**                                       | <ul><li><code>locale</code> - The optional locale to use. Defaults to the <a href="#currentLocale">current locale</a>.</li></ul> |
| **Returns**                                          | <ul><li>The 'Default' Command Set path, or <code>nil</code> if an error occurred</li></ul> |

#### [doShortcut](#doshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:doShortcut(whichShortcut) -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Perform a Final Cut Pro Keyboard Shortcut |
| **Parameters**                                       | <ul><li>whichShortcut - As per the Command Set name</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code> that will perform the shortcut when executed.</li></ul> |

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

#### [launch](#launch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:launch([waitSeconds], [path]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Launches Final Cut Pro, or brings it to the front if it was already running. |
| **Parameters**                                       | <ul><li><code>waitSeconds</code> - If provided, the number of seconds to wait until the launch                   completes. If <code>nil</code>, it will return immediately.</li><li><code>path</code>        - An optional full path to an application without an extension                   (i.e <code>/Applications/Final Cut Pro 10.3.4</code>). This allows you to                   load previous versions of the application.</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

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

#### [quit](#quit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:quit([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Quits Final Cut Pro, if it's running. |
| **Parameters**                                       | <ul><li>waitSeconds      - The number of seconds to wait for the quit to complete.</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [recentLibraryNames](#recentlibrarynames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:recentLibraryNames() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets a table of all the recent library names (that are accessible). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing any recent library names.</li></ul> |

#### [recentLibraryPaths](#recentlibrarypaths)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:recentLibraryPaths() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets a table of all the recent library paths (that are accessible). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing any recent library paths.</li></ul> |

#### [scanPlugins](#scanplugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:scanPlugins() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scan Final Cut Pro Plugins |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A MenuBar object</li></ul> |

#### [selectLibrary](#selectlibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:selectLibrary(title) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to select an open library with the specified title. |
| **Parameters**                                       | <ul><li>title - The title of the library to select.</li></ul> |
| **Returns**                                          | <ul><li>The library row <code>axuielement</code>.</li></ul> |

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

#### [userCommandSets](#usercommandsets)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro:userCommandSets() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the names of all of the user command sets. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of user command sets as strings.</li></ul> |

