# [docs](index.md) » cp.app.menu
---

Represents an app's menu bar, providing multi-lingual access to find and
trigger menu items.

## API Overview
* Constants - Useful values which cannot be changed
 * [NIB_FILE](#nib_file)
 * [ROLE](#role)
 * [STORYBOARD_NAME](#storyboard_name)
* Constructors - API calls which return an object, typically one that offers API methods
 * [menu](#menu)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [showing](#showing)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addMenuFinder](#addmenufinder)
 * [app](#app)
 * [doFindMenuUI](#dofindmenuui)
 * [doIsEnabled](#doisenabled)
 * [doSelectMenu](#doselectmenu)
 * [findMenuUI](#findmenuui)
 * [getMenuTitles](#getmenutitles)
 * [isChecked](#ischecked)
 * [isEnabled](#isenabled)
 * [selectMenu](#selectmenu)
 * [visitMenuItems](#visitmenuitems)

## API Documentation

### Constants

#### [NIB_FILE](#nib_file)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.NIB_FILE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Main NIB File. |

#### [ROLE](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.ROLE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The menu role |

#### [STORYBOARD_NAME](#storyboard_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.STORYBOARD_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Main Storyboard name. |

### Constructors

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu(app) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Constructs a new menu for the specified App. |
| **Parameters**                                       | <ul><li>app - The <code>cp.app</code> instance the menu belongs to.</li></ul> |
| **Returns**                                          | <ul><li>a new menu instance</li></ul> |

### Fields

#### [showing](#showing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.showing <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Tells you if the app's Menu Bar is visible. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu.UI <cp.prop:hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `axuielement` representing the menu. |

### Methods

#### [addMenuFinder](#addmenufinder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:addMenuFinder(finder) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Registers an `AXMenuItem` finder function. The finder's job is to take an individual 'find' |
| **Parameters**                                       | <ul><li><code>finder</code>     - The finder function</li></ul> |
| **Returns**                                          | <ul><li>The <code>AXMenuItem</code> found, or <code>nil</code>.</li></ul> |
| **Notes**                                            | <ul><li>The <code>finder</code> should have the following signature:</li><li><code>function(parentItem, path, childName, locale) -&gt; childItem</code></li><li>The elements are:</li><li>parentItem    - The <code>AXMenuItem</code> containing the children. E.g. the <code>Go To</code> menu under <code>Window</code>.</li><li>path          - An array of strings in the specified locale leading to the parent item. E.g. <code>{"Window", "Go To"}</code>.</li><li>childName     - The name of the next child to find, in the specified locale. E.g. <code>"Libraries"</code>.</li><li>locale        - The <code>cp.i18n.localeID</code> that the menu titles are in.</li><li>childItem     - The <code>AXMenuItem</code> that was found, or <code>nil</code> if not found.</li></ul> |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:app() -> cp.app` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `cp.app` instance this belongs to. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.app</code>.</li></ul> |

#### [doFindMenuUI](#dofindmenuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:doFindMenuUI(path[, options]) -> cp.rx.go.Statement <hs._asm.axuielement>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that when executed will emit each of the menu items along the path. |
| **Parameters**                                       | <ul><li>path         - the table of path items.</li><li>options      - (optional) table of additional configuration options.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, ready to be executed.</li></ul> |
| **Notes**                                            | <ul><li>Each step on the path can be either one of:</li><li>a string     - The exact name of the menu item.</li><li>a number     - The menu item number, starting from 1.</li><li>a function   - Passed one argument - the Menu UI to check - returning <code>true</code> if it matches.</li><li>The <code>options</code> may contain:</li><li>locale   - The locale that any strings in the path are in. Defaults to "en".</li><li>plain    - Whether or not to disable the pattern matching feature. Defaults to <code>false</code>.</li><li>Examples:</li><li><code>myApp:menu():doFindMenuUI({"Edit", "Copy"}):Now(function(item) print(item:title() .. " enabled: ", item:enabled()) end, error)</code></li></ul> |

#### [doIsEnabled](#doisenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:doIsEnabled(path, options) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that returns `true` if the item at the end of the path is enabled. |
| **Parameters**                                       | <ul><li>path      - The menu path to check.</li><li>options   - The options.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a> to execute.</li></ul> |

#### [doSelectMenu](#doselectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:doSelectMenu(path, options) -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects a Menu Item based on the provided menu path. |
| **Parameters**                                       | <ul><li>path - The list of menu items you'd like to activate.</li><li>options - (optional) The table of options to apply.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, ready to execute.</li></ul> |
| **Notes**                                            | <ul><li>Each step on the path can be either one of:</li><li>a string     - The exact name of the menu item.</li><li>a number     - The menu item number, starting from 1.</li><li>a function   - Passed one argument - the Menu UI to check - returning <code>true</code> if it matches.</li><li>The <code>options</code> may include:</li><li>locale - The <code>localeID</code> or <code>string</code> for the locale that the path values are in.</li><li>pressAll - If <code>true</code>, all menu items will be pressed on the way to the final destination.</li><li>plain    - Whether or not to disable the pattern matching feature. Defaults to <code>false</code>.</li><li>Examples:</li><li><code>previewApp:menu():doSelectMenu({"File", "Take Screenshot", "From Entire Screen"}):Now()</code></li></ul> |

#### [findMenuUI](#findmenuui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:findMenuUI(path[, options]) -> Menu UI, table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds a specific Menu UI element for the provided path. |
| **Parameters**                                       | <ul><li>path         - The path list to search for.</li><li>options      - (Optional) The table of options.</li></ul> |
| **Returns**                                          | <ul><li>The Menu UI, or <code>nil</code> if it could not be found.</li><li>The full list of Menu UIs for the path in a table.</li></ul> |
| **Notes**                                            | <ul><li>Each step on the path can be either one of:</li><li>a string     - The exact name of the menu item.</li><li>a number     - The menu item number, starting from 1.</li><li>a function   - Passed one argument - the Menu UI to check - returning <code>true</code> if it matches.</li><li>The <code>options</code> can contain:</li><li>locale   - The <code>localeID</code> or <code>string</code> with the locale code. Defaults to "en".</li><li>plain    - Whether or not to disable the pattern matching feature. Defaults to <code>false</code>.</li></ul> |

#### [getMenuTitles](#getmenutitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:getMenuTitles([locales]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table with the available menus, items and sub-menu, in the specified locales (if available). |
| **Parameters**                                       | <ul><li>locales       - An optional single <code>localeID</code> or a list of <code>localeID</code>s to ensure are loaded.</li></ul> |
| **Returns**                                          | <ul><li>A table of Menu Bar Values</li></ul> |
| **Notes**                                            | <ul><li>This menu may get added to over time if additional locales are loaded - previously loaded locales are not removed from the cache.</li></ul> |

#### [isChecked](#ischecked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isChecked(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Is a menu item checked? |
| **Parameters**                                       | <ul><li>path - At table containing the path to the menu bar item.</li><li>options - The locale the path is in. Defaults to "en".</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if checked otherwise <code>false</code>.</li></ul> |
| **Notes**                                            | <ul><li>The <code>options</code> may include:</li><li>locale   - The <code>localeID</code> or <code>string</code> with the locale code. Defaults to "en".</li></ul> |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:isEnabled(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Is a menu item enabled? |
| **Parameters**                                       | <ul><li>path - At table containing the path to the menu bar item.</li><li>options - The optional table of options.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if enabled otherwise <code>false</code>.</li></ul> |
| **Notes**                                            | <ul><li>The <code>options</code> may include:</li><li>locale   - The <code>localeID</code> or <code>string</code> with the locale code. Defaults to "en".</li></ul> |

#### [selectMenu](#selectmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:selectMenu(path[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects a Menu Item based on the list of menu titles in English. |
| **Parameters**                                       | <ul><li>path - The list of menu items you'd like to activate.</li><li>options - (optional) The table of options to apply.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the press was successful.</li></ul> |
| **Notes**                                            | <ul><li>Each step on the path can be either one of:</li><li>a string     - The exact name of the menu item.</li><li>a number     - The menu item number, starting from 1.</li><li>a function   - Passed one argument - the Menu UI to check - returning <code>true</code> if it matches.</li><li>The <code>options</code> may include:</li><li>locale - The <code>localeID</code> or <code>string</code> for the locale that the path values are in.</li><li>pressAll - If <code>true</code>, all menu items will be pressed on the way to the final destination.</li><li>plain    - Whether or not to disable the pattern matching feature. Defaults to <code>false</code>.</li><li>Example usage:</li><li><code>require("cp.app").forBundleID("com.apple.FinalCut"):menu():selectMenu({"View", "Browser", "Toggle Filmstrip/List View"})</code></li></ul> |

#### [visitMenuItems](#visitmenuitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.menu:visitMenuItems(visitFn[, options]]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Walks the menu tree, calling the `visitFn` on all the 'item' values - that is, |
| **Parameters**                                       | <ul><li>visitFn - The function called for each menu item.</li><li>options - (optional) The table of options.</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |
| **Notes**                                            | <ul><li>The <code>options</code> may include:</li><li>locale   - The <code>localeID</code> or <code>string</code> with the locale code. Defaults to "en".</li><li>startPath - The path to the menu item to start at.</li><li>The <code>visitFn</code> will be called on each menu item with the following parameters:</li><li><code>function(path, menuItem)</code></li><li>The <code>menuItem</code> is the AXMenuItem object, and the <code>path</code> is an array with the path to that menu item. For example, if it is the "Copy" item in the "Edit" menu, the path will be <code>{ "Edit" }</code>.</li></ul> |

