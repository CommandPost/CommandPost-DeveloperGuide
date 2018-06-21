# [docs](index.md) » plugins.finalcutpro.pasteboard.shared
---

Shared Pasteboard Plugin.

## API Overview
* Functions - API calls offered directly by the extension
 * [copyWithCustomClipName](#copywithcustomclipname)
 * [copyWithCustomClipNameAndFolder](#copywithcustomclipnameandfolder)
 * [generateSharedPasteboardMenu](#generatesharedpasteboardmenu)
 * [getHistory](#gethistory)
 * [getHistoryPath](#gethistorypath)
 * [getLocalFolderName](#getlocalfoldername)
 * [getRootPath](#getrootpath)
 * [init](#init)
 * [overrideNextFolderName](#overridenextfoldername)
 * [pasteHistoryItem](#pastehistoryitem)
 * [setHistory](#sethistory)
 * [setRootPath](#setrootpath)
 * [update](#update)
 * [validRootPath](#validrootpath)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)

## API Documentation

### Functions

#### [copyWithCustomClipName](#copywithcustomclipname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.copyWithCustomClipName() -> None` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Triggers a copy with custom clip name action.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [copyWithCustomClipNameAndFolder](#copywithcustomclipnameandfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.copyWithCustomClipNameAndFolder() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Copy with Custom Label & Folder.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [generateSharedPasteboardMenu](#generatesharedpasteboardmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.generateSharedPasteboardMenu() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates the shared pasteboard menu.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The shared pasteboard menu as a table.                                                |

#### [getHistory](#gethistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.getHistory(folderName) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the history for a supplied folder name.                                                                                         |
| **Parameters**                                       |  * folderName - The folder name                                       |
| **Returns**                                          |  * The history in a table.                                                |

#### [getHistoryPath](#gethistorypath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.getHistoryPath(folderName, fileExtension) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the History Path.                                                                                         |
| **Parameters**                                       |  * folderName - The folder name * fileExtension - The file extension                                       |
| **Returns**                                          |  * The history path as a string                                                |

#### [getLocalFolderName](#getlocalfoldername)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.getLocalFolderName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the local folder name.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The local folder name as a string.                                                |

#### [getRootPath](#getrootpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.getRootPath() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get shared pasteboard root path.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Shared Pasteboard Path as string.                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.init() -> sharedPasteboard` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       |  * manager - The pasteboard manager                                       |
| **Returns**                                          |  * The sharedPasteboard object                                                |

#### [overrideNextFolderName](#overridenextfoldername)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.overrideNextFolderName(overrideFolder) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Overrides the folder name for the next clip which is copied from Final Cut Pro to the                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The local folder name as a string.                                                |

#### [pasteHistoryItem](#pastehistoryitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.pasteHistoryItem(folderName, index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Paste History Item.                                                                                         |
| **Parameters**                                       |  * folderName - The folder name * index - The index of the item you want to paste                                       |
| **Returns**                                          |  * None                                                |

#### [setHistory](#sethistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.setHistory(folderName, history) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Clears the history.                                                                                         |
| **Parameters**                                       |  * folderName - The folder name                                       |
| **Returns**                                          |  * None                                                |

#### [setRootPath](#setrootpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.setRootPath(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the shared pasteboard root path.                                                                                         |
| **Parameters**                                       |  * path - The path you want to set as a string.                                       |
| **Returns**                                          |  * None                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.update() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the list of folder names as an array of strings.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table of folder names.                                                |

#### [validRootPath](#validrootpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.validRootPath() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets whether or not the current root path exists.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if it exists otherwise `false`.                                                |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Gets whether or not the shared pasteboard is enabled as a boolean.                                                                                         |

