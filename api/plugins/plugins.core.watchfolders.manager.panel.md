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
| **Parameters**                                       | <ul><li>priority - Defines the order in which the panel appears.</li><li>id       - The unique ID for the panel.</li><li>webview  - The webview the panel is attached to.</li></ul> |
| **Returns**                                          | <ul><li>A panel object</li></ul>          |

### Methods

#### [addButton](#addbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addButton(priority, params, itemFn, customWidth) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a button to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><li>`priority` - The priority number for the button.</li><li>`params` - The set of parameters for the button.</li></ul> |
| **Returns**                                          | <ul><li>The panel.</li></ul>          |

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addCheckbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><li>`priority`   - The priority number for the checkbox.</li><li>`params`     - The set of parameters for the checkbox.</li></ul> |
| **Returns**                                          | <ul><li>The panel.</li></ul>          |
| **Notes**                                            | <ul><li>The `params` can contain the following fields:</li><li> ** `id`        - (optional) The unique ID. If none is provided, one will be generated.</li><li> ** `name`      - (optional) The name of the checkbox field.</li><li> ** `label`     - (optional) The text label to display after the checkbox.</li><li> ** `onchange`  - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox.</li><li> ** `class`     - (optional) the CSS class list to apply to the checkbox.</li></ul>                |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addContent(priority, content[, escaped]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel, with the specified `priority` order.                                                                                         |
| **Parameters**                                       | <ul><li>`priority` - the priority order of the content.</li><li>`content` - a value that can be converted to a string.</li><li>`escaped` - if `true`, the content will be escaped.</li></ul> |
| **Returns**                                          | <ul><li>The panel object</li></ul>          |

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addHandler(event, id, handlerFn, keys) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a handler                                                                                         |
| **Parameters**                                       | <ul><li>event - The JavaScript event as string</li><li>id - The ID as string</li><li>handlerFn - The handler function</li><li>keys - Table of keys</li></ul> |
| **Returns**                                          | <ul><li>The panel object</li></ul>          |

#### [addHeading](#addheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addHeading(priority, text, level) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a heading to the panel with the specified `priority` and `text`.                                                                                         |
| **Parameters**                                       | <ul><li>`priority` - The priority number for the heading.</li><li>`text` - The content of the heading as a string.</li><li>`level` - The level of the heading.</li></ul> |
| **Returns**                                          | <ul><li>The panel object</li></ul>          |

#### [addParagraph](#addparagraph)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addParagraph(priority, content[, escaped[, class]]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a paragraph to the panel with the specified `priority` and `content`.                                                                                         |
| **Parameters**                                       | <ul><li>`priority` - The priority number for the paragraph.</li><li>`content` - The content you want to include as a string.</li><li>`escaped` - Whether or not the HTML is escaped as a boolean.</li><li>`class` - The class name as a string.</li></ul> |
| **Returns**                                          | <ul><li>The panel object</li></ul>          |

#### [addPassword](#addpassword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addPassword(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a password textbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><li>`priority`   - The priority number for the password.</li><li>`params`     - The set of parameters for the password.</li></ul> |
| **Returns**                                          | <ul><li>The panel.</li></ul>          |

#### [addSelect](#addselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addSelect(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a select to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><li>`priority` - The priority number for the select.</li><li>`params` - The set of parameters for the select.</li></ul> |
| **Returns**                                          | <ul><li>The panel.</li></ul>          |

#### [addTextbox](#addtextbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addTextbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a textbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><li>`priority`   - The priority number for the textbox.</li><li>`params`     - The set of parameters for the textbox.</li></ul> |
| **Returns**                                          | <ul><li>The panel.</li></ul>          |

#### [generateContent](#generatecontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:generateContent() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets generated toolbar content                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string of generated content</li></ul>          |

#### [getToolbarItem](#gettoolbaritem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:getToolbarItem() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a Toolbar Item                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table of Toolbar Item Values</li></ul>          |

