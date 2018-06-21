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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* priority  - Defines the order in which the panel appears.</li><li markdown="1">* id        - The unique ID for the panel.</li><li markdown="1">* webview   - The webview the panel is attached to.</li></ul> |

### Methods

#### [addButton](#addbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addButton(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a button to the panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">params - The list of parameters.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The same panel.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The `params` table may contain:</li><li markdown="1"> ** `id`        - (optional) the unique ID for the button. If none is provided, one is generated.</li><li markdown="1"> ** `value`     - The value of the button. This is sent to the `onclick` function.</li><li markdown="1"> ** `label`     - The text label for the button. Defaults to the `value` if not provided.</li><li markdown="1"> ** `width`     - The width of the button in pixels.</li><li markdown="1"> ** `onclick`   - the function to execute when the button is clicked. The function should have the signature of `function(id, value)`, where `id` is the id of the button that was clicked, and `value` is the value of the button.</li></ul>                |

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addCheckbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`priority`   - The priority number for the checkbox.</li><li markdown="1">`params`     - The set of parameters for the checkbox.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The panel.</li><li markdown="1">Notes:</li><li markdown="1">The `params` can contain the following fields:</li><li markdown="1"> ** `id`         - (optional) The unique ID. If none is provided, one will be generated.</li><li markdown="1"> ** `name`       - (optional) The name of the checkbox field.</li><li markdown="1"> ** `label`      - (optional) The text label to display after the checkbox.</li><li markdown="1"> ** `onchange`   - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox.</li><li markdown="1"> ** `class`      - (optional) the CSS class list to apply to the checkbox.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The `params` can contain the following fields:</li><li markdown="1"> ** `id`         - (optional) The unique ID. If none is provided, one will be generated.</li><li markdown="1"> ** `name`       - (optional) The name of the checkbox field.</li><li markdown="1"> ** `label`      - (optional) The text label to display after the checkbox.</li><li markdown="1"> ** `onchange`   - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox.</li><li markdown="1"> ** `class`      - (optional) the CSS class list to apply to the checkbox.</li></ul>                |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addContent(priority, content[, escaped]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel, with the specified `priority` order.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `priority`        - the priority order of the content.</li><li markdown="1">* `content`         - a value that can be converted to a string.</li><li markdown="1">* `escaped`         - if `true`, the content will be escaped.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel.</li></ul>          |

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addHandler(event, id, handlerFn, keys) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a handler from an Handler ID                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">event - The event</li><li markdown="1">id - the Handler ID</li><li markdown="1">handlerFn - The Handler function</li><li markdown="1">keys - Keys</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [addHeading](#addheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addHeading(text) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a heading to the panel                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">text - The text of the heading as a string</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addParagraph](#addparagraph)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addParagraph(content[, escaped[, class]]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a Paragraph to the panel                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">content - The content as a string</li><li markdown="1">escaped - Whether or not the HTML should be escaped as a boolean. Defaults to `true` for simple text.</li><li markdown="1">class - The class as a string</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addPassword](#addpassword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addPassword(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a password text-box to the panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">params - A table of parameters</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addSelect](#addselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addSelect(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a select to the panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">priority - Priority of the item as number.</li><li markdown="1">params - A table of parameters</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The panel object.</li></ul>          |

#### [addStatus](#addstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addStatus(priority, content, default) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a Paragraph to the panel                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">content - The content value</li><li markdown="1">default - The default value to display if the `content` is `nil`. It will be displayed with a different style.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [addTextbox](#addtextbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addTextbox(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a text-box to the panel                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">params - A table of parameters</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The panel object.</li></ul>          |

#### [getToolbarItem](#gettoolbaritem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:getToolbarItem() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Tool Bar as a table                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The toolbar item as a table.</li></ul>          |

