# [docs](index.md) » plugins.finalcutpro.commands.action
---

An `action` which will execute a command with matching group/id values.
Registers itself with the `finalcutpro.action.manager`.

## API Overview
* Functions - API calls offered directly by the extension
 * [execute](#execute)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [choices](#choices)
 * [enabled](#enabled)

## API Documentation

### Functions

#### [execute](#execute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.action.execute(params) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes the action with the provided parameters.                                                                                         |
| **Parameters**                                       | <ul><li>* `params`	- A table of parameters, matching the following:</li><li>		* `group`	- The Command Group ID</li><li>		* `id`		- The specific Command ID within the group.</li></ul> |

### Fields

#### [choices](#choices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.action.choices <cp.prop: cp.choices; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns an array of available choices                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.action.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | This will be `true` when the command actions are enabled.                                                                                         |

