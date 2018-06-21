# [docs](index.md) » plugins.finalcutpro.timeline.matchframe
---

Match Frame Tools for Final Cut Pro.

## API Overview
* Functions - API calls offered directly by the extension
 * [getMulticamAngleFromSelectedClip](#getmulticamanglefromselectedclip)
 * [matchFrame](#matchframe)
 * [multicamMatchFrame](#multicammatchframe)

## API Documentation

### Functions

#### [getMulticamAngleFromSelectedClip](#getmulticamanglefromselectedclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.matchframe.getMulticamAngleFromSelectedClip() -> angle | boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get Multicam Angle From Selected Clip                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Angle or `false` on error                                                |

#### [matchFrame](#matchframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.matchframe.matchFrame() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Single Match Frame.                                                                                         |
| **Parameters**                                       |  * `focus`  - If set to `true`, the library will search for the matched clip title                                       |
| **Returns**                                          |  * None                                                |

#### [multicamMatchFrame](#multicammatchframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.matchframe.multicamMatchFrame(goBackToTimeline) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Multicam Match Frame                                                                                         |
| **Parameters**                                       |  * goBackToTimeline - `true` if you want to go back to the timeline after opening the clip in the Multicam Editor                                       |
| **Returns**                                          |  * None                                                |

