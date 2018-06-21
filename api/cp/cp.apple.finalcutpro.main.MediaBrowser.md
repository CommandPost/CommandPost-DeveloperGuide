# [docs](index.md) » cp.apple.finalcutpro.main.MediaBrowser
---

Media Browser Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [GARAGE_BAND](#garage_band)
 * [ITUNES](#itunes)
 * [MAX_SECTIONS](#max_sections)
 * [PHOTOS](#photos)
 * [SOUND_EFFECTS](#sound_effects)
 * [TITLE](#title)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [group](#group)
 * [hide](#hide)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [saveLayout](#savelayout)
 * [search](#search)
 * [show](#show)
 * [showGarageBand](#showgarageband)
 * [showITunes](#showitunes)
 * [showPhotos](#showphotos)
 * [showSection](#showsection)
 * [showSoundEffects](#showsoundeffects)
 * [sidebar](#sidebar)

## API Documentation

### Constants

#### [GARAGE_BAND](#garage_band)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser.GARAGE_BAND -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Garage Band ID.                                                                                         |

#### [ITUNES](#itunes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser.ITUNES -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | iTunes ID.                                                                                         |

#### [MAX_SECTIONS](#max_sections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser.MAX_SECTIONS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Maximum Sections.                                                                                         |

#### [PHOTOS](#photos)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser.PHOTOS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Photos ID.                                                                                         |

#### [SOUND_EFFECTS](#sound_effects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser.SOUND_EFFECTS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Sound Effects ID.                                                                                         |

#### [TITLE](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser.TITLE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Photos & Audio Title.                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser.new(parent) -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Browser` instance.                                                                                         |
| **Parameters**                                       |  * parent - The parent object.                                       |
| **Returns**                                          |  * A new `MediaBrowser` object.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:group() -> PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the group PopUpButton.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `PopUpButton` object.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:hide() -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hide the Media Browser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `MediaBrowser` object.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Media Browser layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the Media Browser layout settings - created using `cp.apple.finalcutpro.main.MediaBrowser:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * parent                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Media Browser layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current Media Browser Layout.                                                |

#### [search](#search)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:search() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the Top Categories UI.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `axuielementObject` object.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:show() -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show the Media Browser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `MediaBrowser` object.                                                |

#### [showGarageBand](#showgarageband)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:showGarageBand() -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Garage Band Section.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `MediaBrowser` object.                                                |

#### [showITunes](#showitunes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:showITunes() -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show iTunes Section.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `MediaBrowser` object.                                                |

#### [showPhotos](#showphotos)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:showPhotos() -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Photos Section.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `MediaBrowser` object.                                                |

#### [showSection](#showsection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:showSection(index) -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show a specific section.                                                                                         |
| **Parameters**                                       |  * index - The index ID of the section you want to show as a number.                                       |
| **Returns**                                          |  * `MediaBrowser` object.                                                |

#### [showSoundEffects](#showsoundeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:showSoundEffects() -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Sound Effects Section.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `MediaBrowser` object.                                                |

#### [sidebar](#sidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.MediaBrowser:sidebar() -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the Sidebar Table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `Table` object.                                                |

