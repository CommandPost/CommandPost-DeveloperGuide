# [docs](index.md) » plugins.compressor.watchfolders.panels.media
---

Final Cut Pro Media Watch Folder Plugin.

## API Overview
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
 * [addFilesToCompressor](#addfilestocompressor)
 * [addWatchFolder](#addwatchfolder)
 * [controllerCallback](#controllercallback)
 * [generateTable](#generatetable)
 * [init](#init)
 * [newWatcher](#newwatcher)
 * [refreshTable](#refreshtable)
 * [removeWatcher](#removewatcher)
 * [setupWatchers](#setupwatchers)
 * [styleSheet](#stylesheet)
 * [watchCompressorStatus](#watchcompressorstatus)
 * [watchFolderTriggered](#watchfoldertriggered)

## API Documentation

### Variables

#### [automaticallyImport](#automaticallyimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.automaticallyImport` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Boolean that sets whether or not new generated voice file are automatically added to the timeline or not.                                                                                         |

#### [deleteAfterImport](#deleteafterimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.deleteAfterImport` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Boolean that sets whether or not you want to delete file after they've been imported.                                                                                         |

#### [disableImport](#disableimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.disableImport` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | When `true` Notifications will no longer be triggered.                                                                                         |

#### [filesInTransit](#filesintransit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.filesInTransit` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Files currently being copied                                                                                         |

#### [notifications](#notifications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.notifications` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of Notifications                                                                                         |

#### [savedNotifications](#savednotifications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.savedNotifications` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of Notifications that are saved between restarts                                                                                         |

#### [watchFolders](#watchfolders)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.watchFolders` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of the users watch folders.                                                                                         |

#### [watchFolderTableID](#watchfoldertableid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.watchFolderTableID` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Watch Folder Table ID                                                                                         |

### Functions

#### [addFilesToCompressor](#addfilestocompressor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.addFilesToCompressor(files) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Imports a file into Final Cut Pro                                                                                         |
| **Parameters**                                       |  * files - File names in table                                       |
| **Returns**                                          |  * None                                                |

#### [addWatchFolder](#addwatchfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.addWatchFolder() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Opens the "Add Watch Folder" Dialog.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [controllerCallback](#controllercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.controllerCallback(id, params) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Callback Controller                                                                                         |
| **Parameters**                                       |  * id - ID as string * params - table of Parameters                                       |
| **Returns**                                          |  * None                                                |

#### [generateTable](#generatetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.generateTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generate HTML Table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Returns a HTML table as a string                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.init(deps, env) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       |  * deps - The dependencies environment * env - The plugin environment                                       |
| **Returns**                                          |  * Table of the module.                                                |

#### [newWatcher](#newwatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.newWatcher(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | New Folder Watcher                                                                                         |
| **Parameters**                                       |  * path - Path to Watch Folder                                       |
| **Returns**                                          |  * None                                                |

#### [refreshTable](#refreshtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.refreshTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Refreshes the Final Cut Pro Watch Folder Panel via JavaScript Injection                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [removeWatcher](#removewatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.removeWatcher(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Remove Folder Watcher                                                                                         |
| **Parameters**                                       |  * path - Path to Watch Folder                                       |
| **Returns**                                          |  * None                                                |

#### [setupWatchers](#setupwatchers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.setupWatchers(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Setup Folder Watchers                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [styleSheet](#stylesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.styleSheet() -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates Style Sheet                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Returns Style Sheet as a `cp.web.html` block.                                                |

#### [watchCompressorStatus](#watchcompressorstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.watchCompressorStatus(jobID) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks the Status of a Job in Compressor                                                                                         |
| **Parameters**                                       |  * jobID - Job ID as string * file - File Path as string * destinationPath - Destination Path as string                                       |
| **Returns**                                          |  * None                                                |

#### [watchFolderTriggered](#watchfoldertriggered)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.watchFolderTriggered(files) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Watch Folder Triggered                                                                                         |
| **Parameters**                                       |  * files - A table of files                                       |
| **Returns**                                          |  * None                                                |

