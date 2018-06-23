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
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>Angle or <code>false</code> on error</li></ul>            |

#### [matchFrame](#matchframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.matchframe.matchFrame() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Single Match Frame.                                                                                         |
| **Parameters**                                       | <ul><li><code>focus</code>  - If set to <code>true</code>, the library will search for the matched clip title</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [multicamMatchFrame](#multicammatchframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.matchframe.multicamMatchFrame(goBackToTimeline) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Multicam Match Frame                                                                                         |
| **Parameters**                                       | <ul><li>goBackToTimeline - <code>true</code> if you want to go back to the timeline after opening the clip in the Multicam Editor</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

