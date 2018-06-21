# [docs](index.md) » plugins.finalcutpro.timeline.generators
---

Controls Final Cut Pro's Generators.

## API Overview
* Functions - API calls offered directly by the extension
 * [apply](#apply)

## API Documentation

### Functions

#### [apply](#apply)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.generators.apply(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Applies the specified action as a generator. Expects action to be a table with the following structure:                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`action`     - A table with the name/category/theme for the generator to apply, or a string with just the name.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if a matching generator was found and applied to the timeline.</li></ul>          |

