# [docs](index.md) » cp.docs
---

Documentation Tools.

These tools are for helping generate CommandPost documentation.

Example Usage:
```lua
require("cp.docs").updateDeveloperGuideSummary()
```

## API Overview
* Functions - API calls offered directly by the extension
 * [generateExtensionLinks](#generateextensionlinks)
 * [updateDeveloperGuideSummary](#updatedeveloperguidesummary)

## API Documentation

### Functions

#### [generateExtensionLinks](#generateextensionlinks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.docs.generateExtensionLinks(folder) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns markup of all of the API links for a specific group of extensions.                                                                                         |
| **Parameters**                                       | <ul><li>folder - The folder you want to process (i.e. "cp", "plugins" or "hs").</li></ul> |
| **Returns**                                          | <ul><li>The result as a string, otherwise `nil` if an error occurs.</li></ul>          |

#### [updateDeveloperGuideSummary](#updatedeveloperguidesummary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.docs.updateDeveloperGuideSummary(folder) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Developer Guide Summary.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

