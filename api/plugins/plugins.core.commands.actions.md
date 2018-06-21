# [docs](index.md) » plugins.core.commands.actions
---

An `action` which will execute a command with matching group/id values.
Registers itself with the `core.action.manager`.

## API Overview
* Functions - API calls offered directly by the extension
 * [execute](#execute)
 * [getId](#getid)
 * [init](#init)
 * [onChoices](#onchoices)
 * [reset](#reset)

## API Documentation

### Functions

#### [execute](#execute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.execute(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes the action with the provided parameters.                                                                                         |
| **Parameters**                                       |  * `action` - A table representing the action, matching the following:    * `id` - The specific Command ID within the group.                                       |
| **Returns**                                          |  * `true` if the action was executed successfully.                                                |

#### [getId](#getid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.getId(action) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets an ID from an action table                                                                                         |
| **Parameters**                                       | * `action`      - The action table.                                       |
| **Returns**                                          | * The ID as a string.                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.init(actionmanager, cmds) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       | * `actionmanager` - The Action Manager Plugin* `cmds` - The Commands Plugin.                                       |
| **Returns**                                          | * None                                                |

#### [onChoices](#onchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.onChoices(choices) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds available choices to the  selection.                                                                                         |
| **Parameters**                                       | * `choices`     - The `cp.choices` to add choices to.                                       |
| **Returns**                                          | * None                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.reset() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resets the set of choices.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * Nothing                                                |

