# [docs](index.md) » cp.apple.finalcutpro.main.Browser
---

Browser Module.

## Submodules
 * [cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover](cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [generators](#generators)
 * [hide](#hide)
 * [libraries](#libraries)
 * [loadLayout](#loadlayout)
 * [markerPopover](#markerpopover)
 * [media](#media)
 * [saveLayout](#savelayout)
 * [showGenerators](#showgenerators)
 * [showLibraries](#showlibraries)
 * [showMedia](#showmedia)
 * [showOnPrimary](#showonprimary)
 * [showOnSecondary](#showonsecondary)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.new(app) -> Browser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Browser` instance.                                                                                         |
| **Parameters**                                       |  * app - The Final Cut Pro app instance.                                       |
| **Returns**                                          |  * The new `Browser`.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [generators](#generators)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:generators() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Generators Browser object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `GeneratorsBrowser` object.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:hide() -> Browser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Browser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `Browser` object.                                                |

#### [libraries](#libraries)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:libraries() -> LibrariesBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Libraries Browser object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `LibrariesBrowser` object.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Browser layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the Browser layout settings - created using `cp.apple.finalcutpro.main.Browser:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [markerPopover](#markerpopover)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:markerPopover() -> BrowserMarkerPopover` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Browser Marker Popover object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `BrowserMarkerPopover` object.                                                |

#### [media](#media)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:media() -> MediaBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get Media Browser object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `MediaBrowser` object.                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Browser layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current Browser Layout.                                                |

#### [showGenerators](#showgenerators)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:showGenerators() -> CheckBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Media.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `CheckBox` object.                                                |

#### [showLibraries](#showlibraries)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:showLibraries() -> CheckBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows Libraries.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `CheckBox` object.                                                |

#### [showMedia](#showmedia)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:showMedia() -> CheckBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Media.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `CheckBox` object.                                                |

#### [showOnPrimary](#showonprimary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:showOnPrimary() -> Browser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Browser on Primary Screen.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `Browser` object.                                                |

#### [showOnSecondary](#showonsecondary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser:showOnSecondary() -> Browser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Browser on Secondary Screen.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `Browser` object.                                                |

