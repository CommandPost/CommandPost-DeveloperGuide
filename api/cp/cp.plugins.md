# [docs](index.md) » cp.plugins
---

This is a simple plugin manager.

## Functions

It has a few core functions:

### `plugins.init(...)`

This function will load all enabled plugins in the specified 'parent' package. For example, the default plugin path for CommandPost is `cp.plugins`. This directory contains a collection of `*.lua` files or subdirectories. To initialse the system to load this path, you would call:

```lua
local plugins = require("cp.modules.plugins")
plugins.init("cp.plugins")
```

### `plugins.loadPlugin(...)`

This function loads a plugin directly. If it has dependencies, the dependencies will also be loaded (if possible). If successful, the result of the plugin's `init(dependencies)` function will be returned.

### `plugins.loadPackage(...)`

This function will load a package of plugins. If the package contains sub-packages, they will be loaded recursively.

## Plugin Modules

A plugin file should return a `plugin` table that allows the plugin to be initialised.

A plugin module can have a few simple functions and properties. The key ones are:

### `function plugin.init(dependencies)`

If the `init(dependencies)` function is present, it will be executed when the plugin is loaded. The `dependencies` parameter is a table containing the list of dependencies that the plugin defined

### `plugin.dependencies` table

This is a table with the list of other plugins that this plugin requires to be loaded prior to this plugin. Be careful of creating infinite loops of dependencies - we don't check for them currently!

It is defined like so:

```lua
plugin.dependencies = {
	"cp.plugins.myplugin",
	["cp.plugins.otherplugin"] = "otherplugin"
}
```

As you may have noted, there are two ways to specify a plugin is required. Either by simply specifying it as an 'array' item (the first example) or as a key/value (the second example). Doing the later allows you to specify an alias for the dependency, which can be used in the `init(...)` function, like so:

```lua
local plugin = {}

plugin.dependencies = {
	"cp.plugins.myplugin",
	["cp.plugins.otherplugin"] = "otherplugin"
}

function plugin.init(dependencies)
	local myplugin = dependencies["cp.plugins.myplugin"]
	local otherplugin = dependencies.otherplugin

	-- do other stuff with the dependencies

	return myinstance
end

return plugin
```

