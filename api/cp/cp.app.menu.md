# [docs](index.md) » cp.app.menu
---

Represents an app's menu bar, providing multi-lingual access to find and
trigger menu items.

## API Overview
* Constants - Useful values which cannot be changed
 * [NIB_FILE](#nib_file)
 * [ROLE](#role)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addMenuFinder](#addmenufinder)
 * [app](#app)
 * [findMenuItems](#findmenuitems)
 * [findMenuItemsUI](#findmenuitemsui)
 * [findMenuUI](#findmenuui)
 * [findUI](#findui)
 * [getMenuTitles](#getmenutitles)
 * [isChecked](#ischecked)
 * [isEnabled](#isenabled)
 * [selectMenu](#selectmenu)
 * [selectMenuItem](#selectmenuitem)
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

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.new(app) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new menu for the specified App.                                                                                         |
| **Parameters**                                       |  * app - The `cp.app` instance the menu belongs to.                                       |
| **Returns**                                          |  * a new menu instance                                                |

### Methods

#### [addMenuFinder](#addmenufinder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:addMenuFinder(finder) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers an `AXMenuItem` finder function. The finder's job is to take an individual 'find' step and return either the matching child, or nil if it can't be found. It is used by the [addMenuFinder](#addMenuFinder) function. The `finder` should have the following signature:                                                                                         |
| **Parameters**                                       |  * `finder`     - The finder function                                       |
| **Returns**                                          |  * The `AXMenuItem` found, or `nil`.                                                |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:app() -> cp.app` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.app` instance this belongs to.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.app`.                                                |

#### [findMenuItems](#findmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuItems(path[, options]) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an `Observable` that will emit each of the menu items along the path.                                                                                         |
| **Parameters**                                       |  * path         - the table of path items. * options      - (optional) table of additional configuration options.                                       |
| **Returns**                                          |  * The `Observable` instance.                                                |
| **Notes**                                            |  * This will not act until something `subscribes` to the returned `Observable`.                                                      |

#### [findMenuItemsUI](#findmenuitemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuItemsUI(path[, locale]) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the set of menu items in the provided path. If the path contains a menu, the                                                                                         |
| **Parameters**                                       |  * path - A table containing the path to the menu. * locale - The locale the path is in. Defaults to "en".                                       |
| **Returns**                                          |  * An `axuielementObject` for the menu items.                                                |

#### [findMenuUI](#findmenuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuUI(path[, options]) -> Menu UI, table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a specific Menu UI element for the provided path.                                                                                         |
| **Parameters**                                       |  * path         - The path list to search for. * options      - (Optional) The table of options.                                       |
| **Returns**                                          |  * The Menu UI, or `nil` if it could not be found. * The full list of Menu UIs for the path in a table.                                                |

#### [findUI](#findui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findUI([timeout]) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an `Observable` that will emit the next available instance of                                                                                         |
| **Parameters**                                       |  * timeout - (optional) the number of seconds to wait for the UI. It not provided, defaults to forever.                                       |
| **Returns**                                          |  * An `Observer` that emits the UI.                                                |

#### [getMenuTitles](#getmenutitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:getMenuTitles([locales]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with the available menus, items and sub-menu, in the specified locales (if available).                                                                                         |
| **Parameters**                                       |  * locales       - An optional single `localeID` or a list of `localeID`s to ensure are loaded.                                       |
| **Returns**                                          |  * A table of Menu Bar Values                                                |

#### [isChecked](#ischecked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isChecked(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menu item checked?                                                                                         |
| **Parameters**                                       |  * path - At table containing the path to the menu bar item. * options - The locale the path is in. Defaults to "en".                                       |
| **Returns**                                          |  * `true` if checked otherwise `false`.                                                |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isEnabled(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menu item enabled?                                                                                         |
| **Parameters**                                       |  * path - At table containing the path to the menu bar item. * options - The optional table of options.                                       |
| **Returns**                                          |  * `true` if enabled otherwise `false`.                                                |

#### [selectMenu](#selectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:selectMenu(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a Menu Item based on the list of menu titles in English.                                                                                         |
| **Parameters**                                       |  * path - The list of menu items you'd like to activate. * options - (optional) The table of options to apply.                                       |
| **Returns**                                          |  * `true` if the press was successful.                                                |
| **Notes**                                            |  * Example usage:   `require("cp.app").forBundleID("com.apple.FinalCut"):menu():selectMenu({"View", "Browser", "Toggle Filmstrip/List View"})`                                                      |

#### [selectMenuItem](#selectmenuitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:selectMenuItem(path, options) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a Menu Item based on the provided menu path.                                                                                         |
| **Parameters**                                       |  * path - The list of menu items you'd like to activate. * options - (optional) The table of options to apply.                                       |
| **Returns**                                          |  * An `Observable` which emits the final menu item, or an error if the selection failed.                                                |
| **Notes**                                            |  * The returned `Observable` will be 'hot', in that it will execute even if no subscription is made to the result. However, it will potentially be run asynchronously, so the actual execution may occur later.                                                      |

#### [visitMenuItems](#visitmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:visitMenuItems(visitFn[, options]]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Walks the menu tree, calling the `visitFn` on all the 'item' values - that is,                                                                                         |
| **Parameters**                                       |  * visitFn - The function called for each menu item. * options - (optional) The table of options.                                       |
| **Returns**                                          |  * Nothing                                                |

