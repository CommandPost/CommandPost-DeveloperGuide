# [docs](index.md) » cp.apple.finalcutpro.export.destinations
---

Provides access to the list of Share Destinations configured for the user.

## API Overview
* Functions - API calls offered directly by the extension
 * [details](#details)
 * [indexOf](#indexof)
 * [names](#names)

## API Documentation

### Functions

#### [details](#details)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.details() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the full details of the current Share Destinations as a table.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The table of Share Destinations.</li></ul>          |

#### [indexOf](#indexof)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.indexOf(name) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the index of the Destination with the specified name, or `nil` if not found.                                                                                         |
| **Parameters**                                       | <ul><li>`name`	- The name of the Destination</li></ul> |
| **Returns**                                          | <ul><li>The index of the named Destination, or `nil`.</li></ul>          |

#### [names](#names)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.names() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an array of the names of destinations, in their current order.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The table of Share Destination names.</li></ul>          |