## API Overview
* Functions - API calls offered directly by the extension
 * [disable](#disable)
 * [enable](#enable)
 * [getPlugin](#getPlugin)
 * [getPluginGroup](#getPluginGroup)
 * [getPluginIds](#getPluginIds)
 * [getPluginInfos](#getPluginInfos)
 * [getPluginStatus](#getPluginStatus)
 * [init](#init)
 * [initPlugin](#initPlugin)
 * [initPlugins](#initPlugins)
 * [isDisabled](#isDisabled)
 * [loadComplexPlugin](#loadComplexPlugin)
 * [loadDependencies](#loadDependencies)
 * [loadSimplePlugin](#loadSimplePlugin)
 * [postInitPlugin](#postInitPlugin)
 * [postInitPlugins](#postInitPlugins)
 * [scanDirectory](#scanDirectory)
 * [watchPluginPaths](#watchPluginPaths)

## API Documentation

### Functions

| [disable](#disable)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.disable(id) -> nothing`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Disabled the plugin with the specified ID and reloads the application.                                                                     |
| **Parameters**                              | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                 | <ul><li>nothing</li></ul>          |

| [enable](#enable)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.enable(id) -> nothing`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Enables the plugin with the specified ID, and reloads the application.                                                                     |
| **Parameters**                              | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                 | <ul><li>nothing</li></ul>          |

| [getPlugin](#getPlugin)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.getPlugin(id) -> value`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns an initialised plugin result with the specified `id`                                                                     |
| **Parameters**                              | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                 | <ul><li>the result of the plugin's `init(...)` function call.</li></ul>          |

| [getPluginGroup](#getPluginGroup)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.getPluginGroup(id) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the group for the specifed plugin ID.                                                                     |
| **Parameters**                              | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                 | <ul><li>the list of plugin IDs.</li></ul>          |

| [getPluginIds](#getPluginIds)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.getPluginIds() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Retrieves an array of the loaded plugin IDs.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the list of plugin IDs.</li></ul>          |

| [getPluginInfos](#getPluginInfos)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.getPluginInfos() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Retrieves an array of details about the set of loaded plugins.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the list of plugin infos.</li></ul>          |

| [getPluginStatus](#getPluginStatus)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.getPluginStatus(id) -> cp.plugins.status`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the status for the specified plugin ID.                                                                     |
| **Parameters**                              | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                 | <ul><li>the plugin status, or `nil` if the plugin has not been registered.</li></ul>          |

| [init](#init)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.init(ids) -> cp.plugins`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialises the plugin loader to look in the specified file paths for plugins.                                                                     |
| **Parameters**                              | <ul><li>`ids` - An array of paths to search for plugins in.</li></ul> |
| **Returns**                                 | <ul><li>`cp.plugins` - The module.</li></ul>          |

| [initPlugin](#initPlugin)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.initPlugin(id) -> instance`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialises a specific plugin with the specified path.                                                                     |
| **Parameters**                              | <ul><li>`id` - The LUA package to look in</li></ul> |
| **Returns**                                 | <ul><li>the result of the plugin's `init(...)` function call.</li></ul>          |

| [initPlugins](#initPlugins)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.initPlugins() -> nothing`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialises all registered plugins.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>Nothing</li></ul>          |

| [isDisabled](#isDisabled)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.isDisabled(id) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks if the specified plugin ID is disabled.                                                                     |
| **Parameters**                              | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                 | <ul><li>`true` if the plugin is disabled.</li></ul>          |

| [loadComplexPlugin](#loadComplexPlugin)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.loadComplexPlugin(id) -> plugin`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Loads a 'complex' plugin, which is a folder containing an `init.lua` file.                                                                     |
| **Parameters**                              | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                 | <ul><li>`true` if the plugin ias successfully post-initialised.</li></ul>          |

| [loadDependencies](#loadDependencies)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.loadDependencies(plugin) -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Loads the list of dependencies for the provided plugin.                                                                     |
| **Parameters**                              | <ul><li>`plugin` - The plugin object</li></ul> |
| **Returns**                                 | <ul><li>an array of the dependencies required by the plugin, or `nil` if any could not be loaded.</li></ul>          |

| [loadSimplePlugin](#loadSimplePlugin)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.loadSimplePlugin(id) -> plugin`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Loads a 'simple' plugin, where it is defined by a single LUA script.                                                                     |
| **Parameters**                              | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                 | <ul><li>`true` if the plugin ias successfully post-initialised.</li></ul>          |

| [postInitPlugin](#postInitPlugin)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.postInitPlugin(id) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Runs any post-initialisation functions declared for the specified plugin ID.                                                                     |
| **Parameters**                              | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                 | <ul><li>`true` if the plugin ias successfully post-initialised.</li></ul>          |

| [postInitPlugins](#postInitPlugins)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.postInitPlugins() -> nothing`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Performs any post-initialisation required for plugins.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>Nothing</li></ul>          |

| [scanDirectory](#scanDirectory)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.scanDirectory(directoryPath) -> cp.plugins`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Scans the specified directory and loads any plugins in the directory,                                                                     |
| **Parameters**                              | <ul><li>`directoryPath` - The path to the directory to scan.</li></ul> |
| **Returns**                                 | <ul><li>boolean - `true` if the path was loaded successfully, false if there were any issues.</li></ul>          |

| [watchPluginPaths](#watchPluginPaths)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.plugins.watchPluginPaths() -> nothing`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Watches the plugin paths for changes and reloads the  application if any change.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>Nothing</li></ul>          |

