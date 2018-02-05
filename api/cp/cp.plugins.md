# [docs](index.md) » cp.plugins
---

This is a simple plugin manager.

## Functions

It has a few core functions:

### `plugins.init(...)`

This function will load all enabled plugins in the specified 'parent' folders. For example:

```lua
local plugins = require("cp.plugins")
plugins.init("~/Library/Application Support/CommandPost/Plugins")
```

This will load all plugins in the current user's `Library/Application Support/CommandPost/Plugins` folder.

### `cp.plugins.getPluginModule(id)`

Once the plugins have been loaded, the module can be accessed by their ID via the `getPluginModule(id)` function. It will return the module returned by the plugin's `init` function. This can also be done via the default function for the library. Eg:

```lua
plugins("my.plugin.id").doSomething()
```

## Plugin Modules

Plugins typically have two parts:
1. The plugin table, which defines details about the plugin, and
2. The module, or result, which could be anything, which is returned from the `init` function.


A plugin file should return a `plugin` table that allows the plugin to be initialised. The table will look something like this:

```lua
local module = {}

local module.init(otherPlugin)
    -- do stuff with otherPlugin here
end

local plugin = {
    id = "my.plugin.id",
    group = "foo",
    dependencies = {
        ["some.other.plugin"] = "otherPlugin",
    },
}

function plugin.init(dependencies)
   -- do stuff to initialise the module here
   module.init(dependencies.otherPlugin)
   return module
}

function plugin.postInit(dependencies)
   -- do stuff that will happen after all plugins have been initialised.
end
```

As you can see above, plugin module can have a few simple functions and properties. The key ones are:

### `plugin.id`
This is a unique ID for the plugin. It is used to load the plugin externally, as well as to define dependencies between plugins.

### `plugin.group`
This is the group ID for the plugin. This is used to group plugins visually in the Properties panel for Plugins.

### `plugin.required`
This optional property can be specified for plugins which should never be disabled. This should only be set for plugins which will break the application if disabled.

### `plugin.dependencies`

This is a table with the list of other plugins that this plugin requires to be loaded prior to this plugin. Be careful of creating infinite loops of dependencies - we don't check for them currently!

It is defined like so:

```lua
plugin.dependencies = {
    "cp.plugins.myplugin",
    ["cp.plugins.otherplugin"] = "otherPlugin"
}

As you can see, there are two ways of declaring a dependency. The first is with just the plugin ID, the second has an alias.

These can be accessed in the `init` and `postInit` functions like so:

```lua
function plugin.init(dependencies)
   local myPlugin = dependencies["cp.plugins.myplugin"]
   local otherPlugin = dependencies.otherPlugin -- or dependencies["cp.plugins.otherplugin"]
end
```

A plugin will only have its `init` function called after its dependencies have successfully had their `init` functions called. Additionally, if a plugin has a `postInit`, all declared `postInits` for dependencies will have been called prior to the plugin's `postInit` function.

### `function plugin.init(dependencies[, environment]) -> module`

This function is basically required. It will be executed when the plugin is initialised. The `dependencies` parameter is a table containing the list of dependencies that the plugin defined via the `dependencies` property. The `environment` provides access to resources such as images, HTML files, or other lua modules that are bundled with the plugin. See `Simple vs Complex Plugins` below.
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

## Simple vs Complex Plugins

There are two types of plugin structures supported. The Simple version is a single `.lua` file that matches the above format for `plugin`. The Complex version is a folder containing an `init.lua` file that matches the above format.

The key advantage of Complex Plugins is that the folder can contain other resources, such as images, HTML templates, or other `.lua` files - including 3rd-party libraries if desired. These can be accessed via two main mechanisms:

1. The second `environment` parameter in the `init` function. This is a [cp.plugins.env](cp.plugins.env.md) table, which provides access to files and templates inside the plugin folder. See the [documentation](cp.plugins.env.md) for details.
2. The standard `require` method will allow loading of `*.lua` files inside the plugin from the `init.lua`.

For example, if you have a file called `foo.lua` in your folder, it can be `required` like so:

```lua
local foo = require("foo")
```

You do not have to know anything about where the plugin folder is stored, or use the plugin ID. Just use the local file path within the plugin. If you have another file in a `foo` folder called `bar.lua`, it can be loaded via:

```lua
local fooBar = require("foo.bar")
```

These modules will not be accessible to other plugins or to the main application. They are only available to code inside the plugin.

## Submodules
 * [cp.plugins.env](cp.plugins.env.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [CACHE](#cache)
 * [SETTINGS_DISABLED](#settings_disabled)
 * [SLOW_PLUGIN_WARNING_THRESHOLD](#slow_plugin_warning_threshold)
* Variables - Configurable values
 * [IDS](#ids)
* Functions - API calls offered directly by the extension
 * [addDependent](#adddependent)
 * [disable](#disable)
 * [enable](#enable)
 * [getDependents](#getdependents)
 * [getPlugin](#getplugin)
 * [getPluginIds](#getpluginids)
 * [getPluginModule](#getpluginmodule)
 * [getPlugins](#getplugins)
 * [init](#init)
 * [initPlugin](#initplugin)
 * [initPlugins](#initplugins)
 * [isDisabled](#isdisabled)
 * [loadComplexPlugin](#loadcomplexplugin)
 * [loadDependencies](#loaddependencies)
 * [loadSimplePlugin](#loadsimpleplugin)
 * [postInitPlugin](#postinitplugin)
 * [postInitPlugins](#postinitplugins)
 * [scanDirectory](#scandirectory)
 * [watchPluginPaths](#watchpluginpaths)

## API Documentation

### Constants

#### [CACHE](#cache)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.CACHE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Plugin Cache                                                                                         |

#### [SETTINGS_DISABLED](#settings_disabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.SETTINGS_DISABLED -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Plugin Disabled Code                                                                                         |

#### [SLOW_PLUGIN_WARNING_THRESHOLD](#slow_plugin_warning_threshold)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.SLOW_PLUGIN_WARNING_THRESHOLD -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Slow Plugin Warning Threshold                                                                                         |

### Variables

#### [IDS](#ids)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.IDS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Plugin Status Codes                                                                                         |

### Functions

#### [addDependent](#adddependent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.addDependent(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds the `dependentPlugin` as a dependent of the plugin with the specified id.                                                                                         |
| **Parameters**                                       | <ul><li>`id`                 - The plugin package ID.</li><li>`dependentPlugin`    - The plugin which is a dependent</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [disable](#disable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.disable(id) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disabled the plugin with the specified ID and reloads the application.                                                                                         |
| **Parameters**                                       | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the plugin was disabled, or `false` if it could not be disabled.</li></ul>          |

#### [enable](#enable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.enable(id) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enables the plugin with the specified ID, and reloads the application.                                                                                         |
| **Parameters**                                       | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the plugin had been disabled and is now enabled.</li></ul>          |

#### [getDependents](#getdependents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.getDependents(pluginId)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieves the list of dependent plugins for the specified plugin id.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`      - The plugin ID.</li></ul> |
| **Returns**                                          | <ul><li>The table of dependents.</li></ul>          |

