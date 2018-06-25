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
| **Type**                                             | Function |
| **Description**                                      | Adds an item to the Pasteboard history. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [clearHistory](#clearhistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.clearHistory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Clears the Pasteboard History. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getHistory](#gethistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.getHistory() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the Pasteboard History. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of the Pasteboard history.</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.init(manager) -> Pasteboard History Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the module. |
| **Parameters**                                       | <ul><li>manager - The Pasteboard manager object.</li></ul> |
| **Returns**                                          | <ul><li>Pasteboard History Object</li></ul> |

#### [pasteHistoryItem](#pastehistoryitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.pasteHistoryItem(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Pastes a Pasteboard History Item. |
| **Parameters**                                       | <ul><li>index - The index of the Pasteboard history item.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setHistory](#sethistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.setHistory(history) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets the Pasteboard History. |
| **Parameters**                                       | <ul><li>history - The history in a table.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Enable or disable the Pasteboard History. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable the Pasteboard History. |

