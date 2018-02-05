# [docs](index.md) » plugins.finalcutpro.watchers.version
---

This plugin will compare the current version of Final Cut Pro to the last one run.
If it has changed, watchers' `change` function is called.

## API Overview
* Variables - Configurable values
 * [currentVersion](#currentversion)
 * [lastVersion](#lastversion)
* Functions - API calls offered directly by the extension
 * [unwatch](#unwatch)
 * [watch](#watch)

## API Documentation

### Variables

#### [currentVersion](#currentversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchers.version.currentVersion <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The current Final Cut Pro version.                                                                                         |

#### [lastVersion](#lastversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchers.version.lastVersion <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The last Final Cut Pro version.                                                                                         |

### Functions

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchers.version.unwatch(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unwatch a watcher.                                                                                         |
| **Parameters**                                       | <ul><li>id - The ID of the watcher to unwatch</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.watchers.version.watch(events) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Watch Events.                                                                                         |
| **Parameters**                                       | <ul><li>events - Events to watch</li></ul> |
| **Returns**                                          | <ul><li>The Watcher</li></ul>          |

