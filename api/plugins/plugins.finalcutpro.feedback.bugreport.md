# [docs](index.md) » plugins.finalcutpro.feedback.bugreport
---

Sends Apple a Bug Report or Feature Request for Final Cut Pro.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_HEIGHT](#default_height)
 * [DEFAULT_WIDTH](#default_width)
* Functions - API calls offered directly by the extension
 * [open](#open)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [position](#position)

## API Documentation

### Constants

#### [DEFAULT_HEIGHT](#default_height)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.feedback.bugreport.DEFAULT_HEIGHT -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Default Window Height |

#### [DEFAULT_WIDTH](#default_width)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.feedback.bugreport.DEFAULT_WIDTH -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Default Window Width |

### Functions

#### [open](#open)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.feedback.bugreport.open(bugReport) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Opens Final Cut Pro Feedback Screen |
| **Parameters**                                       | <ul><li>bugReport - Is it a bug report or an enhancement request?</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.feedback.bugreport.position -> <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Webview Position |

