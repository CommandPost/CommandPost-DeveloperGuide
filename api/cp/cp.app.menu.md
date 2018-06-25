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
| **Parameters**                                       | <ul><br /><li>app - The <code>cp.app</code> instance the menu belongs to.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a new menu instance</li><br /></ul>                                           |

### Methods

#### [addMenuFinder](#addmenufinder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:addMenuFinder(finder) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers an `AXMenuItem` finder function. The finder's job is to take an individual 'find' step and return either the matching child, or nil if it can't be found. It is used by the [addMenuFinder](#addMenuFinder) function. The `finder` should have the following signature:                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>finder</code>     - The finder function</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>AXMenuItem</code> found, or <code>nil</code>.</li><br /></ul>                                           |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:app() -> cp.app` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.app` instance this belongs to.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>cp.app</code>.</li><br /></ul>                                           |

#### [findMenuItems](#findmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuItems(path[, options]) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an `Observable` that will emit each of the menu items along the path.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path         - the table of path items. * options      - (optional) table of additional configuration options.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>Observable</code> instance.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This will not act until something <code>subscribes</code> to the returned <code>Observable</code>.</li><br /></ul>                                             |

#### [findMenuItemsUI](#findmenuitemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuItemsUI(path[, locale]) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the set of menu items in the provided path. If the path contains a menu, the                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - A table containing the path to the menu. * locale - The locale the path is in. Defaults to "en".</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>axuielementObject</code> for the menu items.</li><br /></ul>                                           |

#### [findMenuUI](#findmenuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuUI(path[, options]) -> Menu UI, table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a specific Menu UI element for the provided path.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path         - The path list to search for. * options      - (Optional) The table of options.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The Menu UI, or <code>nil</code> if it could not be found. * The full list of Menu UIs for the path in a table.</li><br /></ul>                                           |

#### [findUI](#findui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findUI([timeout]) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an `Observable` that will emit the next available instance of                                                                                         |
| **Parameters**                                       | <ul><br /><li>timeout - (optional) the number of seconds to wait for the UI. It not provided, defaults to forever.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>Observer</code> that emits the UI.</li><br /></ul>                                           |

#### [getMenuTitles](#getmenutitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:getMenuTitles([locales]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with the available menus, items and sub-menu, in the specified locales (if available).                                                                                         |
| **Parameters**                                       | <ul><br /><li>locales       - An optional single <code>localeID</code> or a list of <code>localeID</code>s to ensure are loaded.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table of Menu Bar Values</li><br /></ul>                                           |

#### [isChecked](#ischecked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isChecked(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menu item checked?                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - At table containing the path to the menu bar item. * options - The locale the path is in. Defaults to "en".</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if checked otherwise <code>false</code>.</li><br /></ul>                                           |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isEnabled(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is a menu item enabled?                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - At table containing the path to the menu bar item. * options - The optional table of options.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if enabled otherwise <code>false</code>.</li><br /></ul>                                           |

#### [selectMenu](#selectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:selectMenu(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a Menu Item based on the list of menu titles in English.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - The list of menu items you'd like to activate. * options - (optional) The table of options to apply.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the press was successful.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Example usage:   <code>require("cp.app").forBundleID("com.apple.FinalCut"):menu():selectMenu({"View", "Browser", "Toggle Filmstrip/List View"})</code></li><br /></ul>                                             |

#### [selectMenuItem](#selectmenuitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:selectMenuItem(path, options) -> cp.rx.Observable <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a Menu Item based on the provided menu path.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - The list of menu items you'd like to activate. * options - (optional) The table of options to apply.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>Observable</code> which emits the final menu item, or an error if the selection failed.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The returned <code>Observable</code> will be 'hot', in that it will execute even if no subscription is made to the result. However, it will potentially be run asynchronously, so the actual execution may occur later.</li><br /></ul>                                             |

#### [visitMenuItems](#visitmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:visitMenuItems(visitFn[, options]]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Walks the menu tree, calling the `visitFn` on all the 'item' values - that is,                                                                                         |
| **Parameters**                                       | <ul><br /><li>visitFn - The function called for each menu item. * options - (optional) The table of options.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Nothing</li><br /></ul>                                           |

