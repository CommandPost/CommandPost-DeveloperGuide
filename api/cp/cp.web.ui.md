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
| **Type**                                             | Function |
| **Description**                                      | Creates a `cp.web.html` element for a heading with a specific level |
| **Parameters**                                       | <ul><li><code>params</code> - The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li><code>cp.web.html</code> element representing the heading.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> table has the following fields: <strong> <code>text</code>       - The string (or function) containing the text of the heading. </strong> <code>level</code>       - The heading level (or function) (1-7). Defaults to 3. ** <code>class</code>      - The CSS class (or function) for the heading tag.</li></ul> |

#### [img](#img)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.img(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a `cp.web.html` `img` element. |
| **Parameters**                                       | <ul><li><code>params</code>     - A table or function returning a table with the checkbox data.</li></ul> |
| **Returns**                                          | <ul><li>A <code>cp.web.html</code> with the select defined.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> table has the following supported fields: <strong> <code>src</code>      - The source of the image. If this points to a local file, it will be encoded as Base64. </strong> <code>class</code>     - A string, (or function returning a string) with the CSS class for the element. <strong> <code>width</code>     - The width of the image. </strong> <code>height</code>   - The height of the image.</li></ul> |

#### [javascript](#javascript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.javascript(script[, context][, naked]) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates an HTML script element which will execute the provided |
| **Parameters**                                       | <ul><li>script   - String containing the JavaScript to execute. * context    - (optional) Table containing any values to inject into the script. * naked    - (optional) If <code>true</code>, the javascript will be returned without a surrounding <script> block.</li></ul> |
| **Returns**                                          | <ul><li>a <code>cp.web.html</code> element representing the JavaScript block.</li></ul> |

#### [password](#password)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.password(params) -> hs.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates an `html` element that will output a password text box. |
| **Parameters**                                       | <ul><li><code>params</code> - The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li><code>cp.web.html</code> containing the textbox.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> table has the following supported fields: <strong> <code>id</code>               - The unique ID for the textbox. </strong> <code>name</code>          - The name of the textbox field. <strong> <code>class</code>         - The CSS classname. </strong> <code>placeholder</code>   - Placeholder text</li></ul> |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.select(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a `cp.web.html` `select` element. The `data` should be a table or a function returning a table |
| **Parameters**                                       | <ul><li><code>params</code>     - A table or function returning a table with the checkbox data.</li></ul> |
| **Returns**                                          | <ul><li>A <code>cp.web.html</code> with the select defined.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> table has the following supported fields: <strong> <code>id</code>       - a string (or function) the unique ID for the select. </strong> <code>value</code>       - a string, number, or boolean (or function) with the value of the select. May be <code>nil</code>. ** <code>options</code>   - an array (or function returning an array) of option tables, with the following keys: <strong><em> <code>value</code>  - the value of the option. </em></strong> <code>label</code>  - (optional) the label for the option. If not set, the <code>value</code> is used. <strong><em> <code>disabled</code> - (optional) if the option is disabled. </em>* <code>required</code>    - (optional) if <code>true</code>, there will not be a 'blank' option at the top of the list. </strong> <code>blankLabel</code>  - (optional) if specified, the value will be used for the 'blank' option label.</li></ul> |

#### [style](#style)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.style(rules[, context]) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates an HTML `style` element which will contain the provided rules. |
| **Parameters**                                       | <ul><li>rules    - String containing the CSS rules. * context    - (optional) Table containing any values to inject into the script.</li></ul> |
| **Returns**                                          | <ul><li>a <code>cp.web.html</code> element representing the JavaScript block.</li></ul> |

#### [template](#template)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.template(params) -> hs.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a `html` element that will execute a Resty Template. |
| **Parameters**                                       | <ul><li><code>params</code> - The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li><code>cp.web.html</code> containing the template.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> table has the following supported fields: <strong> <code>view</code>     - The file path to the template, or the template content itself. Required. </strong> <code>context</code> - The table containing the context to execute the template in. ** <code>unescaped</code>   - If true, the template will not be escaped before outputting.</li></ul> |

#### [textbox](#textbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.textbox(params) -> hs.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates an `html` element that will output a text box. |
| **Parameters**                                       | <ul><li><code>params</code> - The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li><code>cp.web.html</code> containing the textbox.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> table has the following supported fields: <strong> <code>id</code>               - The unique ID for the textbox. </strong> <code>name</code>          - The name of the textbox field. <strong> <code>class</code>         - The CSS classname. </strong> <code>placeholder</code>   - Placeholder text. ** <code>value</code>          - The default value of the textbox.</li></ul> |

### Constructors

#### [button](#button)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.button(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Generates a HTML Button |
| **Parameters**                                       | <ul><li><code>params</code>     - Table containing the data you want to display on the button.</li></ul> |
| **Returns**                                          | <ul><li>A <code>cp.web.ui</code> representing the button.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> can contain the following fields: <strong> <code>value</code>        - The value of the button. </strong> <code>label</code>       - The text label for the button. Defaults to the <code>value</code> if not provided. ** <code>width</code>        - The width of the button in pixels.</li></ul> |

#### [checkbox](#checkbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.ui.checkbox(params) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Generates a HTML Checkbox element. |
| **Parameters**                                       | <ul><li>data         - A table or function returning a table with the checkbox data.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.web.ui.element</code>.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> table has the following supported fields: <strong> <code>value</code>        - a string (or function) with the value of the checkbox. If not specified, the title is used. </strong> <code>checked</code>  - a boolean (or function) set to <code>true</code> or <code>false</code>, depending on if the checkbox is checked. <strong> <code>disabled</code>  - a boolean (or function) set to <code>true</code> or <code>false</code>, depending on if the checkbox is disabled. </strong> <code>id</code>       - (optional) a string (or function) with the unique ID for the checkbox. <strong> <code>name</code>      - (optional) a unique name for the checkbox field. </strong> <code>class</code>       - (optional) the CSS class list.</li></ul> |

