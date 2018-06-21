# [docs](index.md) » plugins.core.action.manager
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
 * [getURL](#geturl)
 * [init](#init)

## API Documentation

### Constants

#### [handlerIds](#handlerids)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.handlerIds <cp.prop: table of strings; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns a list of registered handler IDs.                                                                                         |

#### [handlers](#handlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.handlers <cp.prop: table of handlers; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Provides access to the set of handlers registered with the manager. It                                                                                         |

### Functions

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.addHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a new action handler with the specified unique ID and returns it for further configuration.                                                                                         |
| **Parameters**                                       | * `id`		- The unique ID                                       |
| **Returns**                                          | * The `handler` instance.                                                |

#### [getActivator](#getactivator)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.getActivator(id) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an activator with the specified ID. If it doesn't exist, it will be created.                                                                                         |
| **Parameters**                                       | * `activatorId`		- The unique ID of the activator.                                       |
| **Returns**                                          | * The activator with the specified ID.                                                |

#### [getHandler](#gethandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.getHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an existing handler with the specified ID.                                                                                         |
| **Parameters**                                       | * `id`			- The unique ID of the action handler.                                       |
| **Returns**                                          | * The action handler, or `nil`                                                |

#### [getURL](#geturl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.getURL(handlerId, action) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a URL based on the Handler ID & Action Table.                                                                                         |
| **Parameters**                                       |  * `handlerId` - The Handler ID * `action` The action table                                       |
| **Returns**                                          | * A string                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

