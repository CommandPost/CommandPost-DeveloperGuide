# [docs](index.md) » cp.config
---

Manage CommandPost's constants and settings.

## Submodules
 * [cp.config.fileDroppedToDockIconCallback](cp.config.fileDroppedToDockIconCallback.md)
 * [cp.config.shutdownCallback](cp.config.shutdownCallback.md)
 * [cp.config.textDroppedToDockIconCallback](cp.config.textDroppedToDockIconCallback.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [appName](#appname)
 * [appVersion](#appversion)
 * [assetsPath](#assetspath)
 * [basePath](#basepath)
 * [bugReportEmail](#bugreportemail)
 * [bundleID](#bundleid)
 * [bundledPluginsPath](#bundledpluginspath)
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
 * [userConfigRootPath](#userconfigrootpath)
 * [userPluginsPath](#userpluginspath)
* Functions - API calls offered directly by the extension
 * [application](#application)
 * [get](#get)
 * [isFrontmost](#isfrontmost)
 * [reset](#reset)
 * [set](#set)

## API Documentation

### Constants

#### [appName](#appname)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.appName` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The name of the Application                                                                                         |

#### [appVersion](#appversion)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.appVersion` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Prefix used for Configuration Settings                                                                                         |

#### [assetsPath](#assetspath)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.assetsPath` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Path to where Application Assets are stored                                                                                         |

#### [basePath](#basepath)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.basePath` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Path to where the Extensions & Plugins folders are stored.                                                                                         |

#### [bugReportEmail](#bugreportemail)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.bugReportEmail` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Email address used for bug reports                                                                                         |

#### [bundleID](#bundleid)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.bundleID` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Application's Bundle ID                                                                                         |

#### [bundledPluginsPath](#bundledpluginspath)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.bundledPluginsPath` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The path to bundled plugins                                                                                         |

#### [configPrefix](#configprefix)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.configPrefix` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Prefix used for Configuration Settings                                                                                         |

#### [iconPath](#iconpath)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.iconPath` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Path to the Application Icon                                                                                         |

#### [languagePath](#languagepath)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.languagePath` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Path to the Languages Folder                                                                                         |

#### [menubarIconPath](#menubariconpath)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.menubarIconPath` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Path to the Menubar Application Icon                                                                                         |

#### [pluginPaths](#pluginpaths)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.pluginPaths` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of Plugins Paths. Earlier entries take precedence.                                                                                         |

#### [privacyPolicyURL](#privacypolicyurl)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.privacyPolicyURL` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | URL for Privacy Policy                                                                                         |

#### [processID](#processid)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.processID` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Application's Process ID                                                                                         |

#### [scriptPath](#scriptpath)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.scriptPath` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Path to where Application Scripts are stored                                                                                         |

#### [sourceExtensions](#sourceextensions)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.sourceExtensions` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Extensions for files which will trigger a reload when modified.                                                                                         |

#### [sourceWatcher](#sourcewatcher)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.sourceWatcher` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A `cp.sourcewatcher` that will watch for source files and reload CommandPost if any change.                                                                                         |

#### [userConfigRootPath](#userconfigrootpath)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.userConfigRootPath` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The path to user configuration folders                                                                                         |

#### [userPluginsPath](#userpluginspath)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.userPluginsPath` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The path to user plugins                                                                                         |

### Functions

#### [application](#application)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.application() -> hs.application object` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the Application as a hs.application object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>hs.application object</li></ul>          |

#### [get](#get)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.get() -> string or boolean or number or nil or table or binary data` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Loads a setting                                                                                         |
| **Parameters**                                       | <ul><li>key - A string containing the name of the setting</li><li>defaultValue - A default value if the setting doesn't already exist</li></ul> |
| **Returns**                                          | <ul><li>The value of the setting</li></ul>          |

#### [isFrontmost](#isfrontmost)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.isFrontmost() -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether or not the Application is front most                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if Application is front most otherwise `false`</li></ul>          |

#### [reset](#reset)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.reset()` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resets all the settings for the Application                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [set](#set)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.set(key, value)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves a setting with common datatypes                                                                                         |
| **Parameters**                                       | <ul><li>key - A string containing the name of the setting</li><li>val - An optional value for the setting. Valid datatypes are:</li><li>  string</li><li>  number</li><li>  boolean</li><li>  nil</li><li>  table (which may contain any of the same valid datatypes)</li><li>if no value is provided, it is assumed to be nil</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>This function cannot set dates or raw data types</li></ul>                |

