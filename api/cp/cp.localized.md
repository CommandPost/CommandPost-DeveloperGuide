# [docs](index.md) » cp.localized
---

Helps look up localized names for folders.

## API Overview
* Functions - API calls offered directly by the extension
 * [getLocalizedName](#getlocalizedname)

## API Documentation

### Functions

#### [getLocalizedName](#getlocalizedname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.localized.getLocalizedName(path[, locale]) -> string, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the localized name for the `path` in the specified `locale`. If all else fails, the                                                                                         |
| **Parameters**                                       |  * `path`			- The full path to the folder * `locale`		    - The locale to retrieve the name for.                                       |
| **Returns**                                          |  * The localized name, or `name` if not available. * The original name, minus `.localized`                                                |

