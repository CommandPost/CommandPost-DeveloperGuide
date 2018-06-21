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
| **Parameters**                                       |  * params - Parameters table.                                       |
| **Returns**                                          |  * Action ID as string.                                                |

#### [execute](#execute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.execute(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes the action with the provided parameters.                                                                                         |
| **Parameters**                                       | * `action`  - A table of parameters, matching the following:    * `group`   - The Command Group ID    * `id`      - The specific Command ID within the group.                                       |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.id() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the menu ID                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * a string contains the menu ID                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.init(actionmanager) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Menu Action plugin                                                                                         |
| **Parameters**                                       |  * `actionmanager` - the Action Manager plugin                                       |
| **Returns**                                          |  * None                                                |

#### [onChoices](#onchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.onChoices(choices) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Add choices to the chooser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [reload](#reload)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.reload() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Reloads the choices.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.reset() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resets the handler.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

