# [docs](index.md) » plugins.finalcutpro.menu.menuaction
---

A `action` which will trigger an Final Cut Pro menu with a matching path, if available/enabled.
Registers itself with the `plugins.core.actions.actionmanager`.

## API Overview
* Functions - API calls offered directly by the extension
 * [choices](#choices)
 * [execute](#execute)
 * [id](#id)
 * [init](#init)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)

## API Documentation

### Functions

#### [choices](#choices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.choices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an array of available choices                                                                                         |

#### [execute](#execute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.execute(params) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes the action with the provided parameters.                                                                                         |
| **Parameters**                                       | <ul><li>* `params`	- A table of parameters, matching the following:</li><li>		* `group`	- The Command Group ID</li><li>		* `id`		- The specific Command ID within the group.</li></ul> |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.id() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the menu ID                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string contains the menu ID</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.init(actionmanager) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Menu Action plugin                                                                                         |
| **Parameters**                                       | <ul><li>`actionmanager` - the Action Manager plugin</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | This will be `true` when menu actions are enabled.                                                                                         |

