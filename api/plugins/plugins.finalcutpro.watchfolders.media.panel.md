# [docs](index.md) » plugins.finalcutpro.watchfolders.media.panel
---

Watch Folder Media Panel.

## API Overview
* Variables - Configurable values
 * [watchFolderTableID](#watchfoldertableid)
* Functions - API calls offered directly by the extension
 * [addWatchFolder](#addwatchfolder)
 * [controllerCallback](#controllercallback)
 * [generateTable](#generatetable)
 * [init](#init)
 * [refreshTable](#refreshtable)
 * [styleSheet](#stylesheet)

## API Documentation

### Variables

#### [watchFolderTableID](#watchfoldertableid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.panel.watchFolderTableID -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Watch Folder Table ID |

### Functions

#### [addWatchFolder](#addwatchfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.panel.addWatchFolder() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Opens the "Add Watch Folder" Dialog. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [controllerCallback](#controllercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.panel.controllerCallback(id, params) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Callback Controller |
| **Parameters**                                       | <ul><li>id - ID as string</li><li>params - table of Parameters</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [generateTable](#generatetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.panel.generateTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generate HTML Table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns a HTML table as a string</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.panel.init(mediaFolderManager, panelManager) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the module. |
| **Parameters**                                       | <ul><li>mediaFolderManager - Media Folder Manager</li><li>panelManager - Panel Manager</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [refreshTable](#refreshtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.panel.refreshTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Refreshes the Final Cut Pro Watch Folder Panel via JavaScript Injection |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [styleSheet](#stylesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.panel.styleSheet() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates Style Sheet |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns Style Sheet as a string</li></ul> |

