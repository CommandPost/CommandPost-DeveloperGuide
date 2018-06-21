# [docs](index.md) » plugins.finalcutpro.menu.menuaction
---

A `action` which will trigger an Final Cut Pro menu with a matching path, if available/enabled.
Registers itself with the `plugins.core.actions.actionmanager`.

## API Overview
* Functions - API calls offered directly by the extension
 * [actionId](#actionid)
 * [execute](#execute)
 * [id](#id)
 * [init](#init)
 * [onChoices](#onchoices)
 * [reload](#reload)
 * [reset](#reset)

## API Documentation

### Functions

#### [actionId](#actionid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.actionId(params) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the action ID from the parameters table.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">params - Parameters table.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Action ID as string.</li></ul>          |

#### [execute](#execute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.execute(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes the action with the provided parameters.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `action`  - A table of parameters, matching the following:</li><li markdown="1">   `group`   - The Command Group ID</li><li markdown="1">   `id`      - The specific Command ID within the group.</li></ul> |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.id() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the menu ID                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a string contains the menu ID</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.init(actionmanager) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Menu Action plugin                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`actionmanager` - the Action Manager plugin</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [onChoices](#onchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.onChoices(choices) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Add choices to the chooser.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [reload](#reload)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.reload() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Reloads the choices.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.reset() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resets the handler.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

