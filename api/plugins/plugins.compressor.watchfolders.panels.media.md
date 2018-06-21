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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">files - File names in table</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [addWatchFolder](#addwatchfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.addWatchFolder() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Opens the "Add Watch Folder" Dialog.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [controllerCallback](#controllercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.controllerCallback(id, params) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Callback Controller                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">id - ID as string</li><li markdown="1">params - table of Parameters</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [generateTable](#generatetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.generateTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generate HTML Table                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Returns a HTML table as a string</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.init(deps, env) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">deps - The dependencies environment</li><li markdown="1">env - The plugin environment</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Table of the module.</li></ul>          |

#### [newWatcher](#newwatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.newWatcher(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | New Folder Watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - Path to Watch Folder</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [refreshTable](#refreshtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.refreshTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Refreshes the Final Cut Pro Watch Folder Panel via JavaScript Injection                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [removeWatcher](#removewatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.removeWatcher(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Remove Folder Watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - Path to Watch Folder</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [setupWatchers](#setupwatchers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.setupWatchers(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Setup Folder Watchers                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [styleSheet](#stylesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.styleSheet() -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates Style Sheet                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Returns Style Sheet as a `cp.web.html` block.</li></ul>          |

#### [watchCompressorStatus](#watchcompressorstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.watchCompressorStatus(jobID) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks the Status of a Job in Compressor                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">jobID - Job ID as string</li><li markdown="1">file - File Path as string</li><li markdown="1">destinationPath - Destination Path as string</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [watchFolderTriggered](#watchfoldertriggered)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.compressor.watchfolders.panels.media.watchFolderTriggered(files) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Watch Folder Triggered                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">files - A table of files</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

