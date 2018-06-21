# [docs](index.md) » cp.apple.finalcutpro.main.LibrariesBrowser
---

Libraries Browser Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [ALL_CLIPS](#all_clips)
 * [FAVORITES](#favorites)
 * [HIDE_REJECTED](#hide_rejected)
 * [NO_RATINGS_OR_KEYWORDS](#no_ratings_or_keywords)
 * [REJECTED](#rejected)
 * [UNUSED](#unused)
* Functions - API calls offered directly by the extension
 * [clips](#clips)
 * [clipsUI](#clipsui)
 * [deselectAll](#deselectall)
 * [matchesSidebar](#matchessidebar)
 * [openClipTitled](#opencliptitled)
 * [selectAll](#selectall)
 * [selectClip](#selectclip)
 * [selectClipAt](#selectclipat)
 * [selectClipTitled](#selectcliptitled)
 * [selectedClips](#selectedclips)
 * [selectedClipsUI](#selectedclipsui)
 * [selectLibrary](#selectlibrary)
 * [showClip](#showclip)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [appearanceAndFiltering](#appearanceandfiltering)
 * [filmstrip](#filmstrip)
 * [filterToggle](#filtertoggle)
 * [hide](#hide)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [playhead](#playhead)
 * [saveLayout](#savelayout)
 * [search](#search)
 * [searchToggle](#searchtoggle)
 * [selectClipFiltering](#selectclipfiltering)
 * [show](#show)
 * [sidebar](#sidebar)
 * [skimmingPlayhead](#skimmingplayhead)
 * [toggleViewMode](#toggleviewmode)

## API Documentation

### Constants

#### [ALL_CLIPS](#all_clips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.ALL_CLIPS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | All Clips ID.                                                                                         |

#### [FAVORITES](#favorites)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.FAVORITES -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Favourites ID.                                                                                         |

#### [HIDE_REJECTED](#hide_rejected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.HIDE_REJECTED -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Hide Rejected ID.                                                                                         |

#### [NO_RATINGS_OR_KEYWORDS](#no_ratings_or_keywords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.NO_RATINGS_OR_KEYWORDS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | No Rating or Keywords ID.                                                                                         |

#### [REJECTED](#rejected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.REJECTED -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Rejected ID.                                                                                         |

#### [UNUSED](#unused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.UNUSED -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Unused ID.                                                                                         |

### Functions

#### [clips](#clips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:clips(filterFn) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets clips using a custom filter.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">filterFn - A function to filter the UI results.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table of `Clip` objects or `nil` if no clip UI could be found.</li></ul>          |

#### [clipsUI](#clipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:clipsUI(filterFn) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets clip UIs using a custom filter.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">filterFn - A function to filter the UI results.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table of `axuielementObject` objects or `nil` if no clip UI could be found.</li></ul>          |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:deselectAll() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Deselect all clips.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful otherwise `false`.</li></ul>          |

#### [matchesSidebar](#matchessidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.matchesSidebar(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches the Sidebar type.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">element - The element to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if there's a match, otherwise `false`.</li></ul>          |

#### [openClipTitled](#opencliptitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:openClipTitled(name) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Open a clip with a specific title.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">name - The name of the clip you want to open.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful, otherwise `false`.</li></ul>          |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectAll([clips]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Select all clips.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">clips - A optional table of `Clip` objects.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful otherwise `false`.</li></ul>          |

#### [selectClip](#selectclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects a clip.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">clip - The `Clip` you want to select.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful otherwise `false`.</li></ul>          |

#### [selectClipAt](#selectclipat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectClipAt(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Select clip at a specific index.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">index - A number of where the clip appears in the list.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful otherwise `false`.</li></ul>          |

#### [selectClipTitled](#selectcliptitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectClipTitled(title) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Select clip with a specific title.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">title - The title of a clip.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful otherwise `false`.</li></ul>          |

#### [selectedClips](#selectedclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectedClips() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets selected clips.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table of `Clip` objects or `nil` if no clips are selected.</li></ul>          |

#### [selectedClipsUI](#selectedclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectedClipsUI() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets selected clips UI's.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table of `axuielementObject` objects or `nil` if no clips are selected.</li></ul>          |

#### [selectLibrary](#selectlibrary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectLibrary(...) -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects a Library.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">... - Libraries as string.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `Table` object.</li></ul>          |

#### [showClip](#showclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:showClip(clip) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows a clip.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">clip - The `Clip` you want to show.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful otherwise `false`.</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser.new(app) -> LibrariesBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `LibrariesBrowser` instance.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">parent - The parent object.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A new `LibrariesBrowser` object.</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">App</li></ul>          |

#### [appearanceAndFiltering](#appearanceandfiltering)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:appearanceAndFiltering() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Appearance & Filtering Button.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `Button` object.</li></ul>          |

#### [filmstrip](#filmstrip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:filmstrip() -> LibrariesList` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Libraries List object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `LibrariesList` object.</li></ul>          |

#### [filterToggle](#filtertoggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:filterToggle() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The Filter Toggle Button.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `Button` object.</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:hide() -> LibrariesBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hide the Libraries Browser.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `LibrariesBrowser` object.</li></ul>          |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Libraries Browser layout.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">layout - A table containing the Libraries Browser layout settings - created using `cp.apple.finalcutpro.main.LibrariesBrowser:saveLayout()`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">parent</li></ul>          |

#### [playhead](#playhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:playhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Libraries Browser Playhead.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `Playhead` object.</li></ul>          |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Libraries Browser layout to a table.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table containing the current Libraries Browser Layout.</li></ul>          |

#### [search](#search)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:search() -> TextField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Search Text Field.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `TextField` object.</li></ul>          |

#### [searchToggle](#searchtoggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:searchToggle() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Search Toggle Button.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `Button` object.</li></ul>          |

#### [selectClipFiltering](#selectclipfiltering)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:selectClipFiltering(filterType) -> LibrariesBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select Clip Filtering based on Filter Type.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">filterType - The filter type.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `LibrariesBrowser` object.</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:show() -> LibrariesBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show the Libraries Browser.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `LibrariesBrowser` object.</li></ul>          |

#### [sidebar](#sidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:sidebar() -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Libraries sidebar object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`Table` object.</li></ul>          |

#### [skimmingPlayhead](#skimmingplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:skimmingPlayhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Libraries Browser Skimming Playhead.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `Playhead` object.</li></ul>          |

#### [toggleViewMode](#toggleviewmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.LibrariesBrowser:toggleViewMode() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Toggle View Mode button.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `Button` object.</li></ul>          |

