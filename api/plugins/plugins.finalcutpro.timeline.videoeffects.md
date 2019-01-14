# [docs](index.md) » plugins.finalcutpro.timeline.videoeffects
---

Controls Final Cut Pro's Video Effects.

## API Overview
* Functions - API calls offered directly by the extension
 * [videoeffects](#videoeffects)

## API Documentation

### Functions

#### [videoeffects](#videoeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.videoeffects(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Applies the specified action as a video effect. Expects action to be a table with the following structure: |
| **Parameters**                                       | <ul><li><code>action</code>     - A table with the name/category/theme for the video effect to apply, or a string with just the name.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if a matching video effect was found and applied to the timeline.</li></ul> |

