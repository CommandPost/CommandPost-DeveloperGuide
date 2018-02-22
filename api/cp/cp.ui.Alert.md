# [docs](index.md) » cp.ui.Alert
---

Alert UI Module.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [containsText](#containstext)

## API Documentation

### Methods

#### [containsText](#containstext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:containsText(value[, plain]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if there are any child text elements containing the exact text or pattern, from beginning to end.                                                                                         |
| **Parameters**                                       | <ul><li>* textPattern   - The text pattern to check.</li><li>* plain         - If `true`, the text will be compared exactly, otherwise it will be considered to be a pattern. Defaults to `false`.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if an element's `AXValue` matches the text pattern exactly.</li></ul>          |

