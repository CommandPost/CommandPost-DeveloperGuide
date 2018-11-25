# [docs](index.md) » plugins.core.menu.manager.section
---

Controls sections for the CommandPost menu.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_PRIORITY](#default_priority)
 * [SECTION_DISABLED_PREFERENCES_KEY_PREFIX](#section_disabled_preferences_key_prefix)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addApplicationHeading](#addapplicationheading)
 * [addHeading](#addheading)
 * [addItem](#additem)
 * [addItems](#additems)
 * [addMenu](#addmenu)
 * [addSection](#addsection)
 * [addSeparator](#addseparator)
 * [generateTable](#generatetable)
 * [getDisabledPreferenceKey](#getdisabledpreferencekey)
 * [isApplicationHeading](#isapplicationheading)
 * [isDisabled](#isdisabled)
 * [new](#new)
 * [setDisabledFn](#setdisabledfn)
 * [setDisabledPreferenceKey](#setdisabledpreferencekey)

## API Documentation

### Constants

#### [DEFAULT_PRIORITY](#default_priority)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section.DEFAULT_PRIORITY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The default priority |

#### [SECTION_DISABLED_PREFERENCES_KEY_PREFIX](#section_disabled_preferences_key_prefix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section.SECTION_DISABLED_PREFERENCES_KEY_PREFIX -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The preferences key prefix for a disabled section. |

### Methods

#### [addApplicationHeading](#addapplicationheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:addApplicationHeading(title) -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a heading to the top of the section. |
| **Parameters**                                       | <ul><li>title - The title of the Application Heading.</li></ul> |
| **Returns**                                          | <ul><li>section - The new section that was created.</li></ul> |

#### [addHeading](#addheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:addHeading(title) -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a heading to the top of a section. |
| **Parameters**                                       | <ul><li>title - The title of the heading.</li></ul> |
| **Returns**                                          | <ul><li>section - The new section that was created.</li></ul> |

#### [addItem](#additem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:addItem(priority, itemFn) -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Registers a function which will generate a single table item. |
| **Parameters**                                       | <ul><li><code>priority</code>   - The priority of the item within the section. Lower numbers appear first.</li><li><code>itemFn</code>     - A function which will return a table representing a single menu item. See <code>hs.menubar</code> for details.</li></ul> |
| **Returns**                                          | <ul><li>section - The section the item was added to.</li></ul> |

#### [addItems](#additems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:addItems(priority, itemsFn) -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Registers a function which will generate multiple table items. |
| **Parameters**                                       | <ul><li><code>priority</code>   - The priority of the items within the section. Lower numbers appear first.</li><li><code>itemsFn</code>    - A function which will return a table containing multiple table items. See <code>hs.menubar</code> for details.</li></ul> |
| **Returns**                                          | <ul><li>section - The section the item was added to.</li></ul> |

#### [addMenu](#addmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:addMenu(priority, titleFn) -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a new sub-menu with the specified priority. The section that will contain |
| **Parameters**                                       | <ul><li><code>priority</code>   - The priority of the item within the section. Lower numbers appear first.</li><li><code>titleFn</code>    - The function which will return the menu title.</li></ul> |
| **Returns**                                          | <ul><li>section - The new section that was created.</li></ul> |

#### [addSection](#addsection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:addSection(priority, itemFn) -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a new sub-section with the specified priority. The new sub-section is returned. |
| **Parameters**                                       | <ul><li><code>priority</code>   - The priority of the item within the section. Lower numbers appear first.</li></ul> |
| **Returns**                                          | <ul><li>section - The new section that was created.</li></ul> |

#### [addSeparator](#addseparator)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:addSeparator(priority) -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a new seperator with specified priority. |
| **Parameters**                                       | <ul><li><code>priority</code>   - The priority of the items within the section. Lower numbers appear first.</li></ul> |
| **Returns**                                          | <ul><li>section - The new section that was created.</li></ul> |

#### [generateTable](#generatetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:generateTable() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Generates a new menu table based on the registered items and sections inside this section. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>table</code>  - The menu table for this section. See <code>hs.menubar</code> for details on the format.</li></ul> |

#### [getDisabledPreferenceKey](#getdisabledpreferencekey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:getDisabledPreferenceKey() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the disabled preferences key. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the section has a disabled preferences key defined, otherwise <code>false</code>.</li></ul> |

#### [isApplicationHeading](#isapplicationheading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:isApplicationHeading() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Does this section contain an application heading? |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it does contain an application heading, otherwise <code>false</code>.</li></ul> |

#### [isDisabled](#isdisabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:isDisabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the disabled status |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the section is disabled, otherwise <code>false</code></li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:new() -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new menu section, which can have items and sub-menus added to it. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>section - The section that was created.</li></ul> |

#### [setDisabledFn](#setdisabledfn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:setDisabledFn(disabledFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the Disabled Function |
| **Parameters**                                       | <ul><li>disabledFn - The disabled function.</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [setDisabledPreferenceKey](#setdisabledpreferencekey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.section:setDisabledPreferenceKey(key) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the Disabled Preferences Key. |
| **Parameters**                                       | <ul><li>key - A string which contains the unique preferences key.</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

