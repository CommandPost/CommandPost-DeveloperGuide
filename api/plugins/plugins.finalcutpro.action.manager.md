# [docs](index.md) » plugins.finalcutpro.action.manager
---

Action Manager Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [handlerIds](#handlerids)
 * [handlers](#handlers)
* Functions - API calls offered directly by the extension
 * [addHandler](#addhandler)
 * [getActivator](#getactivator)
 * [getHandler](#gethandler)

## API Documentation

### Constants

#### [handlerIds](#handlerids)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.manager.handlerIds <cp.prop: table of strings; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns a list of registered handler IDs.                                                                                         |

#### [handlers](#handlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.manager.handlers <cp.prop: table of handlers; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Provides access to the set of handlers registered with the manager. It                                                                                         |

### Functions

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.manager.addHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a new action handler with the specified unique ID and returns it for further configuration.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`		- The unique ID</li></ul> |
| **Returns**                                          | <ul><li>* The `handler` instance.</li></ul>          |

#### [getActivator](#getactivator)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.manager.getActivator(id) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an activator with the specified ID. If it doesn't exist, it will be created.                                                                                         |
| **Parameters**                                       | <ul><li>* `activatorId`		- The unique ID of the activator.</li></ul> |
| **Returns**                                          | <ul><li>* The activator with the specified ID.</li></ul>          |

#### [getHandler](#gethandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.manager.getHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an existing handler with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`			- The unique ID of the action handler.</li></ul> |
| **Returns**                                          | <ul><li>* The action handler, or `nil`</li></ul>          |

