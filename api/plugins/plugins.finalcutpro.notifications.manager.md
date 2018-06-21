# [docs](index.md) » plugins.finalcutpro.notifications.manager
---

Notifications Manager Plugin.

## API Overview
* Constants - Useful values which cannot be changed
 * [manager](#manager)
* Variables - Configurable values
 * [watchers](#watchers)
* Functions - API calls offered directly by the extension
 * [unwatch](#unwatch)
 * [watch](#watch)

## API Documentation

### Constants

#### [manager](#manager)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.manager` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Event Types                                                                                         |

### Variables

#### [watchers](#watchers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.manager.watchers -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Watchers                                                                                         |

### Functions

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.manager.unwatch(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Start Watchers                                                                                         |
| **Parameters**                                       |  * id - The ID of the watcher to unwatch as string                                       |
| **Returns**                                          |  * None                                                |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.manager.watch(event) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Start Watchers                                                                                         |
| **Parameters**                                       |  * events - Events to watch                                       |
| **Returns**                                          |  * The ID of the watcher as string                                                |

