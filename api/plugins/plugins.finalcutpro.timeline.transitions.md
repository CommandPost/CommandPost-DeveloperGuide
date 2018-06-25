# [docs](index.md) » plugins.finalcutpro.timeline.transitions
---

Controls Final Cut Pro's Transitions.

## API Overview
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [transitions](#transitions)

## API Documentation

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.transitions.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise the Module                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The Module</li><br /></ul>                                           |

#### [transitions](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.transitions(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Applies the specified action as a transition. Expects action to be a table with the following structure:                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>action</code>     - A table with the name/category/theme for the transition to apply, or a string with just the name.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if a matching transition was found and applied to the timeline.</li><br /></ul>                                           |

