# [docs](index.md) » cp.apple.finalcutpro.plugins
---

Scans an entire system for Final Cut Pro Effects, Generators, Titles & Transitions.

Usage:
```lua
    require("cp.apple.finalcutpro"):plugins():scan()
```

## Submodules
 * [cp.apple.finalcutpro.plugins.guiscan](cp.apple.finalcutpro.plugins.guiscan.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [appBuiltinPlugins](#appbuiltinplugins)
 * [appEdelEffects](#appedeleffects)
 * [audioUnitsCache](#audiounitscache)
 * [coreAudioPreferences](#coreaudiopreferences)
 * [types](#types)
* Variables - Configurable values
 * [outputReport](#outputreport)
* Functions - API calls offered directly by the extension
 * [clearCaches](#clearcaches)
 * [new](#new)
 * [scan](#scan)
 * [scanned](#scanned)
 * [scanSystemAudioUnits](#scansystemaudiounits)
 * [scanUserEffectsPresets](#scanusereffectspresets)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [audioEffects](#audioeffects)
 * [effectBundleStrings](#effectbundlestrings)
 * [effectStrings](#effectstrings)
 * [generators](#generators)
 * [init](#init)
 * [ofType](#oftype)
 * [registerPlugin](#registerplugin)
 * [reset](#reset)
 * [scanAll](#scanall)
 * [scanAppAudioEffectBundles](#scanappaudioeffectbundles)
 * [scanAppBuiltInPlugins](#scanappbuiltinplugins)
 * [scanAppEdelEffects](#scanappedeleffects)
 * [scanAppMotionTemplates](#scanappmotiontemplates)
 * [scanPluginCategoryDirectory](#scanplugincategorydirectory)
 * [scanPluginsDirectory](#scanpluginsdirectory)
 * [scanPluginThemeDirectory](#scanpluginthemedirectory)
 * [scanSystemMotionTemplates](#scansystemmotiontemplates)
 * [scanUserMotionTemplates](#scanusermotiontemplates)
 * [titles](#titles)
 * [transitions](#transitions)
 * [translateEffectBundle](#translateeffectbundle)
 * [unwatch](#unwatch)
 * [videoEffects](#videoeffects)
 * [watch](#watch)

## API Documentation

### Constants

#### [appBuiltinPlugins](#appbuiltinplugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.appBuiltinPlugins -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of built-in plugins |

#### [appEdelEffects](#appedeleffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.appEdelEffects -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of Built-in Soundtrack Pro EDEL Effects. |

#### [audioUnitsCache](#audiounitscache)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.audioUnitsCache -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Path to the Audio Units Cache |

#### [coreAudioPreferences](#coreaudiopreferences)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.coreAudioPreferences -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Core Audio Preferences File Path |

#### [types](#types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.types -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of the different Motion Template Extensions |

### Variables

#### [outputReport](#outputreport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.outputReport <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Set this to `true` via `_fcp:plugins():outputReport(true)` to enable reporting. |

### Functions

#### [clearCaches](#clearcaches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.clearCaches() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Clears any local caches created for tracking the plugins. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the caches have been cleared successfully.</li></ul> |
| **Notes**                                            | <ul><li>Does not uninstall any of the actual plugins.</li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.new(fcp) -> plugins object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new Plugins Object. |
| **Parameters**                                       | <ul><li>fcp - The <code>cp.apple.finalcutpro</code> object</li></ul> |
| **Returns**                                          | <ul><li>The plugins object</li></ul> |

#### [scan](#scan)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scan() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Scans Final Cut Pro for Effects, Transitions, Generators & Titles |
| **Parameters**                                       | <ul><li>fcp - the <code>cp.apple.finalcutpro</code> instance</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [scanned](#scanned)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins.scanned() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets if the system has been scanned. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> is scanned otherwise <code>false</code>.</li></ul> |

#### [scanSystemAudioUnits](#scansystemaudiounits)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanSystemAudioUnits(locale) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Scans for Validated Audio Units, and saves the results to a cache for faster subsequent startup times. |
| **Parameters**                                       | <ul><li>locale   - the locale to scan in.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [scanUserEffectsPresets](#scanusereffectspresets)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanUserEffectsPresets(locale) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Scans Final Cut Pro Effects Presets |
| **Parameters**                                       | <ul><li><code>locale</code>    - The locale to scan for.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:app() -> plugins` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `cp.apple.finalcutpro` object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro</code> object.</li></ul> |

#### [audioEffects](#audioeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:audioEffects([locale]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the 'audio effect' plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>A table of the available plugins.</li></ul> |

#### [effectBundleStrings](#effectbundlestrings)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:effectBundleStrings() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns all the Effect Bundle Strings. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The effect bundle strings in a table.</li></ul> |

#### [effectStrings](#effectstrings)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:effectStrings() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table of Effects Strings. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of effect strings.</li></ul> |

#### [generators](#generators)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:generators([locale]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the 'generator' plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>A table of the available plugins.</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:init() -> plugins` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Initialises the module. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The plugins object.</li></ul> |

#### [ofType](#oftype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:ofType(type[, locale]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the plugins of the specified type (`types.videoEffect`, etc.) and if provided, locale. |
| **Parameters**                                       | <ul><li><code>type</code>        - The plugin type. See <code>types</code> for the complete list.</li><li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>A table of the available plugins of the specified type.</li></ul> |

#### [registerPlugin](#registerplugin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:registerPlugin(path, type, categoryName, themeName, pluginName, locale) -> plugin` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Registers a plugin with the specified details. |
| **Parameters**                                       | <ul><li><code>path</code>           - The path to the plugin directory.</li><li><code>type</code>           - The type of plugin</li><li><code>categoryName</code>   - The category name, in the specified locale.</li><li><code>themeName</code>      - The theme name, in the specified locale. May be <code>nil</code> if not in a theme.</li><li><code>pluginName</code>     - The plugin name, in the specified locale.</li><li><code>locale</code>         - The <code>cp.i18n.localeID</code> or string code for same (e.g. "en", "fr", "de")</li></ul> |
| **Returns**                                          | <ul><li>The plugin object.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:reset() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resets all the cached plugins. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [scanAll](#scanall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanAll() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scans all supported locales, loading them into memory. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

#### [scanAppAudioEffectBundles](#scanappaudioeffectbundles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanAppAudioEffectBundles() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scans the Audio Effect Bundles directories. |
| **Parameters**                                       | <ul><li>directoryPath - Directory to scan</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [scanAppBuiltInPlugins](#scanappbuiltinplugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanAppBuiltInPlugins([locale]) -> None` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scan Built In Plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>    - The <code>cp.i18n.localeID</code> code to search for. Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [scanAppEdelEffects](#scanappedeleffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanAppEdelEffects() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scans for Soundtrack Pro EDEL Effects. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [scanAppMotionTemplates](#scanappmotiontemplates)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanAppMotionTemplates(locale) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scans for app-provided Final Cut Pro Plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>    - The locale to scan for.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [scanPluginCategoryDirectory](#scanplugincategorydirectory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanPluginCategoryDirectory(locale, path, plugin) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scans a folder as a plugin category folder. The contents will be folders that are either theme folders or actual plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>        - The locale to scan with.</li><li><code>path</code>            - The path to the plugin type directory</li><li><code>plugin</code>      - A table containing the plugin details collected so far.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the folder was scanned successfully.</li></ul> |

#### [scanPluginsDirectory](#scanpluginsdirectory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanPluginsDirectory(locale, path, filter) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scans a root plugins directory. Plugins directories have a standard structure which comes in two flavours: |
| **Parameters**                                       | <ul><li><code>locale</code>   - The locale code to scan for (e.g. "en" or "fr").</li><li><code>path</code>       - The path of the root plugin directory to scan.</li><li><code>checkFn</code>    - A function which will receive the path being scanned and return <code>true</code> if it should be scanned.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the plugin directory was successfully scanned.</li></ul> |

#### [scanPluginThemeDirectory](#scanpluginthemedirectory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanPluginThemeDirectory(locale, path, plugin) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scans a folder as a plugin theme folder. The contents will be plugin folders. |
| **Parameters**                                       | <ul><li><code>locale</code>        - The locale to scan with.</li><li><code>path</code>            - The path to the plugin type directory</li><li><code>plugin</code>          - A table containing the plugin details collected so far.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the folder was scanned successfully.</li></ul> |

#### [scanSystemMotionTemplates](#scansystemmotiontemplates)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanSystemMotionTemplates(locale) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scans for system-provided Final Cut Pro Plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>    - The locale to scan for.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [scanUserMotionTemplates](#scanusermotiontemplates)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:scanUserMotionTemplates(locale) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scans for user-provided Final Cut Pro Plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>    - The locale to scan for.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [titles](#titles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:titles([locale]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the 'title' plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>A table of the available plugins.</li></ul> |

#### [transitions](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:transitions([locale]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the 'transitions' plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>A table of the available plugins.</li></ul> |

#### [translateEffectBundle](#translateeffectbundle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:translateEffectBundle(input, locale) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Translates an Effect Bundle Item. |
| **Parameters**                                       | <ul><li>input - The original name</li><li>locale - The locale code you want to attempt to translate to</li></ul> |
| **Returns**                                          | <ul><li>The translated value for <code>input</code> in the specified locale, if present.</li></ul> |

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:unwatch(id) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Unwatches a watcher with a specific ID. |
| **Parameters**                                       | <ul><li>id - The ID of the watcher to stop watching.</li></ul> |
| **Returns**                                          | <ul><li>The watcher object.</li></ul> |

#### [videoEffects](#videoeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:videoEffects([locale]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the 'video effect' plugins. |
| **Parameters**                                       | <ul><li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li></ul> |
| **Returns**                                          | <ul><li>A table of the available plugins.</li></ul> |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.plugins:watch(events) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a watcher for the provided events table. |
| **Parameters**                                       | <ul><li>events - A table of events to watch.</li></ul> |
| **Returns**                                          | <ul><li>The watcher object</li></ul> |
| **Notes**                                            | <ul><li>The events can be: <strong> videoEffects </strong> audioEffects <strong> transitions </strong> titles ** generators</li></ul> |

