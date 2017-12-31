# [docs](index.md) » plugins.finalcutpro.tangent.manager
---

Tangent Control Surface Manager

This plugin allows Hammerspoon to communicate with Tangent's range of
panels (Element, Virtual Element Apps, Wave, Ripple and any future panels).

Download the Tangent Developer Support Pack & Tangent Hub Installer for Mac
here: http://www.tangentwave.co.uk/developer-support

## API Overview
* Constants - Useful values which cannot be changed
 * [MODES](#modes)
* Variables - Configurable values
 * [active](#active)
 * [customParameters](#customparameters)
* Functions - API calls offered directly by the extension
 * [callback](#callback)
 * [init](#init)
 * [start](#start)
 * [stop](#stop)
 * [updateMode](#updatemode)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)

## API Documentation

### Constants

#### [MODES](#modes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.manager.MODES() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default Modes for CommandPost in the Tangent Mapper.                                                                                         |

### Variables

#### [active](#active)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.manager.active -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Returns `true` if plugin is active, otherwise `false`.                                                                                         |

#### [customParameters](#customparameters)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.manager.customParameters` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table containing custom Tangent parameters.                                                                                         |

### Functions

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.manager.callback(id, metadata) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Tangent Manager Callback Function                                                                                         |
| **Parameters**                                       | <ul><li>id - The ID of the Tangent Message</li><li>metadata - A table of metadata</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.manager.init(deps, env) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Tangent Plugin                                                                                         |
| **Parameters**                                       | <ul><li>deps - Dependencies Table</li><li>env - Environment Table</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.manager.start() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Starts the Tangent Plugin                                                                                         |
| **Parameters**                                       | <ul><li>resetControlMap - When `true`, CommandPost will rebuild the Control Map for Tangent Mapper.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successfully started, otherwise `false`</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.manager.stop() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the Tangent Plugin                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [updateMode](#updatemode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.manager.updateMode() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Mode on the Tangent Hub                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Enable or disables the Tangent Manager.                                                                                         |

