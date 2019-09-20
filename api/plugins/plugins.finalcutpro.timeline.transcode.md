# [docs](index.md) » plugins.finalcutpro.timeline.transcode
---

Adds actions that allows you to transcode clips from the timeline.

## API Overview
* Constants - Useful values which cannot be changed
 * [transcodeType](#transcodetype)
* Functions - API calls offered directly by the extension
 * [doTranscodeSelectedBrowserClips](#dotranscodeselectedbrowserclips)
 * [doTranscodeSelectedClips](#dotranscodeselectedclips)
 * [doTranscodeSelectedTimelineClips](#dotranscodeselectedtimelineclips)
 * [optimizeSelectedClips](#optimizeselectedclips)
 * [proxySelectedClips](#proxyselectedclips)
 * [transcodeSelectedClips](#transcodeselectedclips)

## API Documentation

### Constants

#### [transcodeType](#transcodetype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.transcode.transcodeType -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Transcode type. |

### Functions

#### [doTranscodeSelectedBrowserClips](#dotranscodeselectedbrowserclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.transcode.doTranscodeSelectedBrowserClips() -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a [Statement](cp.rx.go.Statement.md) to transcode selected browser clips. |
| **Parameters**                                       | <ul><li>transcodeType - Either "optimized" or "proxy"</li></ul> |
| **Returns**                                          | <ul><li><a href="cp.rx.go.Statement.md">Statement</a> to execute</li></ul> |

#### [doTranscodeSelectedClips](#dotranscodeselectedclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.transcode.doTranscodeSelectedClips() -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a [Statement](cp.rx.go.Statement.md) to transcode selected clips. |
| **Parameters**                                       | <ul><li>transcodeType - Either "optimized" or "proxy"</li></ul> |
| **Returns**                                          | <ul><li><a href="cp.rx.go.Statement.md">Statement</a> to execute</li></ul> |

#### [doTranscodeSelectedTimelineClips](#dotranscodeselectedtimelineclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.transcode.doTranscodeSelectedTimelineClips() -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a [Statement](cp.rx.go.Statement.md) to transcode selected timeline clips. |
| **Parameters**                                       | <ul><li>transcodeType - Either "optimized" or "proxy"</li></ul> |
| **Returns**                                          | <ul><li><a href="cp.rx.go.Statement.md">Statement</a> to execute</li></ul> |

#### [optimizeSelectedClips](#optimizeselectedclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.transcode.optimizeSelectedClips() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Create optimised media for selected clips. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [proxySelectedClips](#proxyselectedclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.transcode.proxySelectedClips() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Create Proxies for selected clips. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [transcodeSelectedClips](#transcodeselectedclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.transcode.transcodeSelectedClips(transcodeType) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Transcode selected clips. |
| **Parameters**                                       | <ul><li>transcodeType - Either "optimized" or "proxy"</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

