# [docs](index.md) » cp.pattern
---

Contains pattern matching utility functions.

## API Overview
* Functions - API calls offered directly by the extension
 * [doesMatch](#doesmatch)

## API Documentation

### Functions

#### [doesMatch](#doesmatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.pattern.doesMatch(value, searchString[, options]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided value matches the search string, given the provided options. |
| **Parameters**                                       | <ul><li>value         - The value to check.</li><li>searchString  - The string values to match.</li><li>options       - The table of options.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the value matches the search string</li></ul> |
| **Notes**                                            | <ul><li>Supported options:<ul><li>caseSensitive - If <code>true</code>, the case in the search string must match the value.</li><li>exact         - If <code>true</code>, the search string must match exactly somewhere within the value. If <code>false</code>, words separated by spaces can appear anywhere in the value.</li><li>wholeWords    - If <code>true</code>, either the whole string (if <code>exact</code> is <code>true</code>) or each word (if <code>exact</code> is false) must match at word boundaries.</li></ul></li></ul> |

