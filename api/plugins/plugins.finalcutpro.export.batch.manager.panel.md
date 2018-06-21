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
| **Parameters**                                       | * priority  - Defines the order in which the panel appears.* id        - The unique ID for the panel.* webview   - The webview the panel is attached to.                                       |

### Methods

#### [addButton](#addbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addButton(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a button to the panel.                                                                                         |
| **Parameters**                                       |  * params - The list of parameters.                                       |
| **Returns**                                          |  * The same panel.                                                |
| **Notes**                                            |  * The `params` table may contain: ** `id`        - (optional) the unique ID for the button. If none is provided, one is generated. ** `value`     - The value of the button. This is sent to the `onclick` function. ** `label`     - The text label for the button. Defaults to the `value` if not provided. ** `width`     - The width of the button in pixels. ** `onclick`   - the function to execute when the button is clicked. The function should have the signature of `function(id, value)`, where `id` is the id of the button that was clicked, and `value` is the value of the button.                                                      |

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addCheckbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       |  * `priority`   - The priority number for the checkbox. * `params`     - The set of parameters for the checkbox.                                       |
| **Returns**                                          |  * The panel.Notes: * The `params` can contain the following fields: ** `id`         - (optional) The unique ID. If none is provided, one will be generated. ** `name`       - (optional) The name of the checkbox field. ** `label`      - (optional) The text label to display after the checkbox. ** `onchange`   - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox. ** `class`      - (optional) the CSS class list to apply to the checkbox.                                                |
| **Notes**                                            |  * The `params` can contain the following fields: ** `id`         - (optional) The unique ID. If none is provided, one will be generated. ** `name`       - (optional) The name of the checkbox field. ** `label`      - (optional) The text label to display after the checkbox. ** `onchange`   - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox. ** `class`      - (optional) the CSS class list to apply to the checkbox.                                                      |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addContent(priority, content[, escaped]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel, with the specified `priority` order.                                                                                         |
| **Parameters**                                       | * `priority`        - the priority order of the content.* `content`         - a value that can be converted to a string.* `escaped`         - if `true`, the content will be escaped.                                       |
| **Returns**                                          | * The panel.                                                |

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addHandler(event, id, handlerFn, keys) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a handler from an Handler ID                                                                                         |
| **Parameters**                                       |  * event - The event * id - the Handler ID * handlerFn - The Handler function * keys - Keys                                       |
| **Returns**                                          |  * None                                                |

#### [addHeading](#addheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addHeading(text) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a heading to the panel                                                                                         |
| **Parameters**                                       |  * text - The text of the heading as a string                                       |
| **Returns**                                          | * The panel object.                                                |

#### [addParagraph](#addparagraph)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addParagraph(content[, escaped[, class]]) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a Paragraph to the panel                                                                                         |
| **Parameters**                                       |  * content - The content as a string * escaped - Whether or not the HTML should be escaped as a boolean. Defaults to `true` for simple text. * class - The class as a string                                       |
| **Returns**                                          | * The panel object.                                                |

#### [addPassword](#addpassword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addPassword(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a password text-box to the panel.                                                                                         |
| **Parameters**                                       |  * params - A table of parameters                                       |
| **Returns**                                          | * The panel object.                                                |

#### [addSelect](#addselect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addSelect(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a select to the panel.                                                                                         |
| **Parameters**                                       |  * priority - Priority of the item as number. * params - A table of parameters                                       |
| **Returns**                                          |  * The panel object.                                                |

#### [addStatus](#addstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addStatus(priority, content, default) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a Paragraph to the panel                                                                                         |
| **Parameters**                                       |  * content - The content value * default - The default value to display if the `content` is `nil`. It will be displayed with a different style.                                       |
| **Returns**                                          | * The panel object.                                                |

#### [addTextbox](#addtextbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:addTextbox(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a text-box to the panel                                                                                         |
| **Parameters**                                       |  * params - A table of parameters                                       |
| **Returns**                                          | * The panel object.                                                |

#### [getToolbarItem](#gettoolbaritem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.panel:getToolbarItem() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Tool Bar as a table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The toolbar item as a table.                                                |

