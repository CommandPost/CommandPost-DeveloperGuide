# [docs](index.md) » plugins.finalcutpro.bugfix.clipselection
---

Fixes a bug in Final Cut Pro 10.4.1 that selects unwanted clips when
making a selection of multiple clips using your mouse as a "lasso".

## API Overview
* Variables - Configurable values
 * [active](#active)
 * [enabled](#enabled)
* Functions - API calls offered directly by the extension
 * [activate](#activate)
 * [deactivate](#deactivate)
 * [init](#init)

## API Documentation

### Variables

#### [active](#active)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.bugfix.clipselection.active <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Checks if the plugin is currently active, depending on `enabled` and which                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.bugfix.clipselection.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Allows the fix to be enabled/disabled by setting the `bugfix_clipselection'                                                                                         |

### Functions

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.bugfix.clipselection.activate() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Activates the module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [deactivate](#deactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.bugfix.clipselection.deactivate() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Deactivates the module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.bugfix.clipselection.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

