# [docs](index.md) » plugins.finalcutpro.watchfolders.media
---

Final Cut Pro Media Watch Folder Plugin.

## Submodules
 * [plugins.finalcutpro.watchfolders.media.MediaFolder](plugins.finalcutpro.watchfolders.media.MediaFolder.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [SECONDS_UNTIL_DELETE](#seconds_until_delete)
* Variables - Configurable values
 * [automaticallyImport](#automaticallyimport)
 * [deleteAfterImport](#deleteafterimport)
 * [insertIntoTimeline](#insertintotimeline)
 * [mediaFolders](#mediafolders)
 * [watchFolderTableID](#watchfoldertableid)
* Functions - API calls offered directly by the extension
 * [addWatchFolder](#addwatchfolder)
 * [controllerCallback](#controllercallback)
 * [generateTable](#generatetable)
 * [init](#init)
 * [loadMediaFolders](#loadmediafolders)
 * [refreshTable](#refreshtable)
 * [saveMediaFolders](#savemediafolders)
 * [styleSheet](#stylesheet)

## API Documentation

### Constants

#### [SECONDS_UNTIL_DELETE](#seconds_until_delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.SECONDS_UNTIL_DELETE -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Seconds until a file is deleted. |

### Variables

#### [automaticallyImport](#automaticallyimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.automaticallyImport <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Boolean that sets whether or not new generated voice file are automatically added to the timeline or not. |

#### [deleteAfterImport](#deleteafterimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.deleteAfterImport <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Boolean that sets whether or not you want to delete file after they've been imported. |

#### [insertIntoTimeline](#insertintotimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.insertIntoTimeline <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Boolean that sets whether or not the files are automatically added to the timeline or not. |

#### [mediaFolders](#mediafolders)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.mediaFolders` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The table of MediaFolders currently configured. |

#### [watchFolderTableID](#watchfoldertableid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.watchFolderTableID -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Watch Folder Table ID |

### Functions

#### [addWatchFolder](#addwatchfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.addWatchFolder() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Opens the "Add Watch Folder" Dialog. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [controllerCallback](#controllercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.controllerCallback(id, params) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Callback Controller |
| **Parameters**                                       | <ul><li>id - ID as string</li><li>params - table of Parameters</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [generateTable](#generatetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.generateTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generate HTML Table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns a HTML table as a string</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.init(deps, env) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the module. |
| **Parameters**                                       | <ul><li>deps - The dependencies environment</li><li>env - The plugin environment</li></ul> |
| **Returns**                                          | <ul><li>Table of the module.</li></ul> |

#### [loadMediaFolders](#loadmediafolders)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.loadMediaFolders()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Loads the MediaFolder list from storage. Any existing MediaFolder instances |

#### [refreshTable](#refreshtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.refreshTable() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Refreshes the Final Cut Pro Watch Folder Panel via JavaScript Injection |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [saveMediaFolders](#savemediafolders)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.saveMediaFolders()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Saves the current state of the media folders, including notifications, etc. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

#### [styleSheet](#stylesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.styleSheet() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates Style Sheet |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns Style Sheet as a string</li></ul> |

