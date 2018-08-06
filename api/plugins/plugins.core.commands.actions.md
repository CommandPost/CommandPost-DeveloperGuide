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
| **Type**                                             | Function |
| **Description**                                      | Executes the action with the provided parameters. |
| **Parameters**                                       | <ul><li><code>action</code> - A table representing the action, matching the following:<ul><li><code>id</code> - The specific Command ID within the group.</li></ul></li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the action was executed successfully.</li></ul> |

#### [getId](#getid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.getId(action) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets an ID from an action table |
| **Parameters**                                       | <ul><li><code>action</code>      - The action table.</li></ul> |
| **Returns**                                          | <ul><li>The ID as a string.</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.init(actionmanager, cmds) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the module. |
| **Parameters**                                       | <ul><li><code>actionmanager</code> - The Action Manager Plugin</li><li><code>cmds</code> - The Commands Plugin.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [onChoices](#onchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.onChoices(choices) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Adds available choices to the  selection. |
| **Parameters**                                       | <ul><li><code>choices</code>     - The <code>cp.choices</code> to add choices to.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.commands.actions.reset() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Resets the set of choices. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

