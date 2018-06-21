# [docs](index.md) » plugins.finalcutpro.timeline.mousezoom
---

Allows you to zoom in or out of a Final Cut Pro timeline using the mechanical scroll wheel on your mouse or the Touch Pad on the Magic Mouse when holding down the OPTION modifier key.

Special Thanks: Iain Anderson (@funwithstuff) for all his incredible testing!

## API Overview
* Variables - Configurable values
 * [customModifier](#custommodifier)
 * [enabled](#enabled)
 * [numberOfTouchDevices](#numberoftouchdevices)
 * [offset](#offset)
 * [threshold](#threshold)
* Functions - API calls offered directly by the extension
 * [findMagicMouses](#findmagicmouses)
 * [start](#start)
 * [stop](#stop)
 * [update](#update)

## API Documentation

### Variables

#### [customModifier](#custommodifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.mousezoom.customModifier <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Custom Modifier as string.                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.mousezoom.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Toggles the Enable Proxy Menu Icon                                                                                         |

#### [numberOfTouchDevices](#numberoftouchdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.mousezoom.numberOfTouchDevices -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Number of Touch Devices Detected.                                                                                         |

#### [offset](#offset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.mousezoom.offset -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Offset Value used in difference calculations.                                                                                         |

#### [threshold](#threshold)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.mousezoom.threshold -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Threshold Value used in difference calculations.                                                                                         |

### Functions

#### [findMagicMouses](#findmagicmouses)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.mousezoom.findMagicMouses() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Find Magic Mouse Devices and adds them to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.mousezoom.start() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enables the ability to zoon a timeline using your mouse scroll wheel and the OPTION modifier key.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.mousezoom.stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disables the ability to zoom a timeline using your mouse scroll wheel and the OPTION modifier key.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.mousezoom.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see whether or not we should enable the timeline zoom watchers.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

