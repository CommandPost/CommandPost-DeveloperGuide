# [docs](index.md) » plugins.finalcutpro.export.batch.manager.panel
---

CommandPost Batch Export Panel.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_PRIORITY](#default_priority)
 * [HANDLER_PRIORITY](#handler_priority)
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
 * [addStatus](#addstatus)
 * [addTextbox](#addtextbox)
 * [getToolbarItem](#gettoolbaritem)

## API Documentation

### Constants

#### [DEFAULT_PRIORITY](#default_priority)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel.DEFAULT_PRIORITY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default priority for panels.                                                                                         |

#### [HANDLER_PRIORITY](#handler_priority)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel.HANDLER_PRIORITY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default priority for handler scripts.                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel.new(priority, id) -> cp.core.preferences.manager.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new panel with the specified priority and ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li>priority  - Defines the order in which the panel appears.<em> id        - The unique ID for the panel.</em> webview   - The webview the panel is attached to.</li><br /></ul>                                        |

### Methods

#### [addButton](#addbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addButton(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a button to the panel.                                                                                         |
| **Parameters**                                       | <ul><br /><li>params - The list of parameters.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The same panel.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The <code>params</code> table may contain: <strong> <code>id</code>        - (optional) the unique ID for the button. If none is provided, one is generated. </strong> <code>value</code>     - The value of the button. This is sent to the <code>onclick</code> function. <strong> <code>label</code>     - The text label for the button. Defaults to the <code>value</code> if not provided. </strong> <code>width</code>     - The width of the button in pixels. ** <code>onclick</code>   - the function to execute when the button is clicked. The function should have the signature of <code>function(id, value)</code>, where <code>id</code> is the id of the button that was clicked, and <code>value</code> is the value of the button.</li><br /></ul>                                             |

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addCheckbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code>   - The priority number for the checkbox. * <code>params</code>     - The set of parameters for the checkbox.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel.Notes: * The <code>params</code> can contain the following fields: <strong> <code>id</code>         - (optional) The unique ID. If none is provided, one will be generated. </strong> <code>name</code>       - (optional) The name of the checkbox field. <strong> <code>label</code>      - (optional) The text label to display after the checkbox. </strong> <code>onchange</code>   - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, <code>id</code> and <code>params</code>, the latter of which is a table containing the <code>value</code> and <code>checked</code> values of the checkbox. ** <code>class</code>      - (optional) the CSS class list to apply to the checkbox.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The <code>params</code> can contain the following fields: <strong> <code>id</code>         - (optional) The unique ID. If none is provided, one will be generated. </strong> <code>name</code>       - (optional) The name of the checkbox field. <strong> <code>label</code>      - (optional) The text label to display after the checkbox. </strong> <code>onchange</code>   - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, <code>id</code> and <code>params</code>, the latter of which is a table containing the <code>value</code> and <code>checked</code> values of the checkbox. ** <code>class</code>      - (optional) the CSS class list to apply to the checkbox.</li><br /></ul>                                             |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addContent(priority, content[, escaped]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel, with the specified `priority` order.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code>        - the priority order of the content.<em> <code>content</code>         - a value that can be converted to a string.</em> <code>escaped</code>         - if <code>true</code>, the content will be escaped.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel.</li><br /></ul>                                           |

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addHandler(event, id, handlerFn, keys) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a handler from an Handler ID                                                                                         |
| **Parameters**                                       | <ul><br /><li>event - The event * id - the Handler ID * handlerFn - The Handler function * keys - Keys</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [addHeading](#addheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addHeading(text) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a heading to the panel                                                                                         |
| **Parameters**                                       | <ul><br /><li>text - The text of the heading as a string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addParagraph](#addparagraph)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addParagraph(content[, escaped[, class]]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a Paragraph to the panel                                                                                         |
| **Parameters**                                       | <ul><br /><li>content - The content as a string * escaped - Whether or not the HTML should be escaped as a boolean. Defaults to <code>true</code> for simple text. * class - The class as a string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addPassword](#addpassword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addPassword(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a password text-box to the panel.                                                                                         |
| **Parameters**                                       | <ul><br /><li>params - A table of parameters</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addSelect](#addselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addSelect(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a select to the panel.                                                                                         |
| **Parameters**                                       | <ul><br /><li>priority - Priority of the item as number. * params - A table of parameters</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addStatus](#addstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addStatus(priority, content, default) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a Paragraph to the panel                                                                                         |
| **Parameters**                                       | <ul><br /><li>content - The content value * default - The default value to display if the <code>content</code> is <code>nil</code>. It will be displayed with a different style.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addTextbox](#addtextbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addTextbox(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a text-box to the panel                                                                                         |
| **Parameters**                                       | <ul><br /><li>params - A table of parameters</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [getToolbarItem](#gettoolbaritem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:getToolbarItem() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Tool Bar as a table                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The toolbar item as a table.</li><br /></ul>                                           |

