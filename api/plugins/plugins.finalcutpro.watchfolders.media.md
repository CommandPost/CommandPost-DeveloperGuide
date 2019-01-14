# [docs](index.md) » plugins.finalcutpro.watchfolders.media
---

Final Cut Pro Media Watch Folder Plugin.

## Submodules
 * [plugins.finalcutpro.watchfolders.media.MediaFolder](plugins.finalcutpro.watchfolders.media.MediaFolder.md)
 * [plugins.finalcutpro.watchfolders.media.panel](plugins.finalcutpro.watchfolders.media.panel.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [SECONDS_UNTIL_DELETE](#seconds_until_delete)
* Variables - Configurable values
 * [automaticallyImport](#automaticallyimport)
 * [deleteAfterImport](#deleteafterimport)
 * [insertIntoTimeline](#insertintotimeline)
 * [mediaFolders](#mediafolders)
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [loadMediaFolders](#loadmediafolders)
 * [saveMediaFolders](#savemediafolders)

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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.mediaFolders -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The table of MediaFolders currently configured. |

### Functions

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

#### [saveMediaFolders](#savemediafolders)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.saveMediaFolders()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Saves the current state of the media folders, including notifications, etc. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

