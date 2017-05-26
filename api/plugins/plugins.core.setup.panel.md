# [docs](index.md) » plugins.core.setup.panel
---

CommandPost Setup Window Panel.

## API Overview
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

## API Documentation

### Functions

#### [panelCount](#panelcount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panelCount() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | The number of panels currently being processed in this session.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The number of panels.</li></ul>          |

#### [panelNumber](#panelnumber)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panelNumber() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | The number of the panel currently being viewed.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the current panel number, or `0` if no panels are registered.</li></ul>          |

#### [panelQueue](#panelqueue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panelQueue() -> table of panels` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | The table of panels remaining to be processed. Panels are removed from the queue                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The table of panels remaining to be processed.</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel.new(id, priority) -> plugins.core.setup.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new panel with the specified priority and ID.                                                                                         |
| **Parameters**                                       | <ul><li>priority	- Defines the order in which the panel appears.</li><li>id		- The unique ID for the panel.</li></ul> |

### Methods

#### [addButton](#addbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addButton(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a button with the specified priority and parameters.                                                                                         |
| **Parameters**                                       | <ul><li>priority	- Defines the order in which the panel appears.</li><li>params	- The list of parameters.</li></ul> |
| **Returns**                                          | <ul><li>The same panel.</li></ul>          |
| **Notes**                                            | <ul><li>The `params` table may contain:</li><li> ** `id`		- (optional) the unique ID for the button. If none is provided, one is generated.</li><li> ** `value`		- The value of the button. This is sent to the `onclick` function.</li><li> ** `label`		- The text label for the button. Defaults to the `value` if not provided.</li><li> ** `width`		- The width of the button in pixels.</li><li> ** `onclick`	- the function to execute when the button is clicked. The function should have the signature of `function(id, value)`, where `id` is the id of the button that was clicked, and `value` is the value of the button.</li></ul>                |

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addCheckbox(params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><li>`priority`	- The priority number for the checkbox.</li><li>`params`		- The set of parameters for the checkbox.</li></ul> |
| **Returns**                                          | <ul><li>The panel.</li><li>Notes:</li><li>* The `params` can contain the following fields:</li><li>** `id`			- (optional) The unique ID. If none is provided, one will be generated.</li><li>** `name`		- (optional) The name of the checkbox field.</li><li>** `label`		- (optional) The text label to display after the checkbox.</li><li>** `onchange`	- (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox.</li><li>** `class`		- (optional) the CSS class list to apply to the checkbox.</li></ul>          |
| **Notes**                                            | <ul><li>* The `params` can contain the following fields:</li><li>** `id`			- (optional) The unique ID. If none is provided, one will be generated.</li><li>** `name`		- (optional) The name of the checkbox field.</li><li>** `label`		- (optional) The text label to display after the checkbox.</li><li>** `onchange`	- (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox.</li><li>** `class`		- (optional) the CSS class list to apply to the checkbox.</li></ul>                |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.panel:addContent(content) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel, with the specified `priority` order.                                                                                         |
| **Parameters**                                       | <ul><li>* `priority`		- the priority order of the content.</li><li>* `content`			- a value that can be converted to a string.</li><li>* `unescaped`		- if `true`, the content will not be escaped. Defaults to true.</li></ul> |
| **Returns**                                          | <ul><li>* The panel.</li></ul>          |

