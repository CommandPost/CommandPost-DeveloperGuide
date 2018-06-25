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
| **Parameters**                                       | <ul><br /><li>priority - Defines the order in which the panel appears. * id       - The unique ID for the panel. * webview  - The webview the panel is attached to.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A panel object</li><br /></ul>                                           |

### Methods

#### [addButton](#addbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addButton(priority, params, itemFn, customWidth) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a button to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code> - The priority number for the button. * <code>params</code> - The set of parameters for the button.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel.</li><br /></ul>                                           |

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addCheckbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code>   - The priority number for the checkbox. * <code>params</code>     - The set of parameters for the checkbox.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The <code>params</code> can contain the following fields: <strong> <code>id</code>        - (optional) The unique ID. If none is provided, one will be generated. </strong> <code>name</code>      - (optional) The name of the checkbox field. <strong> <code>label</code>     - (optional) The text label to display after the checkbox. </strong> <code>onchange</code>  - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, <code>id</code> and <code>params</code>, the latter of which is a table containing the <code>value</code> and <code>checked</code> values of the checkbox. ** <code>class</code>     - (optional) the CSS class list to apply to the checkbox.</li><br /></ul>                                             |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addContent(priority, content[, escaped]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel, with the specified `priority` order.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code> - the priority order of the content. * <code>content</code> - a value that can be converted to a string. * <code>escaped</code> - if <code>true</code>, the content will be escaped.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object</li><br /></ul>                                           |

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addHandler(event, id, handlerFn, keys) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a handler                                                                                         |
| **Parameters**                                       | <ul><br /><li>event - The JavaScript event as string * id - The ID as string * handlerFn - The handler function * keys - Table of keys</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object</li><br /></ul>                                           |

#### [addHeading](#addheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addHeading(priority, text, level) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a heading to the panel with the specified `priority` and `text`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code> - The priority number for the heading. * <code>text</code> - The content of the heading as a string. * <code>level</code> - The level of the heading.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object</li><br /></ul>                                           |

#### [addParagraph](#addparagraph)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addParagraph(priority, content[, escaped[, class]]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a paragraph to the panel with the specified `priority` and `content`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code> - The priority number for the paragraph. * <code>content</code> - The content you want to include as a string. * <code>escaped</code> - Whether or not the HTML is escaped as a boolean. * <code>class</code> - The class name as a string.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object</li><br /></ul>                                           |

#### [addPassword](#addpassword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addPassword(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a password textbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code>   - The priority number for the password. * <code>params</code>     - The set of parameters for the password.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel.</li><br /></ul>                                           |

#### [addSelect](#addselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addSelect(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a select to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code> - The priority number for the select. * <code>params</code> - The set of parameters for the select.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel.</li><br /></ul>                                           |

#### [addTextbox](#addtextbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:addTextbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a textbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code>   - The priority number for the textbox. * <code>params</code>     - The set of parameters for the textbox.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel.</li><br /></ul>                                           |

#### [generateContent](#generatecontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:generateContent() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets generated toolbar content                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string of generated content</li><br /></ul>                                           |

#### [getToolbarItem](#gettoolbaritem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.panel:getToolbarItem() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a Toolbar Item                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table of Toolbar Item Values</li><br /></ul>                                           |

