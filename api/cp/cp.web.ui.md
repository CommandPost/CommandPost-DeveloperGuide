# [docs](index.md) » cp.web.ui
---

This extension contains functions which simplify the creation of standard UI events
using `cp.web.html` as the basis. Most functions return a `html` element which is
potentially dynamically updatable. Most values can be set using a value or a function,
and if functions are provided, they are re-evaluated every time the element is generated.

## API Overview
* Functions - API calls offered directly by the extension
 * [heading](#heading)
 * [img](#img)
 * [javascript](#javascript)
 * [password](#password)
 * [select](#select)
 * [style](#style)
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
| **Parameters**                                       |  * `params`	- The parameters table. Details below.                                       |
| **Returns**                                          |  * `cp.web.html` element representing the heading.                                                |
| **Notes**                                            |  * The `params` table has the following fields: ** `text`		- The string (or function) containing the text of the heading. ** `level` 		- The heading level (or function) (1-7). Defaults to 3. ** `class`		- The CSS class (or function) for the heading tag.                                                      |

#### [img](#img)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.img(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a `cp.web.html` `img` element.                                                                                         |
| **Parameters**                                       |  * `params`		- A table or function returning a table with the checkbox data.                                       |
| **Returns**                                          |  * A `cp.web.html` with the select defined.                                                |
| **Notes**                                            |  * The `params` table has the following supported fields: ** `src`		- The source of the image. If this points to a local file, it will be encoded as Base64. ** `class`		- A string, (or function returning a string) with the CSS class for the element. ** `width`		- The width of the image. ** `height`	- The height of the image.                                                      |

#### [javascript](#javascript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.javascript(script[, context]) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates an HTML script element which will execute the provided                                                                                         |
| **Parameters**                                       |  * script 	- String containing the JavaScript to execute. * context	- (optional) Table containing any values to inject into the script.                                       |
| **Returns**                                          |  * a `cp.web.html` element representing the JavaScript block.                                                |

#### [password](#password)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.password(params) -> hs.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates an `html` element that will output a password text box.                                                                                         |
| **Parameters**                                       |  * `params`	- The parameters table. Details below.                                       |
| **Returns**                                          |  * `cp.web.html` containing the textbox.                                                |
| **Notes**                                            |  * The `params` table has the following supported fields: ** `id`				- The unique ID for the textbox. ** `name`			- The name of the textbox field. ** `class`			- The CSS classname. ** `placeholder`	- Placeholder text                                                      |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.select(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a `cp.web.html` `select` element. The `data` should be a table or a function returning a table                                                                                         |
| **Parameters**                                       |  * `params`		- A table or function returning a table with the checkbox data.                                       |
| **Returns**                                          |  * A `cp.web.html` with the select defined.                                                |
| **Notes**                                            |  * The `params` table has the following supported fields: ** `id`		- a string (or function) the unique ID for the select. ** `value`		- a string, number, or boolean (or function) with the value of the select. May be `nil`. ** `options`	- an array (or function returning an array) of option tables, with the following keys: *** `value`	- the value of the option. *** `label`	- (optional) the label for the option. If not set, the `value` is used. *** `disabled` - (optional) if the option is disabled. ** `required`	- (optional) if `true`, there will not be a 'blank' option at the top of the list. ** `blankLabel`	- (optional) if specified, the value will be used for the 'blank' option label.                                                      |

#### [style](#style)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.style(rules[, context]) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates an HTML `style` element which will contain the provided rules.                                                                                         |
| **Parameters**                                       |  * rules 	- String containing the CSS rules. * context	- (optional) Table containing any values to inject into the script.                                       |
| **Returns**                                          |  * a `cp.web.html` element representing the JavaScript block.                                                |

#### [template](#template)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.template(params) -> hs.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a `html` element that will execute a Resty Template.                                                                                         |
| **Parameters**                                       |  * `params`	- The parameters table. Details below.                                       |
| **Returns**                                          |  * `cp.web.html` containing the template.                                                |
| **Notes**                                            |  * The `params` table has the following supported fields: ** `view`		- The file path to the template, or the template content itself. Required. ** `context`	- The table containing the context to execute the template in. ** `unescaped`	- If true, the template will not be escaped before outputting.                                                      |

#### [textbox](#textbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.textbox(params) -> hs.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates an `html` element that will output a text box.                                                                                         |
| **Parameters**                                       |  * `params`	- The parameters table. Details below.                                       |
| **Returns**                                          |  * `cp.web.html` containing the textbox.                                                |
| **Notes**                                            |  * The `params` table has the following supported fields: ** `id`				- The unique ID for the textbox. ** `name`			- The name of the textbox field. ** `class`			- The CSS classname. ** `placeholder`	- Placeholder text. ** `value`			- The default value of the textbox.                                                      |

### Constructors

#### [button](#button)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.button(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Generates a HTML Button                                                                                         |
| **Parameters**                                       |  * `params`		- Table containing the data you want to display on the button.                                       |
| **Returns**                                          |  * A `cp.web.ui` representing the button.                                                |
| **Notes**                                            |  * The `params` can contain the following fields: ** `value`		- The value of the button. ** `label`		- The text label for the button. Defaults to the `value` if not provided. ** `width`		- The width of the button in pixels.                                                      |

#### [checkbox](#checkbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.checkbox(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Generates a HTML Checkbox element.                                                                                         |
| **Parameters**                                       |  * data			- A table or function returning a table with the checkbox data.                                       |
| **Returns**                                          |  * The `cp.web.ui.element`.                                                |
| **Notes**                                            |  * The `params` table has the following supported fields: ** `value`		- a string (or function) with the value of the checkbox. If not specified, the title is used. ** `checked`	- a boolean (or function) set to `true` or `false`, depending on if the checkbox is checked. ** `disabled`	- a boolean (or function) set to `true` or `false`, depending on if the checkbox is disabled. ** `id`		- (optional) a string (or function) with the unique ID for the checkbox. ** `name`		- (optional) a unique name for the checkbox field. ** `class`		- (optional) the CSS class list.                                                      |

