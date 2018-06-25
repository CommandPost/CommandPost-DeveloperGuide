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
| **Parameters**                                       | <ul><br /><li>buttonID - The button ID you want to clear.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [favourites](#favourites)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.favourites() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a table of favourites from file.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table of favourites.</li><br /></ul>                                           |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise Module.                                                                                         |
| **Parameters**                                       | <ul><br /><li>tangentManager - Tangent Manager Plugin * actionManager - Action Manager Plugin * cpGroup - CommandPost Group</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [saveAction](#saveaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.saveAction(buttonID, actionTitle, handlerID, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves an action to Favourites.                                                                                         |
| **Parameters**                                       | <ul><br /><li>buttonID - The button ID as number. * actionTitle - The action title as string. * handlerID - The handler ID as string. * action - The action table.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [updateControls](#updatecontrols)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.updateControls() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Update Controls                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

