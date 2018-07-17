# [docs](index.md) » plugins.finalcutpro.timeline.titles
---

Controls Final Cut Pro's Titles.

## API Overview
* Constants - Useful values which cannot be changed
 * [FILE_NAME](#file_name)
 * [FOLDER_NAME](#folder_name)
* Functions - API calls offered directly by the extension
 * [apply](#apply)

## API Documentation

### Constants

#### [FILE_NAME](#file_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.titles.FILE_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | File name of settings file. |

#### [FOLDER_NAME](#folder_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.titles.FOLDER_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Folder Name where settings file is contained. |

### Functions

#### [apply](#apply)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.titles.apply(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Applies the specified action as a title. Expects action to be a table with the following structure: |
| **Parameters**                                       | <ul><li><code>action</code>      - A table with the name/category/theme for the title to apply, or a string with just the name.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if a matching title was found and applied to the timeline.</li></ul> |

