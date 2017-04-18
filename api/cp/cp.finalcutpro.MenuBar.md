# [docs](index.md) » cp.finalcutpro.MenuBar
---

Represents the Final Cut Pro X menu bar, providing functions that allow different tasks to be accomplished.

## API Overview
* Functions - API calls offered directly by the extension
 * [generateMenuMap](#generatemenumap)
 * [new](#new)
 * [selectMenu](#selectmenu)
* Methods - API calls which can only be made on an object returned by a constructor
 * [visitMenuItems](#visitmenuitems)

## API Documentation

### Functions

#### [generateMenuMap](#generatemenumap)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.finalcutpro.MenuBar:generateMenuMap() -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a map of the menu bar and saves it in the location specified                                                                                         |
| **Parameters**                                       | <ul><li>N/A</li></ul> |
| **Returns**                                          | <ul><li>True is successful otherwise Nil</li></ul>          |

#### [new](#new)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.finalcutpro.MenuBar:new(App) -> MenuBar` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Constructs a new MenuBar for the specified App.                                                                                         |
| **Parameters**                                       | <ul><li>app - The App instance the MenuBar belongs to.</li></ul> |
| **Returns**                                          | <ul><li>a new MenuBar instance</li></ul>          |

#### [selectMenu](#selectmenu)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.finalcutpro.MenuBar:selectMenu(...) -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects a Final Cut Pro Menu Item based on the list of menu titles in English.                                                                                         |
| **Parameters**                                       | <ul><li>... - The list of menu items you'd like to activate, for example:</li><li>           select("View", "Browser", "as List")</li></ul> |
| **Returns**                                          | <ul><li>`true` if the press was successful.</li></ul>          |

### Methods

#### [visitMenuItems](#visitmenuitems)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.finalcutpro.MenuBar:visitMenuItems(visitFn[, startPath]) -> nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Walks the menu tree, calling the `visitFn` on all the 'item' values - that is,                                                                                         |
| **Parameters**                                       | <ul><li>`visitFn`	- The function called for each menu item.</li></ul> |
| **Returns**                                          | <ul><li>True is successful otherwise Nil</li></ul>          |

