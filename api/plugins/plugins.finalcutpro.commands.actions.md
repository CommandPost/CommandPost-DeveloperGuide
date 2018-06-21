# [docs](index.md) » plugins.finalcutpro.commands.actions
---

An `action` which will execute a command with matching group/id values.
Registers itself with the `core.action.manager`.

## API Overview
* Functions - API calls offered directly by the extension
 * [execute](#execute)
 * [getId](#getid)
 * [getId](#getid)
 * [init](#init)
 * [onChoices](#onchoices)
 * [onExecute](#onexecute)
 * [reset](#reset)

## API Documentation

### Functions

#### [execute](#execute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.execute(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes the action with the provided parameters.                                                                                         |
| **Parameters**                                       | * `action`  - A table representing the action, matching the following:    * `id`      - The specific Command ID within the group.                                       |

#### [getId](#getid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.getId(action) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get ID.                                                                                         |
| **Parameters**                                       | * action - The action table.                                       |
| **Returns**                                          | * The ID as a string.                                                |

#### [getId](#getid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actionss.getId(action) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the ID from an action.                                                                                         |
| **Parameters**                                       | * action - The action table.                                       |
| **Returns**                                          | * The ID as a string.                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.init(actionmanager, cmds) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       |  * actionmanager - The action manager object * cmds - Final Cut Pro commands manager                                       |
| **Returns**                                          |  * None                                                |

#### [onChoices](#onchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.onChoices([choices]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds available choices to the selection.                                                                                         |
| **Parameters**                                       | * `choices` - The optional `cp.choices` to add choices to.                                       |
| **Returns**                                          | * None                                                |

#### [onExecute](#onexecute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.onExecute(action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | On Execute.                                                                                         |
| **Parameters**                                       | * action - The action table.                                       |
| **Returns**                                          | * None                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.reset() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Reset the Font Handler Cache.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * None                                                |

