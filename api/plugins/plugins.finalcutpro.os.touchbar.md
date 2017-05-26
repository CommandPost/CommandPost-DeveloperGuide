# [docs](index.md) » plugins.finalcutpro.os.touchbar
---

Virtual Touch Bar Plugin.

## API Overview
* Functions - API calls offered directly by the extension
 * [callback](#callback)
 * [hide](#hide)
 * [show](#show)
 * [start](#start)
 * [stop](#stop)
 * [update](#update)
 * [updateLocation](#updatelocation)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)
 * [isActive](#isactive)
 * [lastLocation](#lastlocation)
 * [location](#location)
 * [supported](#supported)

## API Documentation

### Functions

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.callback() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Callback Function for the Virtual Touch Bar                                                                                         |
| **Parameters**                                       | <ul><li>obj - the touchbarObject the callback is for</li><li>message - the message to the callback, either "didEnter" or "didExit"</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hide the Virtual Touch Bar                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Show the Virtual Touch Bar                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.start() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Virtual Touch Bar                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the Virtual Touch Bar                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the visibility and location of the Virtual Touch Bar                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [updateLocation](#updatelocation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.updateLocation() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Location of the Virtual Touch Bar                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the plugin is enabled.                                                                                         |

#### [isActive](#isactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.isActive <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the plugin is enabled and the TouchBar is supported on this OS.                                                                                         |

#### [lastLocation](#lastlocation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.lastLocation <cp.prop: point table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The last known Virtual Touch Bar Location                                                                                         |

#### [location](#location)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.location <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The Virtual Touch Bar Location Setting                                                                                         |

#### [supported](#supported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.touchbar.supported <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the plugin is supported on this OS.                                                                                         |

