# [docs](index.md) » plugins.finalcutpro.timeline.titles
---

Controls Final Cut Pro's Titles.

## API Overview
* Functions - API calls offered directly by the extension
 * [apply](#apply)

## API Documentation

### Functions

#### [apply](#apply)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.titles.apply(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Applies the specified action as a title. Expects action to be a table with the following structure:                                                                                         |
| **Parameters**                                       |  * `action`      - A table with the name/category/theme for the title to apply, or a string with just the name.                                       |
| **Returns**                                          |  * `true` if a matching title was found and applied to the timeline.                                                |

