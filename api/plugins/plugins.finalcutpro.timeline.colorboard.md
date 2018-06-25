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
| **Type**                                             | Function |
| **Description**                                      | Color Board Mouse Puck Release |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [nextAspect](#nextaspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.colorboard.nextAspect() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Goes to the next Color Board aspect. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [startMousePuck](#startmousepuck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.colorboard.startMousePuck(aspect, property) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Color Board - Puck Control Via Mouse |
| **Parameters**                                       | <ul><li>aspect - "global", "shadows", "midtones" or "highlights" * property - "Color", "Saturation" or "Exposure"</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [startShiftingPuck](#startshiftingpuck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.colorboard.startShiftingPuck(puck, percentShift, angleShift) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Starts shifting the puck, repeating at the keyboard repeat rate. Runs until `stopShiftingPuck()` is called. |
| **Parameters**                                       | <ul><li>puck         - The puck to shift * property      - The property to shift (typically the <code>percent</code> or <code>angle</code> value for the puck) * amount        - The amount to shift the property.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [stopShiftingPuck](#stopshiftingpuck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.colorboard.stopShiftingPuck() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stops the puck from shifting with the keyboard. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