#### [getPlugin](#getplugin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.getPlugin(id) -> plugin` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieves a plugin from the cache by ID.                                                                                         |
| **Parameters**                                       | <ul><li>id - The ID of the plugin you want to get</li></ul> |
| **Returns**                                          | <ul><li>The plugin</li></ul>          |

#### [getPluginIds](#getpluginids)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.getPluginIds() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieves an array of the loaded plugin IDs.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the list of plugin IDs.</li></ul>          |

#### [getPluginModule](#getpluginmodule)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.getPluginModule(id) -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an initialised plugin result with the specified `id`.                                                                                         |
| **Parameters**                                       | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                          | <ul><li>the result of the plugin's `init(...)` function call.</li></ul>          |

#### [getPlugins](#getplugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.getPlugins() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieves an array of details about the set of loaded plugins.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the list of plugins.</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.init(paths) -> cp.plugins` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the plugin loader to look in the specified file paths for plugins.                                                                                         |
| **Parameters**                                       | <ul><li>`paths` - An array of paths to search for plugins in.</li></ul> |
| **Returns**                                          | <ul><li>`cp.plugins` - The module.</li></ul>          |

#### [initPlugin](#initplugin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.initPlugin(id) -> module` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises a specific plugin with the specified path.                                                                                         |
| **Parameters**                                       | <ul><li>`id` - The LUA package to look in</li></ul> |
| **Returns**                                          | <ul><li>the result of the plugin's `init(...)` function call.</li></ul>          |

#### [initPlugins](#initplugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.initPlugins() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises all registered plugins.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [isDisabled](#isdisabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.isDisabled(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the specified plugin ID is disabled.                                                                                         |
| **Parameters**                                       | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the plugin is disabled.</li></ul>          |

#### [loadComplexPlugin](#loadcomplexplugin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.loadComplexPlugin(path) -> plugin` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Loads a 'complex' plugin, which is a folder containing an `init.lua` file.                                                                                         |
| **Parameters**                                       | <ul><li>`path` - The plugin package ID.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the plugin is successfully post-initialised.</li></ul>          |

#### [loadDependencies](#loaddependencies)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.loadDependencies(plugin) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Loads the list of dependencies for the provided plugin.                                                                                         |
| **Parameters**                                       | <ul><li>`plugin` - The plugin object</li></ul> |
| **Returns**                                          | <ul><li>an array of the dependencies required by the plugin, or `nil` if any could not be loaded.</li></ul>          |

#### [loadSimplePlugin](#loadsimpleplugin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.loadSimplePlugin(id) -> plugin` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Loads a 'simple' plugin, where it is defined by a single LUA script.                                                                                         |
| **Parameters**                                       | <ul><li>`path` - The plugin package ID.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the plugin is successfully post-initialised.</li></ul>          |

#### [postInitPlugin](#postinitplugin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.postInitPlugin(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Runs any post-initialisation functions declared for the specified plugin ID.                                                                                         |
| **Parameters**                                       | <ul><li>`id` - The plugin package ID.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the plugin is successfully post-initialised.</li></ul>          |

#### [postInitPlugins](#postinitplugins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.postInitPlugins() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs any post-initialisation required for plugins.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [scanDirectory](#scandirectory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.scanDirectory(directoryPath) -> cp.plugins` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Scans the specified directory and loads any plugins in the directory,                                                                                         |
| **Parameters**                                       | <ul><li>`directoryPath` - The path to the directory to scan.</li></ul> |
| **Returns**                                          | <ul><li>boolean - `true` if the path was loaded successfully, false if there were any issues.</li></ul>          |

#### [watchPluginPaths](#watchpluginpaths)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.watchPluginPaths() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Watches the plugin paths for changes and reloads the  application if any change.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

