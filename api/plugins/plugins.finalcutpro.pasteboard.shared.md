# [docs](index.md) » plugins.finalcutpro.pasteboard.shared
---

Shared Pasteboard Plugin.

## API Overview
* Functions - API calls offered directly by the extension
 * [copyWithCustomClipName](#copywithcustomclipname)
 * [copyWithCustomClipNameAndFolder](#copywithcustomclipnameandfolder)
 * [doDecodeHistoryItem](#dodecodehistoryitem)
 * [doPasteHistoryItem](#dopastehistoryitem)
 * [generateSharedPasteboardMenu](#generatesharedpasteboardmenu)
 * [getFolderNames](#getfoldernames)
 * [getHistory](#gethistory)
 * [getHistoryPath](#gethistorypath)
 * [getLocalFolderName](#getlocalfoldername)
 * [getRootPath](#getrootpath)
 * [overrideNextFolderName](#overridenextfoldername)
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
| **Type**                                             | Function |
| **Description**                                      | Triggers a copy with custom clip name action. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [copyWithCustomClipNameAndFolder](#copywithcustomclipnameandfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.copyWithCustomClipNameAndFolder() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Copy with Custom Label & Folder. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [doDecodeHistoryItem](#dodecodehistoryitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.doDecodeHistoryItem(folderName, index) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Decodes a Paste History Item. |
| **Parameters**                                       | <ul><li>folderName - The folder name</li><li>index - The index of the item you want to decode</li></ul> |
| **Returns**                                          | <ul><li>The decoded Pasteboard History Item or <code>nil</code>.</li></ul> |

#### [doPasteHistoryItem](#dopastehistoryitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.doPasteHistoryItem(folderName, index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Paste History Item. |
| **Parameters**                                       | <ul><li>folderName - The folder name</li><li>index - The index of the item you want to paste</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [generateSharedPasteboardMenu](#generatesharedpasteboardmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.generateSharedPasteboardMenu() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates the shared pasteboard menu. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The shared pasteboard menu as a table.</li></ul> |

#### [getFolderNames](#getfoldernames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.getFolderNames() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the list of folder names as an array of strings. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of folder names.</li></ul> |

#### [getHistory](#gethistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.getHistory(folderName) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the history for a supplied folder name. |
| **Parameters**                                       | <ul><li>folderName - The folder name</li></ul> |
| **Returns**                                          | <ul><li>The history in a table.</li></ul> |

#### [getHistoryPath](#gethistorypath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.getHistoryPath(folderName, fileExtension) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the History Path. |
| **Parameters**                                       | <ul><li>folderName - The folder name</li><li>fileExtension - The file extension</li></ul> |
| **Returns**                                          | <ul><li>The history path as a string</li></ul> |

#### [getLocalFolderName](#getlocalfoldername)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.getLocalFolderName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the local folder name. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The local folder name as a string.</li></ul> |

#### [getRootPath](#getrootpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.getRootPath() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get shared pasteboard root path. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Shared Pasteboard Path as string.</li></ul> |

#### [overrideNextFolderName](#overridenextfoldername)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.overrideNextFolderName(overrideFolder) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Overrides the folder name for the next clip which is copied from Final Cut Pro to the |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The local folder name as a string.</li></ul> |

#### [setHistory](#sethistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.setHistory(folderName, history) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Clears the history. |
| **Parameters**                                       | <ul><li>folderName - The folder name</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setRootPath](#setrootpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.setRootPath(path) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets the shared pasteboard root path. |
| **Parameters**                                       | <ul><li>path - The path you want to set as a string.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Starts or stops the Shared Pasteboard watcher. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [validRootPath](#validrootpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.validRootPath() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets whether or not the current root path exists. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it exists otherwise <code>false</code>.</li></ul> |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.shared.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets whether or not the shared pasteboard is enabled as a boolean. |

