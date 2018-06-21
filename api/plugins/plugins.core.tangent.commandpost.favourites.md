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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">buttonID - The button ID you want to clear.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [favourites](#favourites)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.favourites() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a table of favourites from file.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table of favourites.</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise Module.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">tangentManager - Tangent Manager Plugin</li><li markdown="1">actionManager - Action Manager Plugin</li><li markdown="1">cpGroup - CommandPost Group</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [saveAction](#saveaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.saveAction(buttonID, actionTitle, handlerID, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves an action to Favourites.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">buttonID - The button ID as number.</li><li markdown="1">actionTitle - The action title as string.</li><li markdown="1">handlerID - The handler ID as string.</li><li markdown="1">action - The action table.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [updateControls](#updatecontrols)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.commandpost.favourites.updateControls() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Update Controls                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

