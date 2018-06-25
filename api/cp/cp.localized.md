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
| **Parameters**                                       | <ul><br /><li><code>path</code>           - The full path to the folder * <code>locale</code>            - The locale to retrieve the name for.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The localized name, or <code>name</code> if not available. * The original name, minus <code>.localized</code></li><br /></ul>                                           |

