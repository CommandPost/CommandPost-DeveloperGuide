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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">app - The `cp.app` instance the menu belongs to.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a new menu instance</li></ul>          |

### Methods

#### [addMenuFinder](#addmenufinder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:addMenuFinder(finder) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers an `AXMenuItem` finder function. The finder's job is to take an individual 'find' step and return either the matching child, or nil if it can't be found. It is used by the [addMenuFinder](#addMenuFinder) function. The `finder` should have the following signature:                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`finder`     - The finder function</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `AXMenuItem` found, or `nil`.</li></ul>          |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:app() -> cp.app` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.app` instance this belongs to.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `cp.app`.</li></ul>          |

#### [findMenuItems](#findmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuItems(path[, options]) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an `Observable` that will emit each of the menu items along the path.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path         - the table of path items.</li><li markdown="1">options      - (optional) table of additional configuration options.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `Observable` instance.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This will not act until something `subscribes` to the returned `Observable`.</li></ul>                |

#### [findMenuItemsUI](#findmenuitemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuItemsUI(path[, locale]) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the set of menu items in the provided path. If the path contains a menu, the                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - A table containing the path to the menu.</li><li markdown="1">locale - The locale the path is in. Defaults to "en".</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `axuielementObject` for the menu items.</li></ul>          |

#### [findMenuUI](#findmenuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuUI(path[, options]) -> Menu UI, table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a specific Menu UI element for the provided path.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path         - The path list to search for.</li><li markdown="1">options      - (Optional) The table of options.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The Menu UI, or `nil` if it could not be found.</li><li markdown="1">The full list of Menu UIs for the path in a table.</li></ul>          |

#### [findUI](#findui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findUI([timeout]) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an `Observable` that will emit the next available instance of                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">timeout - (optional) the number of seconds to wait for the UI. It not provided, defaults to forever.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `Observer` that emits the UI.</li></ul>          |

#### [getMenuTitles](#getmenutitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:getMenuTitles([locales]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with the available menus, items and sub-menu, in the specified locales (if available).                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">locales       - An optional single `localeID` or a list of `localeID`s to ensure are loaded.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table of Menu Bar Values</li></ul>          |

#### [isChecked](#ischecked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isChecked(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menu item checked?                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - At table containing the path to the menu bar item.</li><li markdown="1">options - The locale the path is in. Defaults to "en".</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if checked otherwise `false`.</li></ul>          |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isEnabled(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menu item enabled?                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - At table containing the path to the menu bar item.</li><li markdown="1">options - The optional table of options.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if enabled otherwise `false`.</li></ul>          |

#### [selectMenu](#selectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:selectMenu(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a Menu Item based on the list of menu titles in English.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - The list of menu items you'd like to activate.</li><li markdown="1">options - (optional) The table of options to apply.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if the press was successful.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Example usage:</li><li markdown="1">   `require("cp.app").forBundleID("com.apple.FinalCut"):menu():selectMenu({"View", "Browser", "Toggle Filmstrip/List View"})`</li></ul>                |

#### [selectMenuItem](#selectmenuitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:selectMenuItem(path, options) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a Menu Item based on the provided menu path.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - The list of menu items you'd like to activate.</li><li markdown="1">options - (optional) The table of options to apply.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `Observable` which emits the final menu item, or an error if the selection failed.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The returned `Observable` will be 'hot', in that it will execute even if no subscription is made to the result. However, it will potentially be run asynchronously, so the actual execution may occur later.</li></ul>                |

#### [visitMenuItems](#visitmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:visitMenuItems(visitFn[, options]]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Walks the menu tree, calling the `visitFn` on all the 'item' values - that is,                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">visitFn - The function called for each menu item.</li><li markdown="1">options - (optional) The table of options.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Nothing</li></ul>          |

