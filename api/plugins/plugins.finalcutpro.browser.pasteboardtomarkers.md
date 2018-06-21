# [docs](index.md) » plugins.finalcutpro.browser.pasteboardtomarkers
---

Take the contents of the Pasteboard and pastes it as clip markers on the
selected clip in the Final Cut Pro Browser. Only one clip can be selected.

Supported format:

```
05:00:00: Test Keyword 1
#05:01:00:01: Test Keyword 2
*05:02:00: Test Keyword 3
05:02:15: Test Keyword 4
*05:03:00: Test Keyword 5
05:03:15: Test Keyword 6
#05:03:30: Test Keyword 7
*05:04:00: Test Keyword 8
```

If a * is place before the timecode, it will make the clip as a favourite
between the current timecode value and the next timecode value.

If a # is place before the timecode, it will create a "To Do" marker.

## API Overview
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [process](#process)

## API Documentation

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.pasteboardtomarkers.init() -> deps` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise the module.                                                                                         |
| **Parameters**                                       |  * deps - Plugin Dependencies                                       |
| **Returns**                                          |  * None                                                |

#### [process](#process)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.pasteboardtomarkers.process() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Processes Pasteboard to Markers                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

