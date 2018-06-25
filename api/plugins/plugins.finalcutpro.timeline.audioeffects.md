# [docs](index.md) » plugins.finalcutpro.timeline.audioeffects
---

Controls Final Cut Pro's Audio Effects.

## API Overview
* Functions - API calls offered directly by the extension
 * [audioeffects](#audioeffects)
 * [init](#init)

## API Documentation

### Functions

#### [audioeffects](#audioeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.audioeffects(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Applies the specified action as a audio effect. Expects action to be a table with the following structure: |
| **Parameters**                                       | <ul><li><code>action</code>     - A table with the name/category/theme for the audio effect to apply, or a string with just the name.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if a matching audio effect was found and applied to the timeline.</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.audioeffects.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialise the Module |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Module</li></ul> |

