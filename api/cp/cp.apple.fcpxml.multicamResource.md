# [docs](index.md) » cp.apple.fcpxml.multicamResource
---

FCPXML Document Multicam Resource Object.

This extension was inspired and uses code based on [Pipeline](https://github.com/reuelk/pipeline).
Thank you Reuel Kim for making something truly awesome, and releasing it as Open Source!

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.multicamResource.new(name, id, formatRef, startTimecode, timecodeFormat, renderColorSpace, angles) -> fcpxmlMulticamResource Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new FCPXML multicam reference FCPXML Document object. |
| **Parameters**                                       | <ul><li>name - The name of the Multicam Resource as a string.</li><li>id - The ID of the Multicam Resource as a string.</li><li>formatRef - The format of the Multicam Resource.</li><li>startTimecode - The start timecode in flicks.</li><li>timecodeFormat - The timecode format (see: <code>cp.apple.fcpxml.TIMECODE_FORMAT</code>).</li><li>renderColorSpace - The render color space (see: <code>cp.apple.fcpxml.COLOR_SPACE</code>).</li><li>angles - A table of angle objects.</li></ul> |
| **Returns**                                          | <ul><li>A new Multicam Resource object.</li></ul> |

