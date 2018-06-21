# [docs](index.md) » plugins.core.touchbar.manager.virtual.updateLocationCallback
---

Virtual Touch Bar Update Location Callback

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [callbackFn](#callbackfn)
 * [delete](#delete)
 * [get](#get)
 * [getAll](#getall)
 * [id](#id)
 * [new](#new)

## API Documentation

### Methods

#### [callbackFn](#callbackfn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.updateLocationCallback:callbackFn() -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the callbackFn of the current Update Location Callback                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * The callbackFn of the current Shutdown Callback                                                |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.updateLocationCallback:delete() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deletes a Update Location Callback based on an ID.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * None                                                |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.updateLocationCallback:get(id) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets an Update Location Callback based on an ID.                                                                                         |
| **Parameters**                                       | * `id`      - The unique ID for the callback you want to return.                                       |
| **Returns**                                          |  * table containing the callback                                                |

#### [getAll](#getall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.updateLocationCallback:getAll() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns all of the created Update Location Callbacks                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * table containing all of the created callbacks                                                |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.updateLocationCallback:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ID of the current Update Location Callback                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * The ID of the current File Dropped to Dock Icon Callback as a `string`                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.updateLocationCallback:new(id, callbackFn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new Update Location Callback                                                                                         |
| **Parameters**                                       | * `id`      - The unique ID for this callback.                                       |
| **Returns**                                          |  * table that has been created                                                |

