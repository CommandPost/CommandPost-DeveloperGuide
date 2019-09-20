# [docs](index.md) » plugins.finalcutpro.menu.menuaction
---

A `action` which will trigger an Final Cut Pro menu with a matching path, if available/enabled.
Registers itself with the `plugins.core.actions.actionmanager`.

## API Overview
* Functions - API calls offered directly by the extension
 * [actionId](#actionid)
 * [init](#init)

## API Documentation

### Functions

#### [actionId](#actionid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.actionId(params) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the action ID from the parameters table. |
| **Parameters**                                       | <ul><li>params - Parameters table.</li></ul> |
| **Returns**                                          | <ul><li>Action ID as string.</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.menu.menuaction.init(actionmanager) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the Menu Action plugin |
| **Parameters**                                       | <ul><li><code>actionmanager</code> - the Action Manager plugin</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

