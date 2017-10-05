# [docs](index.md) » plugins.core.commands.actions
---

An `action` which will execute a command with matching group/id values.
Registers itself with the `core.action.manager`.

## API Overview
* Functions - API calls offered directly by the extension
 * [execute](#execute)
 * [onChoices](#onchoices)
 * [reset](#reset)

## API Documentation

### Functions

#### [execute](#execute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.execute(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes the action with the provided parameters.                                                                                         |
| **Parameters**                                       | <ul><li>* `action`	- A table representing the action, matching the following:</li><li>		* `id`		- The specific Command ID within the group.</li></ul> |

#### [onChoices](#onchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.onChoices(choices) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds available choices to the  selection.                                                                                         |
| **Parameters**                                       | <ul><li>* `choices`		- The `cp.choices` to add choices to.</li></ul> |
| **Returns**                                          | <ul><li>* Nothing</li></ul>          |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.reset() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resets the set of choices.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* Nothing</li></ul>          |

