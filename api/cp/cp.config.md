# [docs](index.md) » cp.config
---

Manage CommandPost's constants and settings.

## Submodules
 * [cp.config.dockIconClickCallback](cp.config.dockIconClickCallback.md)
 * [cp.config.fileDroppedToDockIconCallback](cp.config.fileDroppedToDockIconCallback.md)
 * [cp.config.shutdownCallback](cp.config.shutdownCallback.md)
 * [cp.config.textDroppedToDockIconCallback](cp.config.textDroppedToDockIconCallback.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [appBuild](#appbuild)
 * [appName](#appname)
 * [appVersion](#appversion)
 * [assetsPath](#assetspath)
 * [basePath](#basepath)
 * [bundledPluginsPath](#bundledpluginspath)
 * [bundleID](#bundleid)
 * [cachePath](#cachepath)
 * [configPrefix](#configprefix)
 * [iconPath](#iconpath)
 * [languagePath](#languagepath)
 * [menubarIconPath](#menubariconpath)
 * [pluginPaths](#pluginpaths)
 * [privacyPolicyURL](#privacypolicyurl)
 * [processID](#processid)
 * [scriptPath](#scriptpath)
 * [sourceExtensions](#sourceextensions)
 * [sourceWatcher](#sourcewatcher)
 * [translationURL](#translationurl)
 * [userConfigRootPath](#userconfigrootpath)
 * [userPluginsPath](#userpluginspath)
* Variables - Configurable values
 * [automaticScriptReloading](#automaticscriptreloading)
 * [watcher](#watcher)
* Functions - API calls offered directly by the extension
 * [application](#application)
 * [get](#get)
 * [prop](#prop)
 * [reset](#reset)
 * [set](#set)
 * [unwatch](#unwatch)
 * [watch](#watch)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [developerMode](#developermode)
 * [frontmost](#frontmost)

## API Documentation

### Constants

#### [appBuild](#appbuild)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.appBuild -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Application Build |

#### [appName](#appname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.appName -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The name of the Application |

#### [appVersion](#appversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.appVersion -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Application Version |

#### [assetsPath](#assetspath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.assetsPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Path to where Application Assets are stored |

#### [basePath](#basepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.basePath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Path to where the Extensions & Plugins folders are stored. |

#### [bundledPluginsPath](#bundledpluginspath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.bundledPluginsPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The path to bundled plugins |

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.bundleID -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Application's Bundle ID |

#### [cachePath](#cachepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.cachePath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The path to the CommandPost Cache folder. |

#### [configPrefix](#configprefix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.configPrefix -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Prefix used for Configuration Settings |

#### [iconPath](#iconpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.iconPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Path to the Application Icon |

#### [languagePath](#languagepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.languagePath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Path to the Languages Folder |

#### [menubarIconPath](#menubariconpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.menubarIconPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Path to the Menubar Application Icon |

#### [pluginPaths](#pluginpaths)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.pluginPaths -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of Plugins Paths. Earlier entries take precedence. |

#### [privacyPolicyURL](#privacypolicyurl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.privacyPolicyURL -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | URL for Privacy Policy |

#### [processID](#processid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.processID -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Application's Process ID |

#### [scriptPath](#scriptpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.scriptPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Path to where Application Scripts are stored |

#### [sourceExtensions](#sourceextensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.sourceExtensions -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Extensions for files which will trigger a reload when modified. |

#### [sourceWatcher](#sourcewatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.sourceWatcher -> SourceWatcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `cp.sourcewatcher` that will watch for source files and reload CommandPost if any change. |

#### [translationURL](#translationurl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.translationURL -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | URL for Translations |

#### [userConfigRootPath](#userconfigrootpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.userConfigRootPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The path to user configuration folders |

#### [userPluginsPath](#userpluginspath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.userPluginsPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The path to user plugins |

### Variables

#### [automaticScriptReloading](#automaticscriptreloading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.automaticScriptReloading <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Automatic Script Reloading. |

#### [watcher](#watcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.watcher() -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Config Watcher |

### Functions

#### [application](#application)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.application() -> hs.application object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the Application as a hs.application object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>hs.application object</li></ul> |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.get(key[, defaultValue]) -> string or boolean or number or nil or table or binary data` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Loads a setting |
| **Parameters**                                       | <ul><li>key - A string containing the name of the setting</li><li>defaultValue - A default value if the setting doesn't already exist</li></ul> |
| **Returns**                                          | <ul><li>The value of the setting</li></ul> |

#### [prop](#prop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.prop(key[, defaultValue]) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a `cp.prop` instance connected to the value of the specified key. When the value is modified, it will be notified. |
| **Parameters**                                       | <ul><li><code>key</code>             - The configuration setting key.</li><li><code>defaultValue</code>    - The default value if the key has not been set.</li></ul> |
| **Returns**                                          | <ul><li>A <code>cp.prop</code> instance for the key.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.reset()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Resets all the settings for the Application |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [set](#set)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.set(key, value)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Saves a setting with common datatypes |
| **Parameters**                                       | <ul><li><code>key</code>        - A string containing the name of the setting</li><li><code>value</code>      - An optional value for the setting. Valid datatypes are:</li><li>string</li><li>number</li><li>boolean</li><li>nil</li><li>table (which may contain any of the same valid datatypes)</li><li>if no value is provided, it is assumed to be nil</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This function cannot set dates or raw data types</li></ul> |

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.unwatch(id)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Unregisters the watcher with the specified ID. |
| **Parameters**                                       | <ul><li><code>id</code>     - The ID, originally returned from the <code>watch</code> function.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if a watcher with the ID existed and was successfully removed.</li></ul> |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.watch(events) -> id` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Watches for config events. |
| **Parameters**                                       | <ul><li><code>events</code> - a table containing functions for each event to watch for.</li></ul> |
| **Returns**                                          | <ul><li>a unique ID that can be used to <code>unwatch</code>.</li></ul> |
| **Notes**                                            | <ul><li>Supported events: ** <code>reset()</code>   - occurs after CommandPost's settings are reset.</li></ul> |

### Fields

#### [developerMode](#developermode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.developerMode <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | When `true`, the app is in developer mode. |

#### [frontmost](#frontmost)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.frontmost <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns whether or not the Application is frontmost. |

