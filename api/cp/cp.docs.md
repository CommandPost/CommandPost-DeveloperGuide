# [docs](index.md) » cp.docs
---

Documentation Tools.

These tools are for helping generate CommandPost documentation.

Example Usage:
```lua
require("cp.docs").generate()
```

## API Overview
* Functions - API calls offered directly by the extension
 * [generate](#generate)
 * [generateExtensionLinks](#generateextensionlinks)
 * [updateDeveloperGuideSummary](#updatedeveloperguidesummary)

## API Documentation

### Functions

#### [generate](#generate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.docs.generate() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates the CommandPost Developers Guide.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [generateExtensionLinks](#generateextensionlinks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.docs.generateExtensionLinks(folder) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns markup of all of the API links for a specific group of extensions.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">folder - The folder you want to process (i.e. "cp", "plugins" or "hs").</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The result as a string, otherwise `nil` if an error occurs.</li></ul>          |

#### [updateDeveloperGuideSummary](#updatedeveloperguidesummary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.docs.updateDeveloperGuideSummary() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Developer Guide Summary.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful otherwise `nil`</li></ul>          |

