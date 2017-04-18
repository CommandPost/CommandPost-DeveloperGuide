# [docs](index.md) » plugins.core.commands.commandaction
---

An `action` which will execute a command with matching group/id values.
Registers itself with the `core.action.manager`.

## API Overview
* Functions - API calls offered directly by the extension
 * [choices](#choices)
 * [execute](#execute)

## API Documentation

### Functions

#### [choices](#choices)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.core.commands.commandaction.choices() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an array of available choices                                                                                         |

#### [execute](#execute)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.core.commands.commandaction.execute(params) -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes the action with the provided parameters.                                                                                         |
| **Parameters**                                       | <ul><li>* `params`	- A table of parameters, matching the following:</li><li>		* `group`	- The Command Group ID</li><li>		* `id`		- The specific Command ID within the group.</li></ul> |

