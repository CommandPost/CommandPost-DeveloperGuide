# [docs](index.md) » plugins.core.tangent.commandpost.favourites
---

Tangent Favourites.

## API Overview
* Functions - API calls offered directly by the extension
 * [clearAction](#clearaction)
 * [favourites](#favourites)
 * [init](#init)
 * [saveAction](#saveaction)
 * [updateControls](#updatecontrols)

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

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise Module.                                                                                         |
| **Parameters**                                       | <ul><li>tangentManager - Tangent Manager Plugin</li><li>actionManager - Action Manager Plugin</li><li>cpGroup - CommandPost Group</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [saveAction](#saveaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.saveAction(buttonID, actionTitle, handlerID, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves an action to Favourites.                                                                                         |
| **Parameters**                                       | <ul><li>buttonID - The button ID as number.</li><li>actionTitle - The action title as string.</li><li>handlerID - The handler ID as string.</li><li>action - The action table.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [updateControls](#updatecontrols)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.updateControls() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Update Controls                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

