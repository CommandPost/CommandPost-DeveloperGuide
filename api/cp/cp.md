# [docs](index.md) » cp
---

Core CommandPost functionality

## Submodules
 * [cp.apple](cp.apple.md)
 * [cp.bench](cp.bench.md)
 * [cp.choices](cp.choices.md)
 * [cp.commands](cp.commands.md)
 * [cp.config](cp.config.md)
 * [cp.developer](cp.developer.md)
 * [cp.feedback](cp.feedback.md)
 * [cp.just](cp.just.md)
 * [cp.plist](cp.plist.md)
 * [cp.plugins](cp.plugins.md)
 * [cp.prop](cp.prop.md)
 * [cp.sourcewatcher](cp.sourcewatcher.md)
 * [cp.watcher](cp.watcher.md)
 * [cp.web](cp.web.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [heading](#heading)
 * [init](#init)
 * [javascript](#javascript)
 * [modifierMaskToModifiers](#modifiermasktomodifiers)
 * [modifierMatch](#modifiermatch)
 * [password](#password)
 * [select](#select)
 * [template](#template)
 * [textbox](#textbox)
* Constructors - API calls which return an object, typically one that offers API methods
 * [button](#button)
 * [checkbox](#checkbox)

## API Documentation

### Functions

#### [heading](#heading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.heading(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a `cp.web.html` element for a heading with a specific level                                                                                         |
| **Parameters**                                       | <ul><li>* `params`	- The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li>* `cp.web.html` element representing the heading.</li></ul>          |
| **Notes**                                            | <ul><li>* The `params` table has the following fields:</li><li>** `text`		- The string (or function) containing the text of the heading.</li><li>** `level` 		- The heading level (or function) (1-7). Defaults to 3.</li><li>** `class`		- The CSS class (or function) for the heading tag.</li></ul>                |

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
| **Returns**                                          | <ul><li>a `cp.web.html` element representing the JavaScript block.</li></ul>          |

#### [modifierMaskToModifiers](#modifiermasktomodifiers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.modifierMaskToModifiers() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Modifiers from Apple's Plist Format into Hammerspoon Format                                                                                         |
| **Parameters**                                       | <ul><li>value - Modifiers String</li></ul> |
| **Returns**                                          | <ul><li>table</li></ul>          |

#### [modifierMatch](#modifiermatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.modifierMatch(inputA, inputB) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Compares two modifier tables.                                                                                         |
| **Parameters**                                       | <ul><li>inputA - table of modifiers</li><li>inputB - table of modifiers</li></ul> |
| **Returns**                                          | <ul><li>`true` if there's a match otherwise `false`</li></ul>          |
| **Notes**                                            | <ul><li>This function only takes into account 'ctrl', 'alt', 'cmd', 'shift'.</li></ul>                |

#### [password](#password)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.password(params) -> hs.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates an `html` element that will output a password text box.                                                                                         |
| **Parameters**                                       | <ul><li>* `params`	- The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li>* `cp.web.html` containing the textbox.</li></ul>          |
| **Notes**                                            | <ul><li>* The `params` table has the following supported fields:</li><li>** `id`				- The unique ID for the textbox.</li><li>** `name`			- The name of the textbox field.</li><li>** `class`			- The CSS classname.</li><li>** `placeholder`	- Placeholder text</li></ul>                |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.select(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a `cp.web.html` `select` element. The `data` should be a table or a function returning a table                                                                                         |
| **Parameters**                                       | <ul><li>data			- A table or function returning a table with the checkbox data.</li></ul> |
| **Returns**                                          | <ul><li>A `cp.web.html` with the select defined.</li></ul>          |
| **Notes**                                            | <ul><li>The `params` table has the following supported fields:</li><li> ** `id`		- a string (or function) the unique ID for the select.</li><li> ** `value`		- a string, number, or boolean (or function) with the value of the select. May be `nil`.</li><li> ** `options`	- an array (or function returning an array) of option tables, with the following keys:</li><li> *** `value`	- the value of the option.</li><li> *** `label`	- (optional) the label for the option. If not set, the `value` is used.</li><li> ** `required`	- (optional) if `true`, there will not be a 'blank' option at the top of the list.</li><li> ** `blankLabel`	- (optional) if specified, the value will be used for the 'blank' option label.</li></ul>                |

#### [template](#template)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.template(params) -> hs.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a `html` element that will execute a Resty Template.                                                                                         |
| **Parameters**                                       | <ul><li>* `params`	- The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li>* `cp.web.html` containing the template.</li></ul>          |
| **Notes**                                            | <ul><li>* The `params` table has the following supported fields:</li><li>** `view`		- The file path to the template, or the template content itself. Required.</li><li>** `context`	- The table containing the context to execute the template in.</li><li>** `unescaped`	- If true, the template will not be escaped before outputting.</li></ul>                |

#### [textbox](#textbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.textbox(params) -> hs.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates an `html` element that will output a text box.                                                                                         |
| **Parameters**                                       | <ul><li>* `params`	- The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li>* `cp.web.html` containing the textbox.</li></ul>          |
| **Notes**                                            | <ul><li>* The `params` table has the following supported fields:</li><li>** `id`				- The unique ID for the textbox.</li><li>** `name`			- The name of the textbox field.</li><li>** `class`			- The CSS classname.</li><li>** `placeholder`	- Placeholder text</li></ul>                |

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

