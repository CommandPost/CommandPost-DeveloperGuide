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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `action`  - A table representing the action, matching the following:</li><li markdown="1">   `id`      - The specific Command ID within the group.</li></ul> |

#### [getId](#getid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.getId(action) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get ID.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* action - The action table.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The ID as a string.</li></ul>          |

#### [getId](#getid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actionss.getId(action) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the ID from an action.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* action - The action table.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The ID as a string.</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.init(actionmanager, cmds) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">actionmanager - The action manager object</li><li markdown="1">cmds - Final Cut Pro commands manager</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [onChoices](#onchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.onChoices([choices]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds available choices to the selection.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `choices` - The optional `cp.choices` to add choices to.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* None</li></ul>          |

#### [onExecute](#onexecute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.onExecute(action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | On Execute.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* action - The action table.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* None</li></ul>          |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.commands.actions.reset() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Reset the Font Handler Cache.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* None</li></ul>          |

