# [docs](index.md) » plugins.finalcutpro.pasteboard.history
---

Pasteboard History

## API Overview
* Constants - Useful values which cannot be changed
 * [FILE_NAME](#file_name)
 * [FOLDER_NAME](#folder_name)
 * [HISTORY_MAXIMUM_SIZE](#history_maximum_size)
* Functions - API calls offered directly by the extension
 * [addHistoryItem](#addhistoryitem)
 * [clearHistory](#clearhistory)
 * [doPasteHistoryItem](#dopastehistoryitem)
 * [init](#init)
 * [update](#update)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [_history](#_history)
 * [enabled](#enabled)

## API Documentation

### Constants

#### [FILE_NAME](#file_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.FILE_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | File name of settings file. |

#### [FOLDER_NAME](#folder_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.FOLDER_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Folder Name where settings file is contained. |

#### [HISTORY_MAXIMUM_SIZE](#history_maximum_size)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.HISTORY_MAXIMUM_SIZE -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Maximum Size of Pasteboard History |

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

#### [doPasteHistoryItem](#dopastehistoryitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.doPasteHistoryItem(index) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a function which will paste a Pasteboard History Item when executed. |
| **Parameters**                                       | <ul><li>index - The index of the Pasteboard history item.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a> to be executed.</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.init(manager) -> Pasteboard History Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the module. |
| **Parameters**                                       | <ul><li>manager - The Pasteboard manager object.</li></ul> |
| **Returns**                                          | <ul><li>Pasteboard History Object</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Enable or disable the Pasteboard History. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [_history](#_history)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history._history <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains all the saved Touch Bar Buttons |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.history.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable the Pasteboard History. |

