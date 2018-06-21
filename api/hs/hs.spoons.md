# [docs](index.md) » hs.spoons
---

Utility and management functions for Spoons
Spoons are Lua plugins for Hammerspoon.
See http://www.hammerspoon.org/Spoons/ for more information

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [bindHotkeysToSpec](#bindhotkeystospec)
 * [isInstalled](#isinstalled)
 * [isLoaded](#isloaded)
 * [list](#list)
 * [newSpoon](#newspoon)
 * [resourcePath](#resourcepath)
 * [scriptPath](#scriptpath)
 * [use](#use)

## API Documentation

### Methods

#### [bindHotkeysToSpec](#bindhotkeystospec)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.bindHotkeysToSpec(def, map) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Map a number of hotkeys according to a definition table                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">def - table containing name-to-function definitions for the hotkeys supported by the Spoon. Each key is a hotkey name, and its value must be a function that will be called when the hotkey is invoked.</li><li markdown="1">map - table containing name-to-hotkey definitions, as supported by [bindHotkeys in the Spoon API](https://github.com/Hammerspoon/hammerspoon/blob/master/SPOONS.md#hotkeys). Not all the entries in `def` must be bound, but if any keys in `map` don't have a definition, an error will be produced.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [isInstalled](#isinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.isInstalled(name) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Check if a given Spoon is installed.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">name - Name of the Spoon to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">If the Spoon is installed, it returns a table with the Spoon information as returned by `list()`. Returns `nil` if the Spoon is not installed.</li></ul>          |

#### [isLoaded](#isloaded)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.isLoaded(name) -> boolean | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Check if a given Spoon is loaded.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">name - Name of the Spoon to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if the Spoon is loaded, `nil` otherwise.</li></ul>          |

#### [list](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.list() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a list of installed/loaded Spoons                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">onlyLoaded - only return loaded Spoons (skips those that are installed but not loaded). Defaults to `false`</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Table with a list of installed/loaded spoons (depending on the value of `onlyLoaded`). Each entry is a table with the following entries:</li><li markdown="1">  `name` - Spoon name</li><li markdown="1">  `loaded` - boolean indication of whether the Spoon is loaded (`true`) or only installed (`false`)</li><li markdown="1">  `version` - Spoon version number. Available only for loaded Spoons.</li></ul>          |

#### [newSpoon](#newspoon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.newSpoon(name, basedir, metadata) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Create a skeleton for a new Spoon                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">name: name of the new spoon, without the `.spoon` extension</li><li markdown="1">basedir: (optional) directory where to create the template. Defaults to `~/.hammerspoon/Spoons`</li><li markdown="1">metadata: (optional) table containing metadata values to be inserted in the template. Provided values are merged with the defaults. Defaults to:</li><li markdown="1">   ```</li><li markdown="1">   {</li><li markdown="1">     version = "0.1",</li><li markdown="1">     author = "Your Name <your@email.org>",</li><li markdown="1">     homepage = "https://github.com/Hammerspoon/Spoons",</li><li markdown="1">     license = "MIT - https://opensource.org/licenses/MIT",</li><li markdown="1">     download_url = "https://github.com/Hammerspoon/Spoons/raw/master/Spoons/"..name..".spoon.zip"</li><li markdown="1">   }</li><li markdown="1">   ```</li><li markdown="1">template: (optional) absolute path of the template to use for the `init.lua` file of the new Spoon. Defaults to the `templates/init.tpl` file included with Hammerspoon.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The full directory path where the template was created, or `nil` if there was an error.</li></ul>          |

#### [resourcePath](#resourcepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.resourcePath(partial) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return full path of an object within a spoon directory, given its partial path.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">partial - path of a file relative to the Spoon directory. For example `images/img1.png` will refer to a file within the `images` directory of the Spoon.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Absolute path of the file. Note: no existence or other checks are done on the path.</li></ul>          |

#### [scriptPath](#scriptpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.scriptPath([n]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return path of the current spoon.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">n - (optional) stack level for which to get the path. Defaults to 2, which will return the path of the spoon which called `scriptPath()`</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">String with the path from where the calling code was loaded.</li></ul>          |

#### [use](#use)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.use(name, arg) -> boolean | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Declaratively load and configure a Spoon                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">name - the name of the Spoon to load (without the `.spoon` extension).</li><li markdown="1">arg - if provided, can be used to specify the configuration of the Spoon. The following keys are recognized (all are optional):</li><li markdown="1">  config - a table containing variables to be stored in the Spoon object to configure it. For example, `config = { answer = 42 }` will result in `spoon.<LoadedSpoon>.answer` being set to 42.</li><li markdown="1">  hotkeys - a table containing hotkey bindings. If provided, will be passed as-is to the Spoon's `bindHotkeys()` method. The special string `"default"` can be given to use the Spoons `defaultHotkeys` variable, if it exists.</li><li markdown="1">  fn - a function which will be called with the freshly-loaded Spoon object as its first argument.</li><li markdown="1">  loglevel - if the Spoon has a variable called `logger`, its `setLogLevel()` method will be called with this value.</li><li markdown="1">  start - if `true`, call the Spoon's `start()` method after configuring everything else.</li><li markdown="1">noerror - if `true`, don't log an error if the Spoon is not installed, simply return `nil`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if the spoon was loaded, `nil` otherwise</li></ul>          |

