# [docs](index.md) » plugins.core.tangent.commandpost.favourites
---

Tangent Favourites.

## API Overview
* Functions - API calls offered directly by the extension
 * [clearAction](#clearaction)
 * [favourites](#favourites)
 * [saveAction](#saveaction)

## API Documentation

### Functions

#### [clearAction](#clearaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.clearAction(buttonID) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Clears an Action from Favourites.                                                                                         |
| **Parameters**                                       | <ul><li>buttonID - The button ID you want to clear.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [favourites](#favourites)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.favourites() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a table of favourites from file.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of favourites.</li></ul>          |

#### [saveAction](#saveaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.saveAction(buttonID, actionTitle, handlerID, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves an action to Favourites.                                                                                         |
| **Parameters**                                       | <ul><li>buttonID - The button ID as number.</li><li>actionTitle - The action title as string.</li><li>handlerID - The handler ID as string.</li><li>action - The action table.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

