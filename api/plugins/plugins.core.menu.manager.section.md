# [docs](index.md) » plugins.core.menu.manager.section
---

Controls sections for the CommandPost menu.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [_addGenerator](#_addgenerator)
 * [addItem](#additem)
 * [addItems](#additems)
 * [addMenu](#addmenu)
 * [addSection](#addsection)
 * [generateTable](#generatetable)
 * [new](#new)

## API Documentation

### Methods

#### [_addGenerator](#_addgenerator)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.core.menu.manager.section:_addGenerator() -> section` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | A private method for registering a generator. This should not be called directly.                                                                                         |
| **Parameters**                                       | <ul><li>`generator`	- The generator being added.</li></ul> |
| **Returns**                                          | <ul><li>section - The section.</li></ul>          |

#### [addItem](#additem)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.core.menu.manager.section:addItem(priority, itemFn) -> section` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers a function which will generate a single table item.                                                                                         |
| **Parameters**                                       | <ul><li>`priority`	- The priority of the item within the section. Lower numbers appear first.</li><li>`itemFn`		- A function which will return a table representing a single menu item. See `hs.menubar` for details.</li></ul> |
| **Returns**                                          | <ul><li>section - The section the item was added to.</li></ul>          |

#### [addItems](#additems)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.core.menu.manager.section:addItems(priority, itemsFn) -> section` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers a function which will generate multiple table items.                                                                                         |
| **Parameters**                                       | <ul><li>`priority`	- The priority of the items within the section. Lower numbers appear first.</li><li>`itemsFn`	- A function which will return a table containing multiple table items. See `hs.menubar` for details.</li></ul> |
| **Returns**                                          | <ul><li>section - The section the item was added to.</li></ul>          |

#### [addMenu](#addmenu)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.core.menu.manager.section:addMenu(priority, titleFn) -> section` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a new sub-menu with the specified priority. The section that will contain                                                                                         |
| **Parameters**                                       | <ul><li>`priority`	- The priority of the item within the section. Lower numbers appear first.</li><li>`titleFn`	- The function which will return the menu title.</li></ul> |
| **Returns**                                          | <ul><li>section - The new section that was created.</li></ul>          |

#### [addSection](#addsection)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.core.menu.manager.section:addSection(priority, itemFn) -> section` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a new sub-section with the specified priority. The new sub-section is returned.                                                                                         |
| **Parameters**                                       | <ul><li>`priority`	- The priority of the item within the section. Lower numbers appear first.</li></ul> |
| **Returns**                                          | <ul><li>section - The new section that was created.</li></ul>          |

#### [generateTable](#generatetable)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.core.menu.manager.section:generateTable() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Generates a new menu table based on the registered items and sections inside this section.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`table`	- The menu table for this section. See `hs.menubar` for details on the format.</li></ul>          |

#### [new](#new)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.core.menu.manager.section:new() -> section` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new menu section, which can have items and sub-menus added to it.                                                                                         |
| **Returns**                                          | <ul><li>section - The section that was created.</li></ul>          |

