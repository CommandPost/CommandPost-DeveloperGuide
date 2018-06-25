# [docs](index.md) » plugins.core.setup.panel
---

CommandPost Setup Window Panel.

## API Overview
* Constants - Useful values which cannot be changed
 * [WEBVIEW_LABEL](#webview_label)
* Functions - API calls offered directly by the extension
 * [panelCount](#panelcount)
 * [panelNumber](#panelnumber)
 * [panelQueue](#panelqueue)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addButton](#addbutton)
 * [addCheckbox](#addcheckbox)
 * [addContent](#addcontent)
 * [addFooter](#addfooter)
 * [addHandler](#addhandler)
 * [addHeading](#addheading)
 * [addIcon](#addicon)
 * [addParagraph](#addparagraph)
 * [addPassword](#addpassword)
 * [addSelect](#addselect)
 * [addSubHeading](#addsubheading)
 * [addTextbox](#addtextbox)
 * [getHandler](#gethandler)

## API Documentation

### Constants

#### [WEBVIEW_LABEL](#webview_label)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel.WEBVIEW_LABEL -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The ID for the Webview                                                                                         |

### Functions

#### [panelCount](#panelcount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panelCount() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | The number of panels currently being processed in this session.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The number of panels.</li><br /></ul>                                           |

#### [panelNumber](#panelnumber)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panelNumber() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | The number of the panel currently being viewed.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the current panel number, or <code>0</code> if no panels are registered.</li><br /></ul>                                           |

#### [panelQueue](#panelqueue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panelQueue() -> table of panels` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | The table of panels remaining to be processed. Panels are removed from the queue                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The table of panels remaining to be processed.</li><br /></ul>                                           |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel.new(id, priority) -> plugins.core.setup.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new panel with the specified priority and ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li>priority - Defines the order in which the panel appears. * id       - The unique ID for the panel.</li><br /></ul>                                        |

### Methods

#### [addButton](#addbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addButton(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a button to the panel.                                                                                         |
| **Parameters**                                       | <ul><br /><li>params - The list of parameters.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The same panel.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The <code>params</code> table may contain: <strong> <code>id</code>        - (optional) the unique ID for the button. If none is provided, one is generated. </strong> <code>value</code>     - The value of the button. This is sent to the <code>onclick</code> function. <strong> <code>label</code>     - The text label for the button. Defaults to the <code>value</code> if not provided. </strong> <code>width</code>     - The width of the button in pixels. ** <code>onclick</code>   - the function to execute when the button is clicked. The function should have the signature of <code>function(id, value)</code>, where <code>id</code> is the id of the button that was clicked, and <code>value</code> is the value of the button.</li><br /></ul>                                             |

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addCheckbox(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>priority</code>   - The priority number for the checkbox. * <code>params</code>     - The set of parameters for the checkbox.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The <code>params</code> can contain the following fields: <strong> <code>id</code>        - (optional) The unique ID. If none is provided, one will be generated. </strong> <code>name</code>      - (optional) The name of the checkbox field. <strong> <code>label</code>     - (optional) The text label to display after the checkbox. </strong> <code>onchange</code>  - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, <code>id</code> and <code>params</code>, the latter of which is a table containing the <code>value</code> and <code>checked</code> values of the checkbox. ** <code>class</code>     - (optional) the CSS class list to apply to the checkbox.</li><br /></ul>                                             |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addContent(content[, escaped]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>content</code> - a value that can be converted to a string.* <code>escaped</code> - if <code>true</code>, the content will not be escaped. Defaults to true.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel.</li><br /></ul>                                           |

#### [addFooter](#addfooter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addFooter(content, unescaped) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel's footer.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>content</code> - a value that can be converted to a string.* <code>unescaped</code> - if <code>true</code>, the content will not be escaped. Defaults to true.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel.</li><br /></ul>                                           |

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addHandler(event, id, handlerFn, keys) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a handler from an Handler ID                                                                                         |
| **Parameters**                                       | <ul><br /><li>event - The event * id - the Handler ID * handlerFn - The Handler function * keys - Keys</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [addHeading](#addheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addHeading(text) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a heading to the panel                                                                                         |
| **Parameters**                                       | <ul><br /><li>text - The text of the heading as a string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addIcon](#addicon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addIcon(src) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an icon to the panel.                                                                                         |
| **Parameters**                                       | <ul><br /><li>src - Location of the icon.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addParagraph](#addparagraph)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addParagraph(content[, escaped[, class]]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a Paragraph to the panel                                                                                         |
| **Parameters**                                       | <ul><br /><li>content - The content as a string * escaped - Whether or not the HTML should be escaped as a boolean * class - The class as a string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addPassword](#addpassword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addPassword(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a password text-box to the panel.                                                                                         |
| **Parameters**                                       | <ul><br /><li>params - A table of parameters</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addSelect](#addselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addSelect(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a select to the panel.                                                                                         |
| **Parameters**                                       | <ul><br /><li>params - A table of parameters</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addSubHeading](#addsubheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addSubHeading(text) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a sub-heading to the panel                                                                                         |
| **Parameters**                                       | <ul><br /><li>text - The text of the sub-heading as a string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [addTextbox](#addtextbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addTextbox(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a text-box to the panel                                                                                         |
| **Parameters**                                       | <ul><br /><li>params - A table of parameters</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The panel object.</li><br /></ul>                                           |

#### [getHandler](#gethandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:getHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a handler from an Handler ID                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code> - the Handler ID</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A handler.</li><br /></ul>                                           |

