# [docs](index.md) » hs.spoons
---

Utility and management functions for Spoons
Spoons are Lua plugins for Hammerspoon.
See https://www.hammerspoon.org/Spoons/ for more information

## API Overview
* Functions - API calls offered directly by the extension
 * [bindHotkeysToSpec](#bindhotkeystospec)
 * [isInstalled](#isinstalled)
 * [isLoaded](#isloaded)
 * [list](#list)
 * [newSpoon](#newspoon)
 * [resourcePath](#resourcepath)
 * [scriptPath](#scriptpath)
 * [use](#use)

## API Documentation

### Functions

#### [bindHotkeysToSpec](#bindhotkeystospec)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.bindHotkeysToSpec(def, map) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Map a number of hotkeys according to a definition table |
| **Parameters**                                       | <ul><li>def - table containing name-to-function definitions for the hotkeys supported by the Spoon. Each key is a hotkey name, and its value must be a function that will be called when the hotkey is invoked.</li><li>map - table containing name-to-hotkey definitions and an optional message to be displayed via <code>hs.alert()</code> when the hotkey has been triggered, as supported by <a href="https://github.com/Hammerspoon/hammerspoon/blob/master/SPOONS.md#hotkeys">bindHotkeys in the Spoon API</a>. Not all the entries in <code>def</code> must be bound, but if any keys in <code>map</code> don't have a definition, an error will be produced.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [isInstalled](#isinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.isInstalled(name) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Check if a given Spoon is installed. |
| **Parameters**                                       | <ul><li>name - Name of the Spoon to check.</li></ul> |
| **Returns**                                          | <ul><li>If the Spoon is installed, it returns a table with the Spoon information as returned by <code>list()</code>. Returns <code>nil</code> if the Spoon is not installed.</li></ul> |

#### [isLoaded](#isloaded)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.isLoaded(name) -> boolean | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Check if a given Spoon is loaded. |
| **Parameters**                                       | <ul><li>name - Name of the Spoon to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the Spoon is loaded, <code>nil</code> otherwise.</li></ul> |

#### [list](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.list() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Return a list of installed/loaded Spoons |
| **Parameters**                                       | <ul><li>onlyLoaded - only return loaded Spoons (skips those that are installed but not loaded). Defaults to <code>false</code></li></ul> |
| **Returns**                                          | <ul><li>Table with a list of installed/loaded spoons (depending on the value of <code>onlyLoaded</code>). Each entry is a table with the following entries:</li><li><code>name</code> - Spoon name</li><li><code>loaded</code> - boolean indication of whether the Spoon is loaded (<code>true</code>) or only installed (<code>false</code>)</li><li><code>version</code> - Spoon version number. Available only for loaded Spoons.</li></ul> |

#### [newSpoon](#newspoon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.newSpoon(name, basedir, metadata, [template]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Create a skeleton for a new Spoon |
| **Parameters**                                       | <ul><li>name: name of the new spoon, without the <code>.spoon</code> extension</li><li>basedir: (optional) directory where to create the template. Defaults to <code>~/.hammerspoon/Spoons</code></li><li>metadata: (optional) table containing metadata values to be inserted in the template. Provided values are merged with the defaults. Defaults to:   <code>{     version = "0.1",     author = "Your Name &lt;your@email.org&gt;",     homepage = "https://github.com/Hammerspoon/Spoons",     license = "MIT - https://opensource.org/licenses/MIT",     download_url = "https://github.com/Hammerspoon/Spoons/raw/master/Spoons/"..name..".spoon.zip"   }</code></li><li>template: (optional) absolute path of the template to use for the <code>init.lua</code> file of the new Spoon. Defaults to the <code>templates/init.tpl</code> file included with Hammerspoon.</li></ul> |
| **Returns**                                          | <ul><li>The full directory path where the template was created, or <code>nil</code> if there was an error.</li></ul> |

#### [resourcePath](#resourcepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.resourcePath(partial) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Return full path of an object within a spoon directory, given its partial path. |
| **Parameters**                                       | <ul><li>partial - path of a file relative to the Spoon directory. For example <code>images/img1.png</code> will refer to a file within the <code>images</code> directory of the Spoon.</li></ul> |
| **Returns**                                          | <ul><li>Absolute path of the file. Note: no existence or other checks are done on the path.</li></ul> |

#### [scriptPath](#scriptpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.scriptPath([n]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Return path of the current spoon. |
| **Parameters**                                       | <ul><li>n - (optional) stack level for which to get the path. Defaults to 2, which will return the path of the spoon which called <code>scriptPath()</code></li></ul> |
| **Returns**                                          | <ul><li>String with the path from where the calling code was loaded.</li></ul> |

#### [use](#use)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.use(name, arg, [noerror]) -> boolean | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Declaratively load and configure a Spoon |
| **Parameters**                                       | <ul><li>name - the name of the Spoon to load (without the <code>.spoon</code> extension).</li><li>arg - if provided, can be used to specify the configuration of the Spoon. The following keys are recognized (all are optional):</li><li>config - a table containing variables to be stored in the Spoon object to configure it. For example, <code>config = { answer = 42 }</code> will result in <code>spoon.&lt;LoadedSpoon&gt;.answer</code> being set to 42.</li><li>hotkeys - a table containing hotkey bindings. If provided, will be passed as-is to the Spoon's <code>bindHotkeys()</code> method. The special string <code>"default"</code> can be given to use the Spoons <code>defaultHotkeys</code> variable, if it exists.</li><li>fn - a function which will be called with the freshly-loaded Spoon object as its first argument.</li><li>loglevel - if the Spoon has a variable called <code>logger</code>, its <code>setLogLevel()</code> method will be called with this value.</li><li>start - if <code>true</code>, call the Spoon's <code>start()</code> method after configuring everything else.</li><li>noerror - if <code>true</code>, don't log an error if the Spoon is not installed, simply return <code>nil</code>.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the spoon was loaded, <code>nil</code> otherwise</li></ul> |

