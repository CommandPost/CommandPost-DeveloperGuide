# [docs](index.md) » plugins.finalcutpro.pasteboard.history
---

Pasteboard History

## API Overview
* Functions - API calls offered directly by the extension
 * [addHistoryItem](#addhistoryitem)
 * [clearHistory](#clearhistory)
 * [getHistory](#gethistory)
 * [init](#init)
 * [pasteHistoryItem](#pastehistoryitem)
 * [setHistory](#sethistory)
 * [update](#update)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)

## API Documentation

### Functions

#### [addHistoryItem](#addhistoryitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.addHistoryItem(data, label) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds an item to the Pasteboard history.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [clearHistory](#clearhistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.clearHistory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Clears the Pasteboard History.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [getHistory](#gethistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.getHistory() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the Pasteboard History.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table of the Pasteboard history.                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.init(manager) -> Pasteboard History Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       |  * manager - The Pasteboard manager object.                                       |
| **Returns**                                          |  * Pasteboard History Object                                                |

#### [pasteHistoryItem](#pastehistoryitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.pasteHistoryItem(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Pastes a Pasteboard History Item.                                                                                         |
| **Parameters**                                       |  * index - The index of the Pasteboard history item.                                       |
| **Returns**                                          |  * None                                                |

#### [setHistory](#sethistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.setHistory(history) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Pasteboard History.                                                                                         |
| **Parameters**                                       |  * history - The history in a table.                                       |
| **Returns**                                          |  * None                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enable or disable the Pasteboard History.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Enable or disable the Pasteboard History.                                                                                         |

