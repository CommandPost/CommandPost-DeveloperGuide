# [docs](index.md) » cp.ids
---

Allows managing values/IDs which can vary between versions.

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [currentVersion](#currentversion)
 * [load](#load)
 * [of](#of)
 * [ofCurrent](#ofcurrent)
 * [previousVersion](#previousversion)

## API Documentation

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids.new(path[, currentVersionFn]) -> cp.ids` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `ids` instance with the specified path to the version files and                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `path`				- The path to the version files.</li><li markdown="1">* `currentVersionFn`	- An optional function that will return the current version as a string or `semver`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* A new `cp.ids` instance.</li></ul>          |

### Methods

#### [currentVersion](#currentversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:currentVersion() -> semver` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current version number for the `IDs` library. May be `nil`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `semver` with the version number or `nil` if none is available.</li></ul>          |

#### [load](#load)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:load([version]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads and caches IDs for the given version. It will search through previous versions,                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">version - The version number you want to load as a string (i.e. "10.4.0"). If not provided, the current version is loaded.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table containing all the IDs</li></ul>          |

#### [of](#of)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:of(version, subset) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a function which can be called to retrieve a specific value for the specified version.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">version - The version number you want to load as a string (i.e. "10.4.0")</li><li markdown="1">subset - A string containing the subset of data you want to load</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A function that will return the value of the specified `subset` ID for the specified version.</li></ul>          |

#### [ofCurrent](#ofcurrent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:ofCurrent(subset) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a function which can be called with an ID to retrieve a specific value for the current version.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">subset - A string containing the subset of data you want to load</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A function that will return the value of the specified `subset` ID for the current version.</li></ul>          |

#### [previousVersion](#previousversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:previousVersion([version]) -> semver` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the previous version number that has stored IDs.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">version		- The version number you want to load as a string (i.e. "10.4.0") or a `semver`, or `nil` to use the current version.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `semver` instance for the previous version.</li></ul>          |

