# [docs](index.md) » cp.finalcutpro.MenuBar
---

Represents the Final Cut Pro X menu bar, providing functions that allow different tasks to be accomplished.

## API Overview
* Functions - API calls offered directly by the extension
 * [generateMenuMap](#generateMenuMap)
 * [new](#new)
 * [selectMenu](#selectMenu)
* Methods - API calls which can only be made on an object returned by a constructor
 * [visitMenuItems](#visitMenuItems)

## API Documentation

### Functions

#### [generateMenuMap](#generateMenuMap)
| **Signature**                               | `cp.finalcutpro.MenuBar:generateMenuMap() -> boolean`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Generates a map of the menu bar and saves it in the location specified                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>True is successful otherwise Nil</li></ul>          |

#### [new](#new)
| **Signature**                               | `cp.finalcutpro.MenuBar:new(App) -> MenuBar`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Constructs a new MenuBar for the specified App.                                                                     |
| **Parameters**                              | <ul><li>app - The App instance the MenuBar belongs to.</li></ul> |
| **Returns**                                 | <ul><li>a new MenuBar instance</li></ul>          |

#### [selectMenu](#selectMenu)
| **Signature**                               | `cp.finalcutpro.MenuBar:selectMenu(...) -> boolean`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Selects a Final Cut Pro Menu Item based on the list of menu titles in English.                                                                     |
| **Parameters**                              | <ul><li>... - The list of menu items you'd like to activate, for example:</li><li>           select("View", "Browser", "as List")</li></ul> |
| **Returns**                                 | <ul><li>`true` if the press was successful.</li></ul>          |

### Methods

#### [visitMenuItems](#visitMenuItems)
| **Signature**                               | `cp.finalcutpro.MenuBar:visitMenuItems(visitFn[, startPath]) -> nil`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Walks the menu tree, calling the `visitFn` on all the 'item' values - that is,                                                                     |
| **Parameters**                              | <ul><li>`visitFn`	- The function called for each menu item.</li></ul> |
| **Returns**                                 | <ul><li>True is successful otherwise Nil</li></ul>          |

