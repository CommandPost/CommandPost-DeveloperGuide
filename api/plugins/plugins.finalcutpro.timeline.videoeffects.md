# [docs](index.md) » plugins.finalcutpro.timeline.videoeffects
---

Controls Final Cut Pro's Video Effects.

## API Overview
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [videoeffects](#videoeffects)

## API Documentation

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.videoeffects.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise the Module                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Module</li></ul>          |

#### [videoeffects](#videoeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.videoeffects(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Applies the specified action as a video effect. Expects action to be a table with the following structure:                                                                                         |
| **Parameters**                                       | <ul><li>* `action`		- A table with the name/category/theme for the video effect to apply, or a string with just the name.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if a matching video effect was found and applied to the timeline.</li></ul>          |

