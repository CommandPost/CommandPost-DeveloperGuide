# [docs](index.md) » plugins.core.preferences.manager.panel
---

CommandPost Preferences Panel.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_PRIORITY](#default_priority)
 * [HANDLER_PRIORITY](#handler_priority)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addCheckbox](#addcheckbox)
 * [addContent](#addcontent)

## API Documentation

### Constants

#### [DEFAULT_PRIORITY](#default_priority)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.manager.panel.DEFAULT_PRIORITY` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default priority for panels.                                                                                         |

#### [HANDLER_PRIORITY](#handler_priority)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.manager.panel.HANDLER_PRIORITY` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default priority for handler scripts.                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.manager.panel.new(priority, id) -> cp.core.preferences.manager.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new panel with the specified priority and ID.                                                                                         |
| **Parameters**                                       | <ul><li>* priority	- Defines the order in which the panel appears.</li><li>* id		- The unique ID for the panel.</li><li>* webview	- The webview the panel is attached to.</li></ul> |

### Methods

#### [addCheckbox](#addcheckbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.manager.panel:addCheckbox(priority, params) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                                         |
| **Parameters**                                       | <ul><li>`priority`	- The priority number for the checkbox.</li><li>`params`		- The set of parameters for the checkbox.</li></ul> |
| **Returns**                                          | <ul><li>The panel.</li><li>Notes:</li><li>* The `params` can contain the following fields:</li><li>** `id`			- (optional) The unique ID. If none is provided, one will be generated.</li><li>** `name`		- (optional) The name of the checkbox field.</li><li>** `label`		- (optional) The text label to display after the checkbox.</li><li>** `onchange`	- (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox.</li><li>** `class`		- (optional) the CSS class list to apply to the checkbox.</li></ul>          |
| **Notes**                                            | <ul><li>* The `params` can contain the following fields:</li><li>** `id`			- (optional) The unique ID. If none is provided, one will be generated.</li><li>** `name`		- (optional) The name of the checkbox field.</li><li>** `label`		- (optional) The text label to display after the checkbox.</li><li>** `onchange`	- (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox.</li><li>** `class`		- (optional) the CSS class list to apply to the checkbox.</li></ul>                |

#### [addContent](#addcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.manager.panel:addContent(priority, content) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified `content` to the panel, with the specified `priority` order.                                                                                         |
| **Parameters**                                       | <ul><li>* `priority`		- the priority order of the content.</li><li>* `content`			- a value that can be converted to a string.</li><li>* `unescaped`		- if `true`, the content will not be escaped. Defaults to true.</li></ul> |
| **Returns**                                          | <ul><li>* The panel.</li></ul>          |

