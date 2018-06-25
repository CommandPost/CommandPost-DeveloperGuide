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
| **Parameters**                                       | <ul><br /><li><code>id</code>      - The unique ID</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>handler</code> instance.</li><br /></ul>                                           |

#### [getActivator](#getactivator)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.getActivator(id) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an activator with the specified ID. If it doesn't exist, it will be created.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>activatorId</code>     - The unique ID of the activator.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The activator with the specified ID.</li><br /></ul>                                           |

#### [getHandler](#gethandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.getHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an existing handler with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>          - The unique ID of the action handler.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The action handler, or <code>nil</code></li><br /></ul>                                           |

#### [getURL](#geturl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.getURL(handlerId, action) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a URL based on the Handler ID & Action Table.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>handlerId</code> - The Handler ID * <code>action</code> The action table</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string</li><br /></ul>                                           |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.manager.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

