# [docs](index.md) » plugins.finalcutpro.timeline.colorboard
---

Color Board Plugins.

## API Overview
* Functions - API calls offered directly by the extension
 * [colorBoardMousePuckRelease](#colorboardmousepuckrelease)
 * [nextAspect](#nextaspect)
 * [startMousePuck](#startmousepuck)
 * [startShiftingPuck](#startshiftingpuck)
 * [stopShiftingPuck](#stopshiftingpuck)

## API Documentation

### Functions

#### [colorBoardMousePuckRelease](#colorboardmousepuckrelease)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.colorboard.colorBoardMousePuckRelease() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Color Board Mouse Puck Release                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [nextAspect](#nextaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.colorboard.nextAspect() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Goes to the next Color Board aspect.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [startMousePuck](#startmousepuck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.colorboard.startMousePuck(aspect, property) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Color Board - Puck Control Via Mouse                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">aspect - "global", "shadows", "midtones" or "highlights"</li><li markdown="1">property - "Color", "Saturation" or "Exposure"</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [startShiftingPuck](#startshiftingpuck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.colorboard.startShiftingPuck(puck, percentShift, angleShift) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Starts shifting the puck, repeating at the keyboard repeat rate. Runs until `stopShiftingPuck()` is called.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">puck			- The puck to shift</li><li markdown="1">property		- The property to shift (typically the `percent` or `angle` value for the puck)</li><li markdown="1">amount		- The amount to shift the property.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [stopShiftingPuck](#stopshiftingpuck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.colorboard.stopShiftingPuck() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the puck from shifting with the keyboard.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

