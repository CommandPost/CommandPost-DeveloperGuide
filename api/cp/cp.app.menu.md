# [docs](index.md) » cp.app.menu
---

Represents an app's menu bar, providing multi-lingual access to find and
trigger menu items.

## API Overview
* Constants - Useful values which cannot be changed
 * [NIB_FILE](#nib_file)
 * [ROLE](#role)
* Functions - API calls offered directly by the extension
 * [selectMenu](#selectmenu)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [showing](#showing)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addMenuFinder](#addmenufinder)
 * [app](#app)
 * [findMenuItemsUI](#findmenuitemsui)
 * [findMenuUI](#findmenuui)
 * [getMainMenu](#getmainmenu)
 * [isChecked](#ischecked)
 * [isEnabled](#isenabled)
 * [visitMenuItems](#visitmenuitems)

## API Documentation

### Constants

#### [NIB_FILE](#nib_file)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.NIB_FILE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Main NIB File.                                                                                         |

#### [ROLE](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.ROLE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The menu role                                                                                         |

### Functions

#### [selectMenu](#selectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:selectMenu(path[, locale][, pressAll]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects a Final Cut Pro Menu Item based on the list of menu titles in English.                                                                                         |
| **Parameters**                                       | <ul><li>path - The list of menu items you'd like to activate.</li><li>locale - The locale the path is in. Defaults to "en".</li><li>pressAll - If `true`, all menus will be pressed en route to the target. Defaults to `false`.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the press was successful.</li></ul>          |
| **Notes**                                            | <ul><li>Example usage:</li><li>   `require("cp.app"):forBundleID("com.apple.FinalCut"):menu():selectMenu({"View", "Browser", "Toggle Filmstrip/List View"})`</li></ul>                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.new(app) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new menu for the specified App.                                                                                         |
| **Parameters**                                       | <ul><li>app - The `cp.app` instance the menu belongs to.</li></ul> |
| **Returns**                                          | <ul><li>a new menu instance</li></ul>          |

### Fields

#### [showing](#showing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.showing <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Tells you if the app's Menu Bar is visible.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.UI <cp.prop:hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the menu.                                                                                         |

### Methods

#### [addMenuFinder](#addmenufinder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:addMenuFinder(finder) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers an `AXMenuItem` finder function. The finder's job is to take an individual 'find' step and return either the matching child, or nil if it can't be found. It is used by the [addMenuFinder](#addMenuFinder) function. The `finder` should have the following signature:                                                                                         |
| **Parameters**                                       | <ul><li>`finder`     - The finder function</li></ul> |
| **Returns**                                          | <ul><li>The `AXMenuItem` found, or `nil`.</li></ul>          |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:app() -> cp.app` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.app` instance this belongs to.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `cp.app`.</li></ul>          |

#### [findMenuItemsUI](#findmenuitemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuItemsUI(path[, locale]) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the set of menu items in the provided path. If the path contains a menu, the                                                                                         |
| **Parameters**                                       | <ul><li>path - A table containing the path to the menu.</li><li>locale - The locale the path is in. Defaults to "en".</li></ul> |
| **Returns**                                          | <ul><li>An `axuielementObject` for the menu items.</li></ul>          |

#### [findMenuUI](#findmenuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuUI(path[, locale]) -> Menu UI, table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a specific Menu UI element for the provided path.                                                                                         |
| **Parameters**                                       | <ul><li>path         - The path list to search for.</li><li>locale       - The locale code the path is in. E.g. "en" or "fr". Defaults to "en".</li></ul> |
| **Returns**                                          | <ul><li>The Menu UI, or `nil` if it could not be found.</li><li>The full list of Menu UIs for the path in a table.</li></ul>          |

#### [getMainMenu](#getmainmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:getMainMenu([locales]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with the available menus, items and sub-menu, in the specified locales (if available).                                                                                         |
| **Parameters**                                       | <ul><li>locales       - An optional single `localeID` or a list of `localeID`s to ensure are loaded.</li></ul> |
| **Returns**                                          | <ul><li>A table of Menu Bar Values</li></ul>          |

#### [isChecked](#ischecked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isChecked(path[, locale]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menu item checked?                                                                                         |
| **Parameters**                                       | <ul><li>path - At table containing the path to the menu bar item.</li><li>locale - The locale the path is in. Defaults to "en".</li></ul> |
| **Returns**                                          | <ul><li>`true` if checked otherwise `false`.</li></ul>          |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isEnabled(path[, locale]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menu item enabled?                                                                                         |
| **Parameters**                                       | <ul><li>path - At table containing the path to the menu bar item.</li><li>locale - The locale the path is in. Defaults to "en".</li></ul> |
| **Returns**                                          | <ul><li>`true` if enabled otherwise `false`.</li></ul>          |

#### [visitMenuItems](#visitmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:visitMenuItems(visitFn[, startPath[, locale]]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Walks the menu tree, calling the `visitFn` on all the 'item' values - that is,                                                                                         |
| **Parameters**                                       | <ul><li>visitFn - The function called for each menu item.</li><li>startPath - The path to the menu item to start at.</li><li>locale - The locale the path is in. Defaults to "en".</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul>          |

