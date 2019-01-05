# [docs](index.md) » cp.apple.fcpxml.project
---

FCPXML Document Project Object.

This extension was inspired and uses code based on [Pipeline](https://github.com/reuelk/pipeline).
Thank you Reuel Kim for making something truly awesome, and releasing it as Open Source!

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.project.new(name, format, duration, timecodeStart, timecodeFormat, audioLayout, audioRate, renderColorSpace[, clips]) -> fcpxmlProject Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new project FCPXML object and optionally adds clips to it. |
| **Parameters**                                       | <ul><li>name - The name of the project as a string.</li><li>format - The format of the project.</li><li>duration - The duration of the project.</li><li>timecodeStart - The start timecode of the project.</li><li>timecodeFormat - The timecode format of the project.</li><li>audioLayout - The audio layout of the project.</li><li>audioRate - The audio sample rate of the project.</li><li>renderColorSpace - The render color space of the project.</li><li>clips - An optional table of clips you want to add to the project.</li></ul> |
| **Returns**                                          | <ul><li>A new project object.</li></ul> |

