# [docs](index.md) » plugins.core.menu.manager
---

Menu Manager Plugin.

## Submodules
 * [plugins.core.menu.manager.section](plugins.core.menu.manager.section.md)

## API Overview
* Variables - Configurable values
 * [rootSection](#rootsection)
 * [titleSuffix](#titlesuffix)
* Functions - API calls offered directly by the extension
 * [addSection](#addsection)
 * [addTitleSuffix](#addtitlesuffix)
 * [disable](#disable)
 * [enable](#enable)
 * [generateMenuTable](#generatemenutable)
 * [init](#init)
 * [updateMenubarIcon](#updatemenubaricon)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [displayMenubarAsIcon](#displaymenubarasicon)

## API Documentation

### Variables

#### [rootSection](#rootsection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.rootSection() -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | A new Root Section                                                                                         |

#### [titleSuffix](#titlesuffix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.titleSuffix() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of Title Suffix's                                                                                         |

### Functions

#### [addSection](#addsection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.addSection(priority) -> section` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new menu section, which can have items and sub-menus added to it.                                                                                         |
| **Parameters**                                       |  * priority - The priority order of menu items created in the section relative to other sections.                                       |
| **Returns**                                          |  * section - The section that was created.                                                |

#### [addTitleSuffix](#addtitlesuffix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.addTitleSuffix(fnTitleSuffix)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Allows you to add a custom Suffix to the Menubar Title                                                                                         |
| **Parameters**                                       |  * fnTitleSuffix - A function that returns a single string                                       |
| **Returns**                                          |  * None                                                |

#### [disable](#disable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.disable(priority) -> menubaritem` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes the menu from the system menu bar.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the menubaritem                                                |

#### [enable](#enable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.enable(priority) -> menubaritem` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the previously removed menu back to the system menu bar.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the menubaritem                                                |

#### [generateMenuTable](#generatemenutable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.generateMenuTable()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates the Menu Table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Menu Table                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [updateMenubarIcon](#updatemenubaricon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.updateMenubarIcon(priority) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Menubar Icon                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

### Fields

#### [displayMenubarAsIcon](#displaymenubarasicon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.menu.manager.displayMenubarAsIcon <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | If `true`, the menubar item will be the app icon. If not, it will be the app name.                                                                                         |

