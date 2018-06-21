# [docs](index.md) » plugins.finalcutpro.timeline.height
---

Shortcut for changing Final Cut Pro's Timeline Height

## API Overview
* Variables - Configurable values
 * [changeTimelineClipHeightAlreadyInProgress](#changetimelineclipheightalreadyinprogress)
* Functions - API calls offered directly by the extension
 * [changeTimelineClipHeight](#changetimelineclipheight)
 * [changeTimelineClipHeightRelease](#changetimelineclipheightrelease)
 * [shiftClipHeight](#shiftclipheight)

## API Documentation

### Variables

#### [changeTimelineClipHeightAlreadyInProgress](#changetimelineclipheightalreadyinprogress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.height.changeTimelineClipHeightAlreadyInProgress -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Change timeline clip height already in progress.                                                                                         |

### Functions

#### [changeTimelineClipHeight](#changetimelineclipheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.height.changeTimelineClipHeight(direction) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Change the Timeline Clip Height                                                                                         |
| **Parameters**                                       |  * direction - "up" or "down"                                       |
| **Returns**                                          |  * None                                                |

#### [changeTimelineClipHeightRelease](#changetimelineclipheightrelease)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.height.changeTimelineClipHeightRelease() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Change Timeline Clip Height Release.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [shiftClipHeight](#shiftclipheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.height.shiftClipHeight(direction) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shift Clip Height                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

