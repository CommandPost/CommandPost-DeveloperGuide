# [docs](index.md) » cp.apple.finalcutpro.main.LibrariesFilmstrip
---

Libraries Filmstrip Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [clips](#clips)
 * [clipsUI](#clipsui)
 * [deselectAll](#deselectall)
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
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets clips using a custom filter.                                                                                         |
| **Parameters**                                       |  * filterFn - A function to filter the UI results.                                       |
| **Returns**                                          |  * A table of `Clip` objects or `nil` if no clip UI could be found.                                                |

#### [clipsUI](#clipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:clipsUI(filterFn) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets clip UIs using a custom filter.                                                                                         |
| **Parameters**                                       |  * filterFn - A function to filter the UI results.                                       |
| **Returns**                                          |  * A table of `axuielementObject` objects or `nil` if no clip UI could be found.                                                |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:deselectAll() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Deselect all clips.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectAll([clips]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Select all clips.                                                                                         |
| **Parameters**                                       |  * clips - A optional table of `Clip` objects.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [selectClip](#selectclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip.selectClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects a clip.                                                                                         |
| **Parameters**                                       |  * clip - The `Clip` you want to select.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [selectClipAt](#selectclipat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectClipAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Select clip at a specific index.                                                                                         |
| **Parameters**                                       |  * index - A number of where the clip appears in the list.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [selectClipTitled](#selectcliptitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectClipTitled(title) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Select clip with a specific title.                                                                                         |
| **Parameters**                                       |  * title - The title of a clip.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [selectedClips](#selectedclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectedClips() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets selected clips.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table of `Clip` objects or `nil` if no clips are selected.                                                |

#### [selectedClipsUI](#selectedclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:selectedClipsUI() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets selected clips UI's.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table of `axuielementObject` objects or `nil` if no clips are selected.                                                |

#### [showClip](#showclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:showClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows a clip.                                                                                         |
| **Parameters**                                       |  * clip - The `Clip` you want to show.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [showClipAt](#showclipat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:showClipAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows a clip at a specific index.                                                                                         |
| **Parameters**                                       |  * index - The index of the clip you want to show.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [sortClips](#sortclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip.sortClips(a,b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Determines if clip A is above clip B or not.                                                                                         |
| **Parameters**                                       |  * a - Clip A * b - Clip B                                       |
| **Returns**                                          |  * `true` if clip A is above clip B, otherwise `false`.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip.new(app) -> LibrariesFilmstrip` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `LibrariesFilmstrip` instance.                                                                                         |
| **Parameters**                                       |  * parent - The parent object                                       |
| **Returns**                                          |  * A new `LibrariesFilmstrip` object.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * parent                                                |

#### [playhead](#playhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:playhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the Libraries Filmstrip Playhead.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `Playhead` object                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:show() -> LibrariesFilmstrip` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show the Libraries Filmstrip.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `LibrariesFilmstrip` object                                                |

#### [skimmingPlayhead](#skimmingplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesFilmstrip:skimmingPlayhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the Libraries Filmstrip Skimming Playhead.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `Playhead` object                                                |

