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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The number of panels.</li></ul>          |

#### [panelNumber](#panelnumber)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panelNumber() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | The number of the panel currently being viewed.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the current panel number, or `0` if no panels are registered.</li></ul>          |

#### [panelQueue](#panelqueue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panelQueue() -> table of panels` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | The table of panels remaining to be processed. Panels are removed from the queue                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The table of panels remaining to be processed.</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel.new(id, priority) -> plugins.core.setup.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new panel with the specified priority and ID.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">priority - Defines the order in which the panel appears.</li><li markdown="1">id       - The unique ID for the panel.</li></ul> |

### Methods

#### [addButton](#addbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addButton(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a button to the panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">params - The list of parameters.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The same panel.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The `params` table may contain:</li><li markdown="1"> ** `id`        - (optional) the unique ID for the button. If none is provided, one is generated.</li><li markdown="1"> ** `value`     - The value of the button. This is sent to the `onclick` function.</li><li markdown="1"> ** `label`     - The text label for the button. Defaults to the `value` if not provided.</li><li markdown="1"> ** `width`     - The width of the button in pixels.</li><li markdown="1"> ** `onclick`   - the function to execute when the button is clicked. The function should have the signature of `function(id, value)`, where `id` is the id of the button that was clicked, and `value` is the value of the button.</li></ul>                |

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addCheckbox(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`priority`   - The priority number for the checkbox.</li><li markdown="1">`params`     - The set of parameters for the checkbox.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The `params` can contain the following fields:</li><li markdown="1"> ** `id`        - (optional) The unique ID. If none is provided, one will be generated.</li><li markdown="1"> ** `name`      - (optional) The name of the checkbox field.</li><li markdown="1"> ** `label`     - (optional) The text label to display after the checkbox.</li><li markdown="1"> ** `onchange`  - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox.</li><li markdown="1"> ** `class`     - (optional) the CSS class list to apply to the checkbox.</li></ul>                |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addContent(content[, escaped]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `content` - a value that can be converted to a string.</li><li markdown="1">* `escaped` - if `true`, the content will not be escaped. Defaults to true.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel.</li></ul>          |

#### [addFooter](#addfooter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addFooter(content, unescaped) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel's footer.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `content` - a value that can be converted to a string.</li><li markdown="1">* `unescaped` - if `true`, the content will not be escaped. Defaults to true.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel.</li></ul>          |

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addHandler(event, id, handlerFn, keys) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a handler from an Handler ID                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">event - The event</li><li markdown="1">id - the Handler ID</li><li markdown="1">handlerFn - The Handler function</li><li markdown="1">keys - Keys</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [addHeading](#addheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addHeading(text) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a heading to the panel                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">text - The text of the heading as a string</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addIcon](#addicon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addIcon(src) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an icon to the panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">src - Location of the icon.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addParagraph](#addparagraph)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addParagraph(content[, escaped[, class]]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a Paragraph to the panel                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">content - The content as a string</li><li markdown="1">escaped - Whether or not the HTML should be escaped as a boolean</li><li markdown="1">class - The class as a string</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addPassword](#addpassword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addPassword(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a password text-box to the panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">params - A table of parameters</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addSelect](#addselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addSelect(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a select to the panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">params - A table of parameters</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addSubHeading](#addsubheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addSubHeading(text) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a sub-heading to the panel                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">text - The text of the sub-heading as a string</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addTextbox](#addtextbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addTextbox(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a text-box to the panel                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">params - A table of parameters</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [getHandler](#gethandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:getHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a handler from an Handler ID                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `id` - the Handler ID</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* A handler.</li></ul>          |

