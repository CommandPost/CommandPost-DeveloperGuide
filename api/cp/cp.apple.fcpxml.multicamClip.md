# [docs](index.md) » cp.apple.fcpxml.multicamClip
---

FCPXML Document Multicam Clip Object.

This extension was inspired and uses code based on [Pipeline](https://github.com/reuelk/pipeline).
Thank you Reuel Kim for making something truly awesome, and releasing it as Open Source!

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.multicamClip.new(name, refID, offset, startTimecode, duration, mcSources) -> fcpxmlMulticamClip Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new multicam event clip FCPXML Document object. |
| **Parameters**                                       | <ul><li>name - The name of the Multicam Clip as a string.</li><li>refID - The reference ID of the Multicam Clip.</li><li>offset - The offset of the Multicam clip in flicks.</li><li>startTimecode - The start timecode in flicks.</li><li>duration - The duration of the Multicam clip.</li><li>mcSources - A table of multicam sources.</li></ul> |
| **Returns**                                          | <ul><li>A new Multicam Clip object.</li></ul> |

