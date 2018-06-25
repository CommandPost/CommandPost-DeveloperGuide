# [docs](index.md) » plugins.finalcutpro.timeline.zoomtoselection
---

Zoom the Timeline to fit the currently-selected clips.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_SHIFT](#default_shift)
 * [MIN_SHIFT](#min_shift)
 * [SELECTION_BUFFER](#selection_buffer)
* Functions - API calls offered directly by the extension
 * [init](#init)
* Methods - API calls which can only be made on an object returned by a constructor
 * [zoomToSelection](#zoomtoselection)

## API Documentation

### Constants

#### [DEFAULT_SHIFT](#default_shift)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.zoomtoselection.DEFAULT_SHIFT -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Default Shift. |

#### [MIN_SHIFT](#min_shift)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.zoomtoselection.MIN_SHIFT -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Minimum Shift. |

#### [SELECTION_BUFFER](#selection_buffer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.zoomtoselection.SELECTION_BUFFER -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of pixels of buffer space to allow the selection zoom to fit. |

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.zoomtoselection.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialise the module. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Methods

#### [zoomToSelection](#zoomtoselection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.zoomtoselection.zoomToSelection() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Zooms the view to fit the currently-selected clips. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if there is selected content in the timeline and zooming was successful.</li></ul> |

