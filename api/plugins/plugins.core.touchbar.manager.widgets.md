# [docs](index.md) » plugins.core.touchbar.manager.widgets
---

Touch Bar Widgets Manager

## API Overview
* Functions - API calls offered directly by the extension
 * [allGroups](#allgroups)
* Methods - API calls which can only be made on an object returned by a constructor
 * [get](#get)
 * [getAll](#getall)
 * [id](#id)
 * [new](#new)
 * [params](#params)

## API Documentation

### Functions

#### [allGroups](#allgroups)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.widgets.allGroups() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table containing all of the widget groups.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * Table                                                |

### Methods

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.widgets:get(id) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a Touch Bar widget                                                                                         |
| **Parameters**                                       | * `id`      - The unique ID for the widget you want to return.                                       |
| **Returns**                                          |  * table containing the widget                                                |

#### [getAll](#getall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.widgets:getAll() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns all of the created widgets                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * table containing all of the created callbacks                                                |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.widgets:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ID of the widget                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * The ID of the widget as a `string`                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.widgets:new(id, params) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new Touch Bar Widget.                                                                                         |
| **Parameters**                                       | * `id`      - The unique ID for this widget.                                       |
| **Returns**                                          |  * table that has been created                                                |

#### [params](#params)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.widgets:params() -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the paramaters of the widget                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * The paramaters of the widget                                                |

