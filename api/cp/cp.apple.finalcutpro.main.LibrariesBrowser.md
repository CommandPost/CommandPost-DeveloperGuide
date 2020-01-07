# [docs](index.md) » cp.apple.finalcutpro.main.LibrariesBrowser
---

Libraries Browser Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [deselectAll](#deselectall)
 * [indexOfClip](#indexofclip)
* Constructors - API calls which return an object, typically one that offers API methods
 * [LibrariesBrowser](#librariesbrowser)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [clipFiltering](#clipfiltering)
 * [isFilmstripView](#isfilmstripview)
 * [isFocused](#isfocused)
 * [isListView](#islistview)
 * [mainGroupUI](#maingroupui)
 * [search](#search)
 * [searchToggle](#searchtoggle)
 * [toggleViewMode](#toggleviewmode)
* Methods - API calls which can only be made on an object returned by a constructor
 * [clips](#clips)
 * [clipsUI](#clipsui)
 * [doFindClips](#dofindclips)
 * [doFindClipsTitled](#dofindclipstitled)
 * [doHide](#dohide)
 * [doOpenClipTitled](#doopencliptitled)
 * [doSelectClipTitled](#doselectcliptitled)
 * [doShow](#doshow)
 * [filmstrip](#filmstrip)
 * [hide](#hide)
 * [list](#list)
 * [loadLayout](#loadlayout)
 * [openClipTitled](#opencliptitled)
 * [playhead](#playhead)
 * [saveLayout](#savelayout)
 * [selectAll](#selectall)
 * [selectClip](#selectclip)
 * [selectClipAt](#selectclipat)
 * [selectClipTitled](#selectcliptitled)
 * [selectedClips](#selectedclips)
 * [selectedClipsUI](#selectedclipsui)
 * [selectLibrary](#selectlibrary)
 * [show](#show)
 * [showClip](#showclip)
 * [sidebar](#sidebar)
 * [skimmingPlayhead](#skimmingplayhead)

## API Documentation

### Functions

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:deselectAll() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Deselect all clips. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [indexOfClip](#indexofclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:indexOfClip(clip) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the index of a specific clip. |
| **Parameters**                                       | <ul><li>clip - The <code>Clip</code> you want to get the index of.</li></ul> |
| **Returns**                                          | <ul><li>The index or <code>nil</code> if an error occurs.</li></ul> |

### Constructors

#### [LibrariesBrowser](#librariesbrowser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser(app) -> LibrariesBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `LibrariesBrowser` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>LibrariesBrowser</code> object.</li></ul> |

### Fields

#### [clipFiltering](#clipfiltering)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.clipFiltering <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Clip Filtering [PopUpButton](cp.ui.PopUpButton.md). |

#### [isFilmstripView](#isfilmstripview)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.isFilmstripView <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the Library Browser is in 'filmstrip view' mode. |

#### [isFocused](#isfocused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.isFocused <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the Libraries Browser is the current focus. |

#### [isListView](#islistview)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.isListView <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the Library Browser is in 'list view' mode. |

#### [mainGroupUI](#maingroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.mainGroupUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the main group within the Libraries Browser, or `nil` if not available.. |

#### [search](#search)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.search <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Search [TextField](cp.ui.TextField.md). |

#### [searchToggle](#searchtoggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.searchToggle <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Search Toggle [Button](cp.ui.Button.md). |

#### [toggleViewMode](#toggleviewmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.toggleViewMode <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Toggle View Mode [Button](cp.ui.Button.md). |

### Methods

#### [clips](#clips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:clips(filterFn) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets clips using a custom filter. |
| **Parameters**                                       | <ul><li>filterFn - A function to filter the UI results.</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>Clip</code> objects or <code>nil</code> if no clip UI could be found.</li></ul> |

#### [clipsUI](#clipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:clipsUI(filterFn) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets clip UIs using a custom filter. |
| **Parameters**                                       | <ul><li>filterFn - A function to filter the UI results.</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>axuielementObject</code> objects or <code>nil</code> if no clip UI could be found.</li></ul> |

#### [doFindClips](#dofindclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:doFindClips(filter) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which will send each clip in the Libraries Browser matching the `filter` as an `onNext` signal. |
| **Parameters**                                       | <ul><li>filter    - a function which receives the <a href="cp.apple.finalcutpro.content.Clip.md">Clip</a> to check and returns <code>true</code> or <code>false</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>.</li></ul> |

#### [doFindClipsTitled](#dofindclipstitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:doFindClipsTitled(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which will send each clip in the Libraries Browser with the specified `title` as an `onNext` signal. |
| **Parameters**                                       | <ul><li>title    - The title string to check for.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>.</li></ul> |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will hide the Libraries Browser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>.</li></ul> |

#### [doOpenClipTitled](#doopencliptitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:doOpenClipTitled(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to open the named clip in the Libraries Browser in the Timeline. |
| **Parameters**                                       | <ul><li>title      - The title of the clip to open.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute.</li></ul> |

#### [doSelectClipTitled](#doselectcliptitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:doSelectClipTitled(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which will select the first clip with a matching `title`. |
| **Parameters**                                       | <ul><li>title     - The title to select.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> ready to execute.</li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will show the Libraries Browser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> object.</li></ul> |

#### [filmstrip](#filmstrip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:filmstrip() -> LibrariesFilmstrip` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get Libraries Film Strip object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>LibrariesBrowser</code> object.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:hide() -> LibrariesBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hide the Libraries Browser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>LibrariesBrowser</code> object.</li></ul> |

#### [list](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:list() -> LibrariesList` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get [LibrariesList](cp.apple.finalcutpro.main.LibrariesList.md) object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>LibrariesList</code> object.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a Libraries Browser layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the Libraries Browser layout settings - created using <code>cp.apple.finalcutpro.main.LibrariesBrowser:saveLayout()</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [openClipTitled](#opencliptitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:openClipTitled(name) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Open a clip with a specific title. |
| **Parameters**                                       | <ul><li>name - The name of the clip you want to open.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, otherwise <code>false</code>.</li></ul> |

#### [playhead](#playhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:playhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Libraries Browser Playhead. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Playhead</code> object.</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current Libraries Browser layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current Libraries Browser Layout.</li></ul> |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectAll([clips]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select all clips. |
| **Parameters**                                       | <ul><li>clips - A optional table of <code>Clip</code> objects.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectClip](#selectclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects a clip. |
| **Parameters**                                       | <ul><li>clip - The <code>Clip</code> you want to select.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectClipAt](#selectclipat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectClipAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select clip at a specific index. |
| **Parameters**                                       | <ul><li>index - A number of where the clip appears in the list.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectClipTitled](#selectcliptitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectClipTitled(title) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select clip with a specific title. |
| **Parameters**                                       | <ul><li>title - The title of a clip.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectedClips](#selectedclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectedClips() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets selected clips. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>Clip</code> objects or <code>nil</code> if no clips are selected.</li></ul> |

#### [selectedClipsUI](#selectedclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectedClipsUI() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets selected clips UI's. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>axuielementObject</code> objects or <code>nil</code> if no clips are selected.</li></ul> |

#### [selectLibrary](#selectlibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectLibrary(...) -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects a Library. |
| **Parameters**                                       | <ul><li>... - Libraries as string.</li></ul> |
| **Returns**                                          | <ul><li>A <code>Table</code> object.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:show() -> LibrariesBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show the Libraries Browser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>LibrariesBrowser</code> object.</li></ul> |

#### [showClip](#showclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:showClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows a clip. |
| **Parameters**                                       | <ul><li>clip - The <code>Clip</code> you want to show.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [sidebar](#sidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.sidebar <cp.apple.finalcutpro.main.LibrariesSidebar>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The  [LibrariesSidebar](cp.apple.finalcutpro.main.LibrariesSidebar.md) Table |

#### [skimmingPlayhead](#skimmingplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:skimmingPlayhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Libraries Browser Skimming Playhead. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Playhead</code> object.</li></ul> |

