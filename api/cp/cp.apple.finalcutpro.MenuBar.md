# [docs](index.md) » cp.apple.finalcutpro.MenuBar
---

Represents the Final Cut Pro menu bar, providing functions that allow different tasks to be accomplished.

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
 * [selectMenu](#selectmenu)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addMenuFinder](#addmenufinder)
 * [findMenuUI](#findmenuui)
 * [visitMenuItems](#visitmenuitems)

## API Documentation

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
| **Parameters**                                       | <ul><li>path - The list of menu items you'd like to activate, for example:</li><li>           select({"View", "Browser", "as List"})</li></ul> |
| **Returns**                                          | <ul><li>`true` if the press was successful.</li></ul>          |

### Methods

#### [addMenuFinder](#addmenufinder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:addMenuFinder(finder) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers an `AXMenuItem` finder function. The finder's job is to take an individual 'find' step and return either the matching child, or nil if it can't be found. It is used by the [addMenuFinder](#addMenuFinder) function. The `finder` should have the following signature:                                                                                         |
| **Parameters**                                       | <ul><li>`finder`		- The finder function</li></ul> |
| **Returns**                                          | <ul><li>The `AXMenuItem` found, or `nil`.</li></ul>          |

#### [findMenuUI](#findmenuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:findMenuUI(path) -> Menu UI` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a specific Menu UI element for the provided path.                                                                                         |
| **Parameters**                                       | <ul><li>`path`		- The path list to search for.</li><li>`language`	- The language code the path is in. E.g. "en" or "fr". Defaults to the</li></ul> |
| **Returns**                                          | <ul><li>The Menu UI, or `nil` if it could not be found.</li></ul>          |

#### [visitMenuItems](#visitmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.MenuBar:visitMenuItems(visitFn[, startPath]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Walks the menu tree, calling the `visitFn` on all the 'item' values - that is,                                                                                         |
| **Parameters**                                       | <ul><li>`visitFn`	- The function called for each menu item.</li><li>`startPath`	- The path to the menu item to start at.</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul>          |

