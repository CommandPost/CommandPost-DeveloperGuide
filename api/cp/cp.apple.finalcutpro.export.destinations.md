# [docs](index.md) » cp.apple.finalcutpro.export.destinations
---

Provides access to the list of Share Destinations configured for the user.

## API Overview
* Constants - Useful values which cannot be changed
 * [DESTINATIONS_FILE](#destinations_file)
 * [DESTINATIONS_PATH](#destinations_path)
 * [DESTINATIONS_PATTERN](#destinations_pattern)
 * [PREFERENCES_PATH](#preferences_path)
* Functions - API calls offered directly by the extension
 * [details](#details)
 * [indexOf](#indexof)
 * [names](#names)

## API Documentation

### Constants

#### [DESTINATIONS_FILE](#destinations_file)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.DESTINATIONS_FILE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The Destinations File. |

#### [DESTINATIONS_PATH](#destinations_path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.DESTINATIONS_PATH -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The Destinations Path. |

#### [DESTINATIONS_PATTERN](#destinations_pattern)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.DESTINATIONS_PATTERN -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Destinations File Pattern. |

#### [PREFERENCES_PATH](#preferences_path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.PREFERENCES_PATH -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The Preferences Path |

### Functions

#### [details](#details)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.details() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the full details of the current Share Destinations as a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The table of Share Destinations.</li></ul> |

#### [indexOf](#indexof)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.indexOf(name) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the index of the Destination with the specified name, or `nil` if not found. |
| **Parameters**                                       | <ul><li><code>name</code>   - The name of the Destination</li></ul> |
| **Returns**                                          | <ul><li>The index of the named Destination, or <code>nil</code>.</li></ul> |

#### [names](#names)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.destinations.names() -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns an array of the names of destinations, in their current order. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The table of Share Destination names, or <code>nil</code> if an error has occurred.</li><li>An error message as a string.</li></ul> |

