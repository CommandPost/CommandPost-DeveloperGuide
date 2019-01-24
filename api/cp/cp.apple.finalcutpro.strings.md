# [docs](index.md) » cp.apple.finalcutpro.strings
---

The `cp.strings` for I18N lookups related to Final Cut Pro.
This has been populated with common lookups for user interface values
that appear in Final Cut Pro.

## API Overview
* Constants - Useful values which cannot be changed
 * [strings](#strings)
* Methods - API calls which can only be made on an object returned by a constructor
 * [find](#find)
 * [findKeys](#findkeys)

## API Documentation

### Constants

#### [strings](#strings)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.strings <cp.strings>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The `cp.strings` providing access to common FCPX text values. |

### Methods

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.strings:find(key[, locale][, quiet]]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Looks up an application string with the specified `key`. |
| **Parameters**                                       | <ul><li><code>key</code>    - The key to look up.</li><li><code>locale</code> - Optional locale to retrieve the key for, if available. May be a <code>string</code> or <code>cp.i18n.localeID</code>.</li><li><code>quiet</code>  - Optional boolean, defaults to <code>false</code>. If <code>true</code>, no warnings are logged for missing keys.</li></ul> |
| **Returns**                                          | <ul><li>The requested string or <code>nil</code> if the application is not running.</li></ul> |

#### [findKeys](#findkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.strings:findKeys(string[, lang]) -> {string}` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Looks up an application string and returns an array of keys that match. It will take into account current language the app is running in, or use `lang` if provided. |
| **Parameters**                                       | <ul><li><code>string</code> - The string to look up.</li><li><code>lang</code>   - The language (defaults to current FCPX language).</li></ul> |
| **Returns**                                          | <ul><li>The array of keys with a matching string.</li></ul> |
| **Notes**                                            | <ul><li>This method may be very inefficient, since it has to search through every possible key/value pair to find matches. It is not recommended that this is used in production.</li></ul> |

