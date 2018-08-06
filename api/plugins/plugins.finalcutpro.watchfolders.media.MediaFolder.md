# [docs](index.md) » plugins.finalcutpro.watchfolders.media.MediaFolder
---

Final Cut Pro Media Watch Folder Plugin.

## API Overview
* Functions - API calls offered directly by the extension
 * [freeze](#freeze)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [thaw](#thaw)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addIncoming](#addincoming)
 * [addReady](#addready)
 * [checkNotifications](#checknotifications)
 * [destroy](#destroy)
 * [doDeleteImportedFiles](#dodeleteimportedfiles)
 * [doImportNext](#doimportnext)
 * [doRestoreOriginalPasteboard](#dorestoreoriginalpasteboard)
 * [doRevealInFinder](#dorevealinfinder)
 * [doTagFiles](#dotagfiles)
 * [doWriteFilesToPasteboard](#dowritefilestopasteboard)
 * [handleImport](#handleimport)
 * [importAll](#importall)
 * [importFiles](#importfiles)
 * [importFirst](#importfirst)
 * [importTag](#importtag)
 * [init](#init)
 * [processFiles](#processfiles)
 * [removeFile](#removefile)
 * [save](#save)
 * [skipAll](#skipall)
 * [skipOne](#skipone)
 * [updateIncomingNotification](#updateincomingnotification)
 * [updateReadyNotification](#updatereadynotification)

## API Documentation

### Functions

#### [freeze](#freeze)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder.freeze(mediaFolder) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table with the details of the `MediaFolder`, ready to be stored. |
| **Parameters**                                       | <ul><li>mediaFolder   - The <code>MediaFolder</code> to freeze.</li></ul> |
| **Returns**                                          | <ul><li>A table of details.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder.new() -> MediaFolder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Media Folder. |
| **Parameters**                                       | <ul><li>mod - The module.</li><li>path - Path to the Media Folder.</li><li>videoTag - Video Tag as String</li><li>audioTag - Audio Tag as String</li><li>imageTag - Image Tag as String</li></ul> |
| **Returns**                                          | <ul><li>A new MediaFolder object.</li></ul> |

#### [thaw](#thaw)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder.thaw(details) -> MediaFolder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new MediaFolder based on the details provided. |
| **Parameters**                                       | <ul><li>details   - The table with details of the media folder when it was frozen.</li></ul> |
| **Returns**                                          | <ul><li>A new MediaFolder instance with the specified details.</li></ul> |

### Methods

#### [addIncoming](#addincoming)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:addIncoming(file) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds the file to the 'incoming' list and updates the notification. |
| **Parameters**                                       | <ul><li>file - The file to add.</li></ul> |
| **Returns**                                          | <ul><li>nil</li></ul> |

#### [addReady](#addready)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:addReady(file) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds the file to the 'ready' list and updates the notifications. |
| **Parameters**                                       | <ul><li>file      - The file to add.</li></ul> |
| **Returns**                                          | <ul><li>nil</li></ul> |

#### [checkNotifications](#checknotifications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:checkNotifications() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks Notifications. |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [destroy](#destroy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:destroy()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Destroys the MediaFolder. It should not be used after this is called. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [doDeleteImportedFiles](#dodeleteimportedfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:doDeleteImportedFiles(context) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if we are deleting after import, and if so schedules them to be deleted. |
| **Parameters**                                       | <ul><li>files - a table of file paths.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [doImportNext](#doimportnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:doImportNext() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Imports the next file in the Media Folder. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [doRestoreOriginalPasteboard](#dorestoreoriginalpasteboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:doRestoreOriginalPasteboard(context) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Restore original Pasteboard contents after 2 seconds. |
| **Parameters**                                       | <ul><li>context - The context.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [doRevealInFinder](#dorevealinfinder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:doRevealInFinder() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will reveal the MediaFolder path in the Finder. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Statement</li></ul> |

#### [doTagFiles](#dotagfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:doTagFiles(files) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Tags a table of files. |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [doWriteFilesToPasteboard](#dowritefilestopasteboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:doWriteFilesToPasteboard(files, context) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Write files to the Pasteboard. |
| **Parameters**                                       | <ul><li>files - a table/list of files to be imported.</li><li>context - The context.</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code> to execute.</li></ul> |

#### [handleImport](#handleimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:handleImport(notification) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Handles the importing of a file. |
| **Parameters**                                       | <ul><li>notification - The notification object.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [importAll](#importall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:importAll() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Begins importing all `ready` files, removing them from the `ready` queue. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [importFiles](#importfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:importFiles(files) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Requests for the files to be imported. |
| **Parameters**                                       | <ul><li>files - a table/list of files to be imported.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [importFirst](#importfirst)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:importFirst() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Begins importing the first `ready` file, removing it from the `ready` queue. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [importTag](#importtag)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:importTag() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the import tag. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The import tag as a string.</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:init() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Initialises the folder, getting any watchers, notifications, etc. running. |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [processFiles](#processfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:processFiles() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Process files. |
| **Parameters**                                       | <ul><li>files - A table of files to process.</li><li>fileFlags - A table of file flags.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [removeFile](#removefile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:removeFile(file) -> MediaFolder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes the file from any queues it might be in, updating relevant notifications. |
| **Parameters**                                       | <ul><li>file  - the full path to the file.</li></ul> |
| **Returns**                                          | <ul><li>The MediaFolder instance</li></ul> |

#### [save](#save)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:save()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensures the MediaFolder is saved. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [skipAll](#skipall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:skipAll() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Skip all files in the Media Folder. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [skipOne](#skipone)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:skipOne() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Skip one file in the Media Folder. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateIncomingNotification](#updateincomingnotification)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:updateIncomingNotification() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Updates the 'incoming' notification based on the current set of files in the `incoming` queue. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateReadyNotification](#updatereadynotification)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchfolders.media.MediaFolder:updateReadyNotification() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Updates the 'ready' notification based on the current set of files in the `ready` queue. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

