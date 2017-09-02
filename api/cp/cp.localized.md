# [docs](index.md) » cp.localized
---

Helps look up localized names for folders.

## API Overview
* Functions - API calls offered directly by the extension
 * [getLocalizedName](#getlocalizedname)

## API Documentation

### Functions

#### [getLocalizedName](#getlocalizedname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.localized.getLocalizedName(path[, language]) -> string, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the localized name for the `path` in the specified `language`. If all else fails, the                                                                                         |
| **Parameters**                                       | <ul><li>`path`			- The full path to the folder</li><li>`language`		- The language to retrieve the name for.</li></ul> |
| **Returns**                                          | <ul><li>The localized name, or `name` if not available.</li><li>The original name, minus `.localized`</li></ul>          |

