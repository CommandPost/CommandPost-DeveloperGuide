# [docs](index.md) » cp.apple.finalcutpro.main.LibrariesFilmstrip
---

Libraries Filmstrip Module.

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
 * [showClipAt](#showclipat)
 * [sortClips](#sortclips)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [parent](#parent)
 * [playhead](#playhead)
 * [show](#show)
 * [skimmingPlayhead](#skimmingplayhead)

## API Documentation

### Functions

#### [clips](#clips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:clips(filterFn) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets clips using a custom filter. |
| **Parameters**                                       | <ul><li>filterFn - A function to filter the UI results.</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>Clip</code> objects or <code>nil</code> if no clip UI could be found.</li></ul> |

#### [clipsUI](#clipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:clipsUI(filterFn) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets clip UIs using a custom filter. |
| **Parameters**                                       | <ul><li>filterFn - A function to filter the UI results.</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>axuielementObject</code> objects or <code>nil</code> if no clip UI could be found.</li></ul> |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:deselectAll() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Deselect all clips. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [indexOfClip](#indexofclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:indexOfClip(clip) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the index of a specific clip. |
| **Parameters**                                       | <ul><li>clip - The <code>Clip</code> you want to get the index of.</li></ul> |
| **Returns**                                          | <ul><li>The index or <code>nil</code> if an error occurs.</li></ul> |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectAll([clips]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Select all clips. |
| **Parameters**                                       | <ul><li>clips - A optional table of <code>Clip</code> objects.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectClip](#selectclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip.selectClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Selects a clip. |
| **Parameters**                                       | <ul><li>clip - The <code>Clip</code> you want to select.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectClipAt](#selectclipat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectClipAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Select clip at a specific index. |
| **Parameters**                                       | <ul><li>index - A number of where the clip appears in the list.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectClipTitled](#selectcliptitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectClipTitled(title) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Select clip with a specific title. |
| **Parameters**                                       | <ul><li>title - The title of a clip.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [selectedClips](#selectedclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectedClips() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets selected clips. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>Clip</code> objects or <code>nil</code> if no clips are selected.</li></ul> |

#### [selectedClipsUI](#selectedclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectedClipsUI() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets selected clips UI's. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>axuielementObject</code> objects or <code>nil</code> if no clips are selected.</li></ul> |

#### [showClip](#showclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:showClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Shows a clip. |
| **Parameters**                                       | <ul><li>clip - The <code>Clip</code> you want to show.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [showClipAt](#showclipat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:showClipAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Shows a clip at a specific index. |
| **Parameters**                                       | <ul><li>index - The index of the clip you want to show.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [sortClips](#sortclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip.sortClips(a,b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Determines if clip A is above clip B or not. |
| **Parameters**                                       | <ul><li>a - Clip A</li><li>b - Clip B</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if clip A is above clip B, otherwise <code>false</code>.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip.new(app) -> LibrariesFilmstrip` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `LibrariesFilmstrip` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object</li></ul> |
| **Returns**                                          | <ul><li>A new <code>LibrariesFilmstrip</code> object.</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the app instance representing Final Cut Pro. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the parent object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>parent</li></ul> |

#### [playhead](#playhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:playhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get the Libraries Filmstrip Playhead. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>Playhead</code> object</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:show() -> LibrariesFilmstrip` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show the Libraries Filmstrip. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>LibrariesFilmstrip</code> object</li></ul> |

#### [skimmingPlayhead](#skimmingplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:skimmingPlayhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get the Libraries Filmstrip Skimming Playhead. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>Playhead</code> object</li></ul> |

