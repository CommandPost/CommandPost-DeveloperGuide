# [docs](index.md) » cp.apple.finalcutpro.main.GeneratorsBrowser
---

Generators Browser Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [TITLE](#title)
* Variables - Configurable values
 * [isShowing](#isshowing)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [applyItem](#applyitem)
 * [contents](#contents)
 * [currentItemsUI](#currentitemsui)
 * [getCurrentTitles](#getcurrenttitles)
 * [getGeneratorsRowLabel](#getgeneratorsrowlabel)
 * [getTitlesRowLabel](#gettitlesrowlabel)
 * [group](#group)
 * [hide](#hide)
 * [itemIsSelected](#itemisselected)
 * [loadLayout](#loadlayout)
 * [mainGroupUI](#maingroupui)
 * [parent](#parent)
 * [saveLayout](#savelayout)
 * [search](#search)
 * [selectedItemsUI](#selecteditemsui)
 * [show](#show)
 * [showAllGenerators](#showallgenerators)
 * [showAllTitles](#showalltitles)
 * [showGeneratorsCategory](#showgeneratorscategory)
 * [showInstalledGenerators](#showinstalledgenerators)
 * [showInstalledTitles](#showinstalledtitles)
 * [showSidebar](#showsidebar)
 * [showTitlesCategory](#showtitlescategory)
 * [sidebar](#sidebar)
 * [topCategoriesUI](#topcategoriesui)
 * [UI](#ui)

## API Documentation

### Constants

#### [TITLE](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser.TITLE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Titles & Generators Title. |

### Variables

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser.isShowing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Is the Generators Browser showing? |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser.new(parent) -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `GeneratorsBrowser` instance. |
| **Parameters**                                       | <ul><li>app - The <code>cp.apple.finalcutpro</code> object.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>GeneratorsBrowser</code> object.</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the app instance representing Final Cut Pro. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [applyItem](#applyitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:applyItem(itemUI) -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Applies an item by double clicking on it. |
| **Parameters**                                       | <ul><li>itemUI - The <code>axuielementObject</code> of the item you want to apply.</li></ul> |
| **Returns**                                          | <ul><li>The <code>GeneratorsBrowser</code> object.</li></ul> |

#### [contents](#contents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:contents() -> ScrollArea` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Generators Browser Contents. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>ScrollArea</code> object.</li></ul> |

#### [currentItemsUI](#currentitemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:currentItemsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the current items UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>axuielementObject</code> object.</li></ul> |

#### [getCurrentTitles](#getcurrenttitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:getCurrentTitles() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the list of titles for all generators currently visible. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [getGeneratorsRowLabel](#getgeneratorsrowlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:getGeneratorsRowLabel() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets a Generators Row Label. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Generators Row Label as string.</li></ul> |

#### [getTitlesRowLabel](#gettitlesrowlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:getTitlesRowLabel() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the label of the 'Titles' row in the current language. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The 'Titles' label.</li></ul> |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:group() -> PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>PopUpButton</code> object.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:hide() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the Generators Browser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>GeneratorsBrowser</code> instance.</li></ul> |

#### [itemIsSelected](#itemisselected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:itemIsSelected(itemUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks to see if an item is selected. |
| **Parameters**                                       | <ul><li>itemUI - A <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the item is selected, otherwise <code>false</code>.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a Generators Browser layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the Generators Browser layout settings - created using <code>cp.apple.finalcutpro.main.GeneratorsBrowser:saveLayout()</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [mainGroupUI](#maingroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:mainGroupUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Main Group UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>axuielementObject</code> object.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the parent object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>parent</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current Generators Browser layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current Effects Browser Layout.</li></ul> |

#### [search](#search)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:search() -> PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Search Popup Button object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>PopUpButton</code> object.</li></ul> |

#### [selectedItemsUI](#selecteditemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:selectedItemsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the selected items UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>axuielementObject</code> object.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:show() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Generators Browser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>GeneratorsBrowser</code> instance.</li></ul> |

#### [showAllGenerators](#showallgenerators)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:showAllGenerators() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show All Generators. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>GeneratorsBrowser</code> object.</li></ul> |

#### [showAllTitles](#showalltitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:showAllTitles() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensures the sidebar is showing in the Generators & Titles panel, focused on all 'Titles'. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>GeneratorsBrowser</code> object.</li></ul> |

#### [showGeneratorsCategory](#showgeneratorscategory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:showGeneratorsCategory(name) -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show a specific Generators Category. |
| **Parameters**                                       | <ul><li>name - The name of the Generators Category to show.</li></ul> |
| **Returns**                                          | <ul><li>The <code>GeneratorsBrowser</code> object.</li></ul> |

#### [showInstalledGenerators](#showinstalledgenerators)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:showInstalledGenerators() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensures that the browser is showing 'Installed Generators'. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>GeneratorsBrowser</code> object.</li></ul> |

#### [showInstalledTitles](#showinstalledtitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:showInstalledTitles() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensures that the browser is showing 'Installed Titles'. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>GeneratorsBrowser</code> object.</li></ul> |

#### [showSidebar](#showsidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:showSidebar() -> GeneratorsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensures the sidebar is showing in the Generators & Titles panel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>GeneratorsBrowser</code> object.</li></ul> |

#### [showTitlesCategory](#showtitlescategory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:showTitlesCategory(name) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensures the sidebar is showing and that the selected 'Titles' category is selected, if available. |
| **Parameters**                                       | <ul><li>name - The category name, in the current language.</li></ul> |
| **Returns**                                          | <ul><li>The Generators Browser.</li></ul> |

#### [sidebar](#sidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:sidebar() -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the sidebar object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Table</code> object.</li></ul> |

#### [topCategoriesUI](#topcategoriesui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:topCategoriesUI() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an array of the top-level categories in the sidebar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The array of category rows.</li></ul> |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.GeneratorsBrowser:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Generator Browser UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>axuielementObject</code></li></ul> |

