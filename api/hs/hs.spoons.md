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
| **Parameters**                                       | <ul><br /><li>def - table containing name-to-function definitions for the hotkeys supported by the Spoon. Each key is a hotkey name, and its value must be a function that will be called when the hotkey is invoked. * map - table containing name-to-hotkey definitions, as supported by <a href="https://github.com/Hammerspoon/hammerspoon/blob/master/SPOONS.md#hotkeys">bindHotkeys in the Spoon API</a>. Not all the entries in <code>def</code> must be bound, but if any keys in <code>map</code> don't have a definition, an error will be produced.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [isInstalled](#isinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.isInstalled(name) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Check if a given Spoon is installed.                                                                                         |
| **Parameters**                                       | <ul><br /><li>name - Name of the Spoon to check.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>If the Spoon is installed, it returns a table with the Spoon information as returned by <code>list()</code>. Returns <code>nil</code> if the Spoon is not installed.</li><br /></ul>                                           |

#### [isLoaded](#isloaded)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.isLoaded(name) -> boolean | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Check if a given Spoon is loaded.                                                                                         |
| **Parameters**                                       | <ul><br /><li>name - Name of the Spoon to check.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the Spoon is loaded, <code>nil</code> otherwise.</li><br /></ul>                                           |

#### [list](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.list() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a list of installed/loaded Spoons                                                                                         |
| **Parameters**                                       | <ul><br /><li>onlyLoaded - only return loaded Spoons (skips those that are installed but not loaded). Defaults to <code>false</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table with a list of installed/loaded spoons (depending on the value of <code>onlyLoaded</code>). Each entry is a table with the following entries:   * <code>name</code> - Spoon name   * <code>loaded</code> - boolean indication of whether the Spoon is loaded (<code>true</code>) or only installed (<code>false</code>)   * <code>version</code> - Spoon version number. Available only for loaded Spoons.</li><br /></ul>                                           |

#### [newSpoon](#newspoon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.newSpoon(name, basedir, metadata) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Create a skeleton for a new Spoon                                                                                         |
| **Parameters**                                       | <ul><br /><li>name: name of the new spoon, without the <code>.spoon</code> extension * basedir: (optional) directory where to create the template. Defaults to <code>~/.hammerspoon/Spoons</code> * metadata: (optional) table containing metadata values to be inserted in the template. Provided values are merged with the defaults. Defaults to:   <code>{     version = "0.1",     author = "Your Name &lt;your@email.org&gt;",     homepage = "https://github.com/Hammerspoon/Spoons",     license = "MIT - https://opensource.org/licenses/MIT",     download_url = "https://github.com/Hammerspoon/Spoons/raw/master/Spoons/"..name..".spoon.zip"   }</code> * template: (optional) absolute path of the template to use for the <code>init.lua</code> file of the new Spoon. Defaults to the <code>templates/init.tpl</code> file included with Hammerspoon.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The full directory path where the template was created, or <code>nil</code> if there was an error.</li><br /></ul>                                           |

#### [resourcePath](#resourcepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.resourcePath(partial) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return full path of an object within a spoon directory, given its partial path.                                                                                         |
| **Parameters**                                       | <ul><br /><li>partial - path of a file relative to the Spoon directory. For example <code>images/img1.png</code> will refer to a file within the <code>images</code> directory of the Spoon.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Absolute path of the file. Note: no existence or other checks are done on the path.</li><br /></ul>                                           |

#### [scriptPath](#scriptpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.scriptPath([n]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return path of the current spoon.                                                                                         |
| **Parameters**                                       | <ul><br /><li>n - (optional) stack level for which to get the path. Defaults to 2, which will return the path of the spoon which called <code>scriptPath()</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String with the path from where the calling code was loaded.</li><br /></ul>                                           |

#### [use](#use)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spoons.use(name, arg) -> boolean | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Declaratively load and configure a Spoon                                                                                         |
| **Parameters**                                       | <ul><br /><li>name - the name of the Spoon to load (without the <code>.spoon</code> extension). * arg - if provided, can be used to specify the configuration of the Spoon. The following keys are recognized (all are optional):   * config - a table containing variables to be stored in the Spoon object to configure it. For example, <code>config = { answer = 42 }</code> will result in <code>spoon.&lt;LoadedSpoon&gt;.answer</code> being set to 42.   * hotkeys - a table containing hotkey bindings. If provided, will be passed as-is to the Spoon's <code>bindHotkeys()</code> method. The special string <code>"default"</code> can be given to use the Spoons <code>defaultHotkeys</code> variable, if it exists.   * fn - a function which will be called with the freshly-loaded Spoon object as its first argument.   * loglevel - if the Spoon has a variable called <code>logger</code>, its <code>setLogLevel()</code> method will be called with this value.   * start - if <code>true</code>, call the Spoon's <code>start()</code> method after configuring everything else. * noerror - if <code>true</code>, don't log an error if the Spoon is not installed, simply return <code>nil</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the spoon was loaded, <code>nil</code> otherwise</li><br /></ul>                                           |

