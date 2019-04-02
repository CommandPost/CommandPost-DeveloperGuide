# [docs](index.md) » cp.apple.finalcutpro.viewer.ControlBar
---

Represents the bottom "control" bar on a [Viewer](cp.apple.finalcutpro.viewer.Viewer.md)
which contains the play/pause button, timecode, audio meters, etc.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [ControlBar](#controlbar)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [timecode](#timecode)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.ControlBar.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is a `ControlBar` instance. |
| **Parameters**                                       | <ul><li>element       - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches the pattern for a <code>Viewer</code> <code>ControlBar</code>.</li></ul> |

### Constructors

#### [ControlBar](#controlbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.ControlBar(viewer)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ControlBar` instance. |
| **Parameters**                                       | <ul><li>viewer       - The <a href="cp.apple.finalcutpro.viewer.Viewer.md">Viewer</a> instance.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>ControlBar</code>.</li></ul> |

### Fields

#### [timecode](#timecode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.ControlBar.timecode <cp.prop: string; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current timecode value, with the format "hh:mm:ss:ff". Setting also supports "hh:mm:ss;ff". |

