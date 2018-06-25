# [docs](index.md) » cp.console.history
---

Console History Manager.

Originally created by @asmagill
https://github.com/asmagill/hammerspoon-config-take2/blob/master/utils/_actions/consoleHistory.lua

## API Overview
* Variables - Configurable values
 * [autosaveHistory](#autosavehistory)
* Functions - API calls offered directly by the extension
 * [clearHistory](#clearhistory)
 * [history](#history)
 * [pruneHistory](#prunehistory)
 * [retrieveHistory](#retrievehistory)
 * [saveHistory](#savehistory)

## API Documentation

### Variables

#### [autosaveHistory](#autosavehistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.autosaveHistory -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Auto Save History Timer.                                                                                         |

### Functions

#### [clearHistory](#clearhistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.clearHistory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Clears the Console History.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [history](#history)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.history(toFind) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a history item.                                                                                         |
| **Parameters**                                       | <ul><br /><li>toFind - Number of the item to find.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [pruneHistory](#prunehistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.pruneHistory() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Prune History                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Current History Count</li><br /></ul>                                           |

#### [retrieveHistory](#retrievehistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.retrieveHistory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieve's the Console History.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [saveHistory](#savehistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.console.history.saveHistory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves the Console History.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

