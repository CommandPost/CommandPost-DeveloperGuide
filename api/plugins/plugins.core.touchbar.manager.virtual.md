# [docs](index.md) » plugins.core.touchbar.manager.virtual
---

Virtual Touch Bar Manager

## Submodules
 * [plugins.core.touchbar.manager.virtual.updateLocationCallback](plugins.core.touchbar.manager.virtual.updateLocationCallback.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [LOCATION_DEFAULT_VALUE](#location_default_value)
 * [LOCATION_DRAGGABLE](#location_draggable)
 * [LOCATION_MOUSE](#location_mouse)
* Functions - API calls offered directly by the extension
 * [callback](#callback)
 * [hide](#hide)
 * [show](#show)
 * [start](#start)
 * [stop](#stop)
 * [update](#update)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)
 * [isActive](#isactive)
 * [lastLocation](#lastlocation)

## API Documentation

### Constants

#### [LOCATION_DEFAULT_VALUE](#location_default_value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.LOCATION_DEFAULT_VALUE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Default location value.                                                                                         |

#### [LOCATION_DRAGGABLE](#location_draggable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.LOCATION_DRAGGABLE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Location is Draggable.                                                                                         |

#### [LOCATION_MOUSE](#location_mouse)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.LOCATION_MOUSE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Location is Mouse.                                                                                         |

### Functions

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.callback() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Callback Function for the Virtual Touch Bar                                                                                         |
| **Parameters**                                       |  * obj - the touchbarObject the callback is for * message - the message to the callback, either "didEnter" or "didExit"                                       |
| **Returns**                                          |  * None                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hide the Virtual Touch Bar                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Show the Virtual Touch Bar                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.start() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Virtual Touch Bar                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the Virtual Touch Bar                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the visibility and location of the Virtual Touch Bar                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the plugin is enabled.                                                                                         |

#### [isActive](#isactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.isActive <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the plugin is enabled and the TouchBar is supported on this OS.                                                                                         |

#### [lastLocation](#lastlocation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.virtual.lastLocation <cp.prop: point table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The last known Virtual Touch Bar Location                                                                                         |

