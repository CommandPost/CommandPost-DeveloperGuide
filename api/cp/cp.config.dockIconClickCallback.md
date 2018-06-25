# [docs](index.md) » cp.config.dockIconClickCallback
---

Callback which triggers when the CommandPost Dock Icon is clicked

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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.dockIconClickCallback:callbackFn() -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the callbackFn of the current Dock Icon Click Callback                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The callbackFn of the current Shutdown Callback</li><br /></ul>                                           |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.dockIconClickCallback:get(id) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new Dock Icon Click Callback.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>      - The unique ID for the callback you want to return.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>table containing the callback</li><br /></ul>                                           |

#### [getAll](#getall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.dockIconClickCallback:getAll() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns all of the created Dock Icon Click Callbacks                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>table containing all of the created callbacks</li><br /></ul>                                           |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.dockIconClickCallback:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ID of the current Dock Icon Click Callback                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The ID of the current File Dropped to Dock Icon Callback as a <code>string</code></li><br /></ul>                                           |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.config.dockIconClickCallback:new(id, callbackFn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new File Dropped to Dock Icon Callback.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>      - The unique ID for this callback.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>table that has been created</li><br /></ul>                                           |

