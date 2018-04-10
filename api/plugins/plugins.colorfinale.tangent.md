# [docs](index.md) » plugins.colorfinale.tangent
---

This plugin basically just disables CP's Tangent Manager when ColorFinale is running.

## API Overview
* Variables - Configurable values
 * [colorFinaleActive](#colorfinaleactive)
 * [colorFinaleInstalled](#colorfinaleinstalled)
 * [colorFinaleWindow](#colorfinalewindow)
* Functions - API calls offered directly by the extension
 * [init](#init)

## API Documentation

### Variables

#### [colorFinaleActive](#colorfinaleactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.colorfinale.tangent.colorFinaleActive <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Checks to see if ColorFinale is active.                                                                                         |

#### [colorFinaleInstalled](#colorfinaleinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.colorfinale.tangent.colorFinaleInstalled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Checks to see if ColorFinale is installed.                                                                                         |

#### [colorFinaleWindow](#colorfinalewindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.colorfinale.tangent.colorFinaleWindow <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Checks to see if an object is a Color Finale window.                                                                                         |

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.colorfinale.tangent.init(tangentManager) -> module` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise the module.                                                                                         |
| **Parameters**                                       | <ul><li>tangentManager - The Tangent Manager</li></ul> |
| **Returns**                                          | <ul><li>The ColorFinale Tangent Module.</li></ul>          |

