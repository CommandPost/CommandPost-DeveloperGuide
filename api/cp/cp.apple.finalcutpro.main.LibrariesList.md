# [docs](index.md) » cp.apple.finalcutpro.main.LibrariesList
---

Libraries List Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [clips](#clips)
 * [clipsUI](#clipsui)
 * [deselectAll](#deselectall)
 * [indexOfClip](#indexofclip)
 * [selectAll](#selectall)
 * [selectClip](#selectclip)
 * [selectClipAt](#selectclipat)
 * [selectClipTitled](#selectcliptitled)
 * [selectedClips](#selectedclips)
 * [selectedClipsUI](#selectedclipsui)
 * [showClip](#showclip)
* Constructors - API calls which return an object, typically one that offers API methods
 * [LibrariesList](#librarieslist)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contents](#contents)
 * [isFocused](#isfocused)
 * [isShowing](#isshowing)
 * [playerUI](#playerui)
 * [playhead](#playhead)
 * [skimmingPlayhead](#skimmingplayhead)
* Methods - API calls which can only be made on an object returned by a constructor
 * [columns](#columns)
 * [show](#show)

## API Documentation

### Functions

#### [clips](#clips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:clips(filterFn) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets clips using a custom filter. |
| **Parameters**                                       | <ul><li>filterFn - A function to filter the UI results.</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>Clip</code> objects or <code>nil</code> if no clip UI could be found.</li></ul> |

#### [clipsUI](#clipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:clipsUI(filterFn) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets clip UIs using a custom filter. |
| **Parameters**                                       | <ul><li>filterFn - A function to filter the UI results.</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>axuielementObject</code> objects or <code>nil</code> if no clip UI could be found.</li></ul> |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:deselectAll() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Deselect all clips. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [indexOfClip](#indexofclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:indexOfClip(clip) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the index of a specific clip. |
| **Parameters**                                       | <ul><li>clip - The <code>Clip</code> you want to get the index of.</li></ul> |
| **Returns**                                          | <ul><li>The index or <code>nil</code> if an error occurs.</li></ul> |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:selectAll([clips]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Select all clips. |
| **Parameters**                                       | <ul><li>clips - A optional table of <code>Clip</code> objects.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectClip](#selectclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:selectClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Selects a clip. |
| **Parameters**                                       | <ul><li>clip - The <code>Clip</code> you want to select.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectClipAt](#selectclipat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:selectClipAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Select clip at a specific index. |
| **Parameters**                                       | <ul><li>index - A number of where the clip appears in the list.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectClipTitled](#selectcliptitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:selectClipTitled(title) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Select clip with a specific title. |
| **Parameters**                                       | <ul><li>title - The title of a clip.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectedClips](#selectedclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:selectedClips() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets selected clips. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>Clip</code> objects or <code>nil</code> if no clips are selected.</li></ul> |

#### [selectedClipsUI](#selectedclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:selectedClipsUI() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets selected clips UI's. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>axuielementObject</code> objects or <code>nil</code> if no clips are selected.</li></ul> |

#### [showClip](#showclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:showClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Shows a clip. |
| **Parameters**                                       | <ul><li>clip - The <code>Clip</code> you want to show.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

### Constructors

#### [LibrariesList](#librarieslist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList(app) -> LibrariesList` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `LibrariesList` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>LibrariesList</code> object.</li></ul> |

### Fields

#### [contents](#contents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList.contents <cp.ui.Table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Libraries List Contents UI. |

#### [isFocused](#isfocused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList.isFocused <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Libraries List is currently focused within FCPX. |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Libraries List is showing on screen. |

#### [playerUI](#playerui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList.playerUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` for the player section of the Libraries List UI. |

#### [playhead](#playhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList.playhead <Playhead>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Libraries List Playhead. |

#### [skimmingPlayhead](#skimmingplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList.skimmingPlayhead <Playhead>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | the Libraries List Skimming Playhead. |

### Methods

#### [columns](#columns)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:columns() -> Columns` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the List View Columns object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>AppearanceAndFiltering</code> object.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesList:show() -> LibrariesList` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show the Libraries List. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>LibrariesList</code> object</li></ul> |

