# [docs](index.md) » cp.config.shutdownCallback
---

Shutdown Callback Module.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [callbackFn](#callbackfn)
 * [get](#get)
 * [getAll](#getall)
 * [id](#id)
 * [new](#new)

## API Documentation

### Methods

#### [callbackFn](#callbackfn)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.shutdownCallback:callbackFn() -> function` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the callbackFn of the current Shutdown Callback                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>The callbackFn of the current Shutdown Callback</li></ul>          |

#### [get](#get)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.shutdownCallback:get(id) -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new Shutdown Callback.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`		- The unique ID for the callback you want to return.</li></ul> |
| **Returns**                                          | <ul><li>table containing the callback</li></ul>          |

#### [getAll](#getall)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.shutdownCallback:getAll() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns all of the created Shutdown Callbacks                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>table containing all of the created callbacks</li></ul>          |

#### [id](#id)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.shutdownCallback:id() -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ID of the current Shutdown Callback                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>The ID of the current Shutdown Callback as a `string`</li></ul>          |

#### [new](#new)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.config.shutdownCallback:new(id, callbackFn) -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new Shutdown Callback.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`		- The unique ID for this callback.</li></ul> |
| **Returns**                                          | <ul><li>table that has been created</li></ul>          |

