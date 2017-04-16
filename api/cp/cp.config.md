# [docs](index.md) » cp.config
---

Manage CommandPost's constants and settings.

## Submodules
 * [cp.config.fileDroppedToDockIconCallback](cp.config.fileDroppedToDockIconCallback.md)
 * [cp.config.shutdownCallback](cp.config.shutdownCallback.md)
 * [cp.config.textDroppedToDockIconCallback](cp.config.textDroppedToDockIconCallback.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [appName](#appName)
 * [appVersion](#appVersion)
 * [assetsPath](#assetsPath)
 * [basePath](#basePath)
 * [bugReportEmail](#bugReportEmail)
 * [bundleID](#bundleID)
 * [bundledPluginsPath](#bundledPluginsPath)
 * [configPrefix](#configPrefix)
 * [iconPath](#iconPath)
 * [languagePath](#languagePath)
 * [menubarIconPath](#menubarIconPath)
 * [pluginPaths](#pluginPaths)
 * [processID](#processID)
 * [scriptPath](#scriptPath)
 * [sourceExtensions](#sourceExtensions)
 * [sourceWatcher](#sourceWatcher)
 * [userConfigRootPath](#userConfigRootPath)
 * [userPluginsPath](#userPluginsPath)
* Functions - API calls offered directly by the extension
 * [application](#application)
 * [get](#get)
 * [isFrontmost](#isFrontmost)
 * [reset](#reset)
 * [set](#set)

## API Documentation

### Constants

| [appName](#appName)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.appName`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The name of the Application                                                                     |

| [appVersion](#appVersion)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.appVersion`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Prefix used for Configuration Settings                                                                     |

| [assetsPath](#assetsPath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.assetsPath`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Path to where Application Assets are stored                                                                     |

| [basePath](#basePath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.basePath`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Path to where the Extensions & Plugins folders are stored.                                                                     |

| [bugReportEmail](#bugReportEmail)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.bugReportEmail`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Email address used for bug reports                                                                     |

| [bundleID](#bundleID)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.bundleID`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Application's Bundle ID                                                                     |

| [bundledPluginsPath](#bundledPluginsPath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.bundledPluginsPath`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The path to bundled plugins                                                                     |

| [configPrefix](#configPrefix)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.configPrefix`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Prefix used for Configuration Settings                                                                     |

| [iconPath](#iconPath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.iconPath`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Path to the Application Icon                                                                     |

| [languagePath](#languagePath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.languagePath`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Path to the Languages Folder                                                                     |

| [menubarIconPath](#menubarIconPath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.menubarIconPath`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Path to the Menubar Application Icon                                                                     |

| [pluginPaths](#pluginPaths)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.pluginPaths`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Table of Plugins Paths. Earlier entries take precedence.                                                                     |

| [processID](#processID)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.processID`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Application's Process ID                                                                     |

| [scriptPath](#scriptPath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.scriptPath`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Path to where Application Scripts are stored                                                                     |

| [sourceExtensions](#sourceExtensions)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.sourceExtensions`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Extensions for files which will trigger a reload when modified.                                                                     |

| [sourceWatcher](#sourceWatcher)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.sourceWatcher`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A `cp.sourcewatcher` that will watch for source files and reload CommandPost if any change.                                                                     |

| [userConfigRootPath](#userConfigRootPath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.userConfigRootPath`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The path to user configuration folders                                                                     |

| [userPluginsPath](#userPluginsPath)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.userPluginsPath`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The path to user plugins                                                                     |

### Functions

| [application](#application)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.application() -> hs.application object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Application as a hs.application object                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>hs.application object</li></ul>          |

| [get](#get)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.get() -> string or boolean or number or nil or table or binary data`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Loads a setting                                                                     |
| **Parameters**                              | <ul><li>key - A string containing the name of the setting</li><li>defaultValue - A default value if the setting doesn't already exist</li></ul> |
| **Returns**                                 | <ul><li>The value of the setting</li></ul>          |

| [isFrontmost](#isFrontmost)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.isFrontmost() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns whether or not the Application is front most                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if Application is front most otherwise `false`</li></ul>          |

| [reset](#reset)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.reset()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Resets all the settings for the Application                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [set](#set)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.config.set(key, value)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Saves a setting with common datatypes                                                                     |
| **Parameters**                              | <ul><li>key - A string containing the name of the setting</li><li>val - An optional value for the setting. Valid datatypes are:</li><li>  string</li><li>  number</li><li>  boolean</li><li>  nil</li><li>  table (which may contain any of the same valid datatypes)</li><li>if no value is provided, it is assumed to be nil</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>This function cannot set dates or raw data types</li></ul>                |

