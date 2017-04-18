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
 * [isEnabled](#isenabled)
 * [setEnabled](#setenabled)
 * [toggleEnabled](#toggleenabled)

## API Documentation

### Functions

#### [choices](#choices)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.menu.menuaction.choices() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an array of available choices                                                                                         |

#### [execute](#execute)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.menu.menuaction.execute(params) -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes the action with the provided parameters.                                                                                         |
| **Parameters**                                       | <ul><li>* `params`	- A table of parameters, matching the following:</li><li>		* `group`	- The Command Group ID</li><li>		* `id`		- The specific Command ID within the group.</li></ul> |

#### [id](#id)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.menu.menuaction.id() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the menu ID                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string contains the menu ID</li></ul>          |

#### [init](#init)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.menu.menuaction.init(actionmanager) -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Menu Action plugin                                                                                         |
| **Parameters**                                       | <ul><li>`actionmanager` - the Action Manager plugin</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [isEnabled](#isenabled)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.menu.menuaction.isEnabled() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enabled the Menu Action                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setEnabled](#setenabled)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.menu.menuaction.setEnabled() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets                                                                                         |
| **Parameters**                                       | <ul><li>`value` - boolean value</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [toggleEnabled](#toggleenabled)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.menu.menuaction.toggleEnabled() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles whether or not a menu action is enabled.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

