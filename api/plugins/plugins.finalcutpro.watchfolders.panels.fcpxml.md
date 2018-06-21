# [docs](index.md) » plugins.finalcutpro.watchfolders.panels.fcpxml
---

Final Cut Pro FCPXML Watch Folder Plugin.

## API Overview
* Constants - Useful values which cannot be changed
 * [SECONDS_UNTIL_DELETE](#seconds_until_delete)
* Variables - Configurable values
 * [automaticallyImport](#automaticallyimport)
 * [deleteAfterImport](#deleteafterimport)
 * [disableImport](#disableimport)
 * [filesInTransit](#filesintransit)
 * [notifications](#notifications)
 * [savedNotifications](#savednotifications)
 * [watchFolders](#watchfolders)
 * [watchFolderTableID](#watchfoldertableid)
* Functions - API calls offered directly by the extension
 * [addWatchFolder](#addwatchfolder)
 * [controllerCallback](#controllercallback)
 * [createNotification](#createnotification)
 * [generateTable](#generatetable)
 * [importFile](#importfile)
 * [init](#init)
 * [insertFilesIntoFinalCutPro](#insertfilesintofinalcutpro)
 * [newWatcher](#newwatcher)
 * [refreshTable](#refreshtable)
 * [removeWatcher](#removewatcher)
 * [setupWatchers](#setupwatchers)
 * [styleSheet](#stylesheet)
 * [watchFolderTriggered](#watchfoldertriggered)

## API Documentation

### Constants

#### [SECONDS_UNTIL_DELETE](#seconds_until_delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.SECONDS_UNTIL_DELETE -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Seconds until a file is deleted.                                                                                         |

### Variables

#### [automaticallyImport](#automaticallyimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.automaticallyImport <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Boolean that sets whether or not new generated voice file are automatically added to the timeline or not.                                                                                         |

#### [deleteAfterImport](#deleteafterimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.deleteAfterImport <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Boolean that sets whether or not you want to delete file after they've been imported.                                                                                         |

#### [disableImport](#disableimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.disableImport -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | When `true` Notifications will no longer be triggered.                                                                                         |

#### [filesInTransit](#filesintransit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.filesInTransit -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Files currently being copied                                                                                         |

#### [notifications](#notifications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.notifications -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of Notifications                                                                                         |

#### [savedNotifications](#savednotifications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.savedNotifications <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of Notifications that are saved between restarts                                                                                         |

#### [watchFolders](#watchfolders)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.watchFolders <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of the users watch folders.                                                                                         |

#### [watchFolderTableID](#watchfoldertableid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.watchFolderTableID -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Watch Folder Table ID                                                                                         |

### Functions

#### [addWatchFolder](#addwatchfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.addWatchFolder() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Opens the "Add Watch Folder" Dialog.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [controllerCallback](#controllercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.controllerCallback(id, params) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Callback Controller                                                                                         |
| **Parameters**                                       |  * id - ID as string * params - table of Parameters                                       |
| **Returns**                                          |  * None                                                |

#### [createNotification](#createnotification)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.createNotification(file) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new notification                                                                                         |
| **Parameters**                                       |  * file - File name                                       |
| **Returns**                                          |  * None                                                |

#### [generateTable](#generatetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.generateTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generate HTML Table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Returns a HTML table as a string                                                |

#### [importFile](#importfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.importFile(file, obj) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Imports a file into Final Cut Pro                                                                                         |
| **Parameters**                                       |  * file - File name * tag - The notification tag                                       |
| **Returns**                                          |  * None                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.init(deps, env) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       |  * deps - The dependencies environment * env - The plugin environment                                       |
| **Returns**                                          |  * Table of the module.                                                |

#### [insertFilesIntoFinalCutPro](#insertfilesintofinalcutpro)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.insertFilesIntoFinalCutPro(files) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Imports a file into Final Cut Pro                                                                                         |
| **Parameters**                                       |  * files - File names in table                                       |
| **Returns**                                          |  * None                                                |

#### [newWatcher](#newwatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.newWatcher(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | New Folder Watcher                                                                                         |
| **Parameters**                                       |  * path - Path to Watch Folder                                       |
| **Returns**                                          |  * None                                                |

#### [refreshTable](#refreshtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.refreshTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Refreshes the Final Cut Pro Watch Folder Panel via JavaScript Injection                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [removeWatcher](#removewatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.removeWatcher(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Remove Folder Watcher                                                                                         |
| **Parameters**                                       |  * path - Path to Watch Folder                                       |
| **Returns**                                          |  * None                                                |

#### [setupWatchers](#setupwatchers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.setupWatchers(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Setup Folder Watchers                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [styleSheet](#stylesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.styleSheet() -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates Style Sheet                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Returns Style Sheet as a string                                                |

#### [watchFolderTriggered](#watchfoldertriggered)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.panels.fcpxml.watchFolderTriggered(files) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Watch Folder Triggered                                                                                         |
| **Parameters**                                       |  * files - A table of files                                       |
| **Returns**                                          |  * None                                                |

