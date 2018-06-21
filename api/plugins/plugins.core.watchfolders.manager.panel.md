# [docs](index.md) » plugins.core.watchfolders.manager.panel
---

Watch Folder Panel Manager.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addButton](#addbutton)
 * [addCheckbox](#addcheckbox)
 * [addContent](#addcontent)
 * [addHandler](#addhandler)
 * [addHeading](#addheading)
 * [addParagraph](#addparagraph)
 * [addPassword](#addpassword)
 * [addSelect](#addselect)
 * [addTextbox](#addtextbox)
 * [generateContent](#generatecontent)
 * [getToolbarItem](#gettoolbaritem)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel.new(priority, id) -> panel object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new panel with the specified priority and ID.                                                                                         |
| **Parameters**                                       |  * priority - Defines the order in which the panel appears. * id       - The unique ID for the panel. * webview  - The webview the panel is attached to.                                       |
| **Returns**                                          |  * A panel object                                                |

### Methods

#### [addButton](#addbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addButton(priority, params, itemFn, customWidth) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a button to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       |  * `priority` - The priority number for the button. * `params` - The set of parameters for the button.                                       |
| **Returns**                                          |  * The panel.                                                |

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addCheckbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       |  * `priority`   - The priority number for the checkbox. * `params`     - The set of parameters for the checkbox.                                       |
| **Returns**                                          |  * The panel.                                                |
| **Notes**                                            |  * The `params` can contain the following fields: ** `id`        - (optional) The unique ID. If none is provided, one will be generated. ** `name`      - (optional) The name of the checkbox field. ** `label`     - (optional) The text label to display after the checkbox. ** `onchange`  - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox. ** `class`     - (optional) the CSS class list to apply to the checkbox.                                                      |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addContent(priority, content[, escaped]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel, with the specified `priority` order.                                                                                         |
| **Parameters**                                       |  * `priority` - the priority order of the content. * `content` - a value that can be converted to a string. * `escaped` - if `true`, the content will be escaped.                                       |
| **Returns**                                          |  * The panel object                                                |

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addHandler(event, id, handlerFn, keys) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a handler                                                                                         |
| **Parameters**                                       |  * event - The JavaScript event as string * id - The ID as string * handlerFn - The handler function * keys - Table of keys                                       |
| **Returns**                                          |  * The panel object                                                |

#### [addHeading](#addheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addHeading(priority, text, level) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a heading to the panel with the specified `priority` and `text`.                                                                                         |
| **Parameters**                                       |  * `priority` - The priority number for the heading. * `text` - The content of the heading as a string. * `level` - The level of the heading.                                       |
| **Returns**                                          |  * The panel object                                                |

#### [addParagraph](#addparagraph)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addParagraph(priority, content[, escaped[, class]]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a paragraph to the panel with the specified `priority` and `content`.                                                                                         |
| **Parameters**                                       |  * `priority` - The priority number for the paragraph. * `content` - The content you want to include as a string. * `escaped` - Whether or not the HTML is escaped as a boolean. * `class` - The class name as a string.                                       |
| **Returns**                                          |  * The panel object                                                |

#### [addPassword](#addpassword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addPassword(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a password textbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       |  * `priority`   - The priority number for the password. * `params`     - The set of parameters for the password.                                       |
| **Returns**                                          |  * The panel.                                                |

#### [addSelect](#addselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addSelect(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a select to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       |  * `priority` - The priority number for the select. * `params` - The set of parameters for the select.                                       |
| **Returns**                                          |  * The panel.                                                |

#### [addTextbox](#addtextbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addTextbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a textbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       |  * `priority`   - The priority number for the textbox. * `params`     - The set of parameters for the textbox.                                       |
| **Returns**                                          |  * The panel.                                                |

#### [generateContent](#generatecontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:generateContent() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets generated toolbar content                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A string of generated content                                                |

#### [getToolbarItem](#gettoolbaritem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:getToolbarItem() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a Toolbar Item                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Table of Toolbar Item Values                                                |

