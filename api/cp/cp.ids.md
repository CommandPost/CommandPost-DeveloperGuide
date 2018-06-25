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
| **Parameters**                                       | <ul><br /><li><code>path</code>                - The path to the version files.* <code>currentVersionFn</code>    - An optional function that will return the current version as a string or <code>semver</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A new <code>cp.ids</code> instance.</li><br /></ul>                                           |

### Methods

#### [currentVersion](#currentversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:currentVersion() -> semver` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current version number for the `IDs` library. May be `nil`.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A <code>semver</code> with the version number or <code>nil</code> if none is available.</li><br /></ul>                                           |

#### [load](#load)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:load([version]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads and caches IDs for the given version. It will search through previous versions,                                                                                         |
| **Parameters**                                       | <ul><br /><li>version - The version number you want to load as a string (i.e. "10.4.0"). If not provided, the current version is loaded.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing all the IDs</li><br /></ul>                                           |

#### [of](#of)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:of(version, subset) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a function which can be called to retrieve a specific value for the specified version.                                                                                         |
| **Parameters**                                       | <ul><br /><li>version - The version number you want to load as a string (i.e. "10.4.0") * subset - A string containing the subset of data you want to load</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A function that will return the value of the specified <code>subset</code> ID for the specified version.</li><br /></ul>                                           |

#### [ofCurrent](#ofcurrent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:ofCurrent(subset) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a function which can be called with an ID to retrieve a specific value for the current version.                                                                                         |
| **Parameters**                                       | <ul><br /><li>subset - A string containing the subset of data you want to load</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A function that will return the value of the specified <code>subset</code> ID for the current version.</li><br /></ul>                                           |

#### [previousVersion](#previousversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ids:previousVersion([version]) -> semver` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the previous version number that has stored IDs.                                                                                         |
| **Parameters**                                       | <ul><br /><li>version      - The version number you want to load as a string (i.e. "10.4.0") or a <code>semver</code>, or <code>nil</code> to use the current version.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A <code>semver</code> instance for the previous version.</li><br /></ul>                                           |

