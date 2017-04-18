# [docs](index.md) » cp
---

Core CommandPost functionality

## Submodules
 * [cp.bench](cp.bench.md)
 * [cp.choices](cp.choices.md)
 * [cp.commands](cp.commands.md)
 * [cp.config](cp.config.md)
 * [cp.developer](cp.developer.md)
 * [cp.finalcutpro](cp.finalcutpro.md)
 * [cp.just](cp.just.md)
 * [cp.plist](cp.plist.md)
 * [cp.plugins](cp.plugins.md)
 * [cp.sourcewatcher](cp.sourcewatcher.md)
 * [cp.watcher](cp.watcher.md)
 * [cp.web](cp.web.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [javascript](#javascript)
 * [select](#select)
* Constructors - API calls which return an object, typically one that offers API methods
 * [button](#button)
 * [checkbox](#checkbox)
 * [new](#new)

## API Documentation

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.init()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise CommandPost                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [javascript](#javascript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.javascript(script, context) -> cp.web.ui` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates an HTML script element which will execute the provided                                                                                         |
| **Parameters**                                       | <ul><li>script 	- String containing the JavaScript to execute.</li><li>context	- Table containing any values to inject into the script.</li></ul> |
| **Returns**                                          | <ul><li>a </li></ul>          |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.select(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a `cp.web.html` `select` element. The `data` should be a table or a function returning a table                                                                                         |
| **Parameters**                                       | <ul><li>data			- A table or function returning a table with the checkbox data.</li></ul> |
| **Returns**                                          | <ul><li>A `cp.web.html` with the select defined.</li></ul>          |
| **Notes**                                            | <ul><li>The `params` table has the following supported fields:</li><li> ** `id`		- a string (or function) the unique ID for the select.</li><li> ** `value`		- a string, number, or boolean (or function) with the value of the select. May be `nil`.</li><li> ** `options`	- an array (or function returning an array) of option tables, with the following keys:</li><li> *** `value`	- the value of the option.</li><li> *** `label`	- (optional) the label for the option. If not set, the `value` is used.</li><li> ** `required`	- (optional) if `true`, there will not be a 'blank' option at the top of the list.</li><li> ** `blankLabel`	- (optional) if specified, the value will be used for the 'blank' option label.</li></ul>                |

### Constructors

#### [button](#button)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.button(params) -> cp.web.ui` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Generates a HTML Button                                                                                         |
| **Parameters**                                       | <ul><li>`params`		- Table containing the data you want to display on the button.</li></ul> |
| **Returns**                                          | <ul><li>A `cp.web.ui` representing the button.</li></ul>          |
| **Notes**                                            | <ul><li>* The `params` can contain the following fields:</li><li>** `value`		- The value of th button.</li><li>** `label`		- The text label for the button. Defaults to the `value` if not provided.</li><li>** `width`		- The width of the button in pixels.</li></ul>                |

#### [checkbox](#checkbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.checkbox(title, value[, id]) -> cp.web.ui` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Generates a HTML Checkbox element. The `data` should be a table or a function returning a table                                                                                         |
| **Parameters**                                       | <ul><li>data			- A table or function returning a table with the checkbox data.</li></ul> |
| **Returns**                                          | <ul><li>The `cp.web.ui.element`.</li></ul>          |
| **Notes**                                            | <ul><li>The `params` table has the following supported fields:</li><li> ** `value`		- a string (or function) with the value of the checkbox. If not specified, the title is used.</li><li> ** `checked`	- a boolean (or function) set to `true` or `false`, depending on if the checkbox is checked.</li><li> ** `id`		- (optional) a string (or function) with the unique ID for the checkbox.</li><li> ** `name`		- (optional) a unique name for the checkbox field.</li><li> ** `class`		- (optional) the CSS class list.</li></ul>                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.new(data, generateFn) -> cp.web.ui` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Generates an HTML element with the provided `data` and generator function.                                                                                         |
| **Parameters**                                       | <ul><li>data		- the data table, or function returning a table, containing the </li></ul> |

