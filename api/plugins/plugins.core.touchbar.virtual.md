# [docs](index.md) » plugins.core.touchbar.virtual
---

Virtual Touch Bar Manager

## API Overview
* Constants - Useful values which cannot be changed
 * [LOCATION_DEFAULT_VALUE](#location_default_value)
 * [LOCATION_DRAGGABLE](#location_draggable)
 * [LOCATION_MOUSE](#location_mouse)
* Variables - Configurable values
 * [updateLocationCallback](#updatelocationcallback)
* Functions - API calls offered directly by the extension
 * [callback](#callback)
 * [hide](#hide)
 * [init](#init)
 * [show](#show)
 * [start](#start)
 * [stop](#stop)
 * [update](#update)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)
 * [isActive](#isactive)
 * [lastLocation](#lastlocation)
 * [supported](#supported)

## API Documentation

### Constants

#### [LOCATION_DEFAULT_VALUE](#location_default_value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.LOCATION_DEFAULT_VALUE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Default location value. |

#### [LOCATION_DRAGGABLE](#location_draggable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.LOCATION_DRAGGABLE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Location is Draggable. |

#### [LOCATION_MOUSE](#location_mouse)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.LOCATION_MOUSE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Location is Mouse. |

### Variables

#### [updateLocationCallback](#updatelocationcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.updateLocationCallback -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Update Location Callback |

### Functions

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.callback() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Callback Function for the Virtual Touch Bar |
| **Parameters**                                       | <ul><li>obj - the touchbarObject the callback is for</li><li>message - the message to the callback, either "didEnter" or "didExit"</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Hide the Virtual Touch Bar |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.init() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialise the module. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Show the Virtual Touch Bar |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.start() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the Virtual Touch Bar |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stops the Virtual Touch Bar |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the visibility and location of the Virtual Touch Bar |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is `true` if the plugin is enabled. |

#### [isActive](#isactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.isActive <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is `true` if the plugin is enabled and the TouchBar is supported on this OS. |

#### [lastLocation](#lastlocation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.lastLocation <cp.prop: point table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The last known Virtual Touch Bar Location |

#### [supported](#supported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.virtual.supported <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is `true` if the Touch Bar is supported on this version of macOS. |

