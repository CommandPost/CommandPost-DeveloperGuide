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
 * [versions](#versions)

## API Documentation

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids.new(path[, currentVersionFn]) -> cp.ids` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new `ids` instance with the specified path to the version files and |
| **Parameters**                                       | <ul><li><code>path</code>                - The path to the version files.</li><li><code>currentVersionFn</code>    - An optional function that will return the current version as a string or <code>semver</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>cp.ids</code> instance.</li></ul> |

### Methods

#### [currentVersion](#currentversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:currentVersion() -> semver` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the current version number for the `IDs` library. May be `nil`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>semver</code> with the version number or <code>nil</code> if none is available.</li></ul> |

#### [load](#load)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:load([version]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads and caches IDs for the given version. It will search through previous versions, |
| **Parameters**                                       | <ul><li>version - The version number you want to load as a string (i.e. "10.4.0"). If not provided, the current version is loaded.</li></ul> |
| **Returns**                                          | <ul><li>A table containing all the IDs</li></ul> |

#### [of](#of)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:of(version, subset) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a function which can be called to retrieve a specific value for the specified version. |
| **Parameters**                                       | <ul><li>version - The version number you want to load as a string (i.e. "10.4.0")</li><li>subset - A string containing the subset of data you want to load</li></ul> |
| **Returns**                                          | <ul><li>A function that will return the value of the specified <code>subset</code> ID for the specified version.</li></ul> |

#### [ofCurrent](#ofcurrent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:ofCurrent(subset) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a function which can be called with an ID to retrieve a specific value for the current version. |
| **Parameters**                                       | <ul><li>subset - A string containing the subset of data you want to load</li></ul> |
| **Returns**                                          | <ul><li>A function that will return the value of the specified <code>subset</code> ID for the current version.</li></ul> |

#### [previousVersion](#previousversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:previousVersion([version]) -> semver` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the previous version number that has stored IDs. |
| **Parameters**                                       | <ul><li>version      - The version number you want to load as a string (i.e. "10.4.0") or a <code>semver</code>, or <code>nil</code> to use the current version.</li></ul> |
| **Returns**                                          | <ul><li>A <code>semver</code> instance for the previous version.</li></ul> |

#### [versions](#versions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:versions() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table of versions. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>semver</code> objects.</li></ul> |

