# [docs](index.md) » cp.apple.finalcutpro.MenuBar
---

Represents the Final Cut Pro menu bar, providing functions that allow different tasks to be accomplished.

## API Overview
* Constants - Useful values which cannot be changed
 * [ROLE](#role)
* Functions - API calls offered directly by the extension
 * [new](#new)
 * [selectMenu](#selectmenu)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addMenuFinder](#addmenufinder)
 * [app](#app)
 * [checkMenu](#checkmenu)
 * [findMenuItemsUI](#findmenuitemsui)
 * [findMenuUI](#findmenuui)
 * [getMainMenu](#getmainmenu)
 * [isChecked](#ischecked)
 * [isEnabled](#isenabled)
 * [isShowing](#isshowing)
 * [UI](#ui)
 * [uncheckMenu](#uncheckmenu)
 * [visitMenuItems](#visitmenuitems)

## API Documentation

### Constants

#### [ROLE](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar.ROLE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The menubar role                                                                                         |

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:new(App) -> MenuBar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Constructs a new MenuBar for the specified App.                                                                                         |
| **Parameters**                                       | <ul><li>app - The App instance the MenuBar belongs to.</li></ul> |
| **Returns**                                          | <ul><li>a new MenuBar instance</li></ul>          |

#### [selectMenu](#selectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:selectMenu(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects a Final Cut Pro Menu Item based on the list of menu titles in English.                                                                                         |
| **Parameters**                                       | <ul><li>path - The list of menu items you'd like to activate.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the press was successful.</li></ul>          |
| **Notes**                                            | <ul><li>Example usage:</li><li>   `require("cp.apple.finalcutpro"):menuBar():selectMenu({"View", "Browser", "Toggle Filmstrip/List View"})`</li></ul>                |

### Methods

#### [addMenuFinder](#addmenufinder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:addMenuFinder(finder) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers an `AXMenuItem` finder function. The finder's job is to take an individual 'find' step and return either the matching child, or nil if it can't be found. It is used by the [addMenuFinder](#addMenuFinder) function. The `finder` should have the following signature:                                                                                         |
| **Parameters**                                       | <ul><li>`finder`     - The finder function</li></ul> |
| **Returns**                                          | <ul><li>The `AXMenuItem` found, or `nil`.</li></ul>          |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul>          |

#### [checkMenu](#checkmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:checkMenu(path, wait) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks a menu item.                                                                                         |
| **Parameters**                                       | <ul><li>path - At table containing the path to the menu bar item.</li><li>wait - How long to wait before checking.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful, otherwise `false`.</li></ul>          |

#### [findMenuItemsUI](#findmenuitemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:findMenuItemsUI(path) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the set of menu items in the provided path. If the path contains a menu, the                                                                                         |
| **Parameters**                                       | <ul><li>path - A table containing the path to the menu.</li></ul> |
| **Returns**                                          | <ul><li>An `axuielementObject` for the menu items.</li></ul>          |

#### [findMenuUI](#findmenuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:findMenuUI(path) -> Menu UI` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a specific Menu UI element for the provided path.                                                                                         |
| **Parameters**                                       | <ul><li>`path`       - The path list to search for.</li><li>`language`   - The language code the path is in. E.g. "en" or "fr". Defaults to the</li></ul> |
| **Returns**                                          | <ul><li>The Menu UI, or `nil` if it could not be found.</li></ul>          |

#### [getMainMenu](#getmainmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:getMainMenu() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table of all the possible Menu Bar values for each language.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of Menu Bar Values</li></ul>          |

#### [isChecked](#ischecked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:isChecked(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menubar item checked?                                                                                         |
| **Parameters**                                       | <ul><li>path - At table containing the path to the menu bar item.</li></ul> |
| **Returns**                                          | <ul><li>`true` if checked otherwise `false`.</li></ul>          |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:isEnabled(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menubar item enabled?                                                                                         |
| **Parameters**                                       | <ul><li>path - At table containing the path to the menu bar item.</li></ul> |
| **Returns**                                          | <ul><li>`true` if enabled otherwise `false`.</li></ul>          |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Tells you if the Final Cut Pro Menu Bar is visible.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if showing, otherwise `false`</li></ul>          |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro Menu Bar Accessibility Object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `axuielementObject` on `nil`</li></ul>          |

#### [uncheckMenu](#uncheckmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:uncheckMenu(path, wait) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Uncheck's a menu item.                                                                                         |
| **Parameters**                                       | <ul><li>path - At table containing the path to the menu bar item.</li><li>wait - How long to wait before unchecking.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful, otherwise `false`.</li></ul>          |

#### [visitMenuItems](#visitmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:visitMenuItems(visitFn[, startPath]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Walks the menu tree, calling the `visitFn` on all the 'item' values - that is,                                                                                         |
| **Parameters**                                       | <ul><li>`visitFn`    - The function called for each menu item.</li><li>`startPath`  - The path to the menu item to start at.</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul>          |

