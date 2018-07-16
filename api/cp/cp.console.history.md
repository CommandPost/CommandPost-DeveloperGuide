# [docs](index.md) » cp.console.history
---

Console History Manager.

Based on code by @asmagill
https://github.com/asmagill/hammerspoon-config-take2/blob/master/utils/_actions/consoleHistory.lua

## API Overview
* Functions - API calls offered directly by the extension
 * [clearHistory](#clearhistory)
 * [history](#history)
 * [init](#init)
 * [pruneHistory](#prunehistory)
 * [retrieveHistory](#retrievehistory)
 * [saveHistory](#savehistory)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [cache](#cache)

## API Documentation

### Functions

#### [clearHistory](#clearhistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.clearHistory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Clears the Console History. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [history](#history)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.history(toFind) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a history item. |
| **Parameters**                                       | <ul><li>toFind - Number of the item to find.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.init() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialise the module. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [pruneHistory](#prunehistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.pruneHistory() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Prune History |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Current History Count</li></ul> |

#### [retrieveHistory](#retrievehistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.retrieveHistory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Retrieve's the Console History. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [saveHistory](#savehistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.saveHistory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Saves the Console History. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [cache](#cache)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.cache <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Console History Cache |

