# [docs](index.md) » plugins.finalcutpro.import.ignorecard
---

Ignore Final Cut Pro's Media Import Window.

## API Overview
* Variables - Configurable values
 * [enabled](#enabled)
* Functions - API calls offered directly by the extension
 * [getDeviceWatcher](#getdevicewatcher)
 * [update](#update)

## API Documentation

### Variables

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.import.ignorecard.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Toggles the Ignore Card Plugin                                                                                         |

### Functions

#### [getDeviceWatcher](#getdevicewatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.import.ignorecard.getDeviceWatcher() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Media Import Window Watcher                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An `hs.fs.volume` object                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.import.ignorecard.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Starts to stops the Ignore Card device watcher.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

