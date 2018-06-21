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
| **Parameters**                                       |  * buttonID - The button ID you want to clear.                                       |
| **Returns**                                          |  * None                                                |

#### [favourites](#favourites)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.favourites() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a table of favourites from file.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table of favourites.                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise Module.                                                                                         |
| **Parameters**                                       |  * tangentManager - Tangent Manager Plugin * actionManager - Action Manager Plugin * cpGroup - CommandPost Group                                       |
| **Returns**                                          |  * None                                                |

#### [saveAction](#saveaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.saveAction(buttonID, actionTitle, handlerID, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves an action to Favourites.                                                                                         |
| **Parameters**                                       |  * buttonID - The button ID as number. * actionTitle - The action title as string. * handlerID - The handler ID as string. * action - The action table.                                       |
| **Returns**                                          |  * None                                                |

#### [updateControls](#updatecontrols)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.updateControls() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Update Controls                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

