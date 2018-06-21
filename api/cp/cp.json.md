# [docs](index.md) » cp.json
---

A collection of handy JSON tools.

## API Overview
* Functions - API calls offered directly by the extension
 * [decode](#decode)
 * [encode](#encode)
 * [prop](#prop)
 * [read](#read)
 * [write](#write)

## API Documentation

### Functions

#### [decode](#decode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.decode(jsonString) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Decodes JSON into a table                                                                                         |
| **Parameters**                                       |  * jsonString - A string containing some JSON data                                       |
| **Returns**                                          |  * A table representing the supplied JSON data                                                |
| **Notes**                                            |  * This is useful for retrieving some of the more complex lua table structures as a persistent setting (see `hs.settings`)                                                      |

#### [encode](#encode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.encode(val[, prettyprint]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Encodes a table as JSON                                                                                         |
| **Parameters**                                       |  * val - A table containing data to be encoded as JSON * prettyprint - An optional boolean, true to format the JSON for human readability, false to format the JSON for size efficiency. Defaults to false                                       |
| **Returns**                                          |  * A string containing a JSON representation of the supplied table                                                |
| **Notes**                                            |  * This is useful for storing some of the more complex lua table structures as a persistent setting (see `hs.settings`)                                                      |

#### [prop](#prop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.prop(folder, filename, defaultValue) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a `cp.prop` instance for a JSON file.                                                                                         |
| **Parameters**                                       |  * path - The path to the JSON folder (i.e. "~/Library/Caches") * folder - The folder containing the JSON file (i.e. "Final Cut Pro") * filename - The filename of the JSON file (i.e. "Test.json") * defaultValue - The default value if the JSON file doesn't exist yet.                                       |
| **Returns**                                          |  * A `cp.prop` instance.                                                |

#### [read](#read)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.read(path) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Attempts to read the specified path as a JSON file.                                                                                         |
| **Parameters**                                       |  * path      - The JSON file path.                                       |
| **Returns**                                          |  * The JSON file converted into table, or `nil`.                                                |

#### [write](#write)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.write(path, data) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Writes data to a JSON file.                                                                                         |
| **Parameters**                                       |  * path - The path to where you want to save the JSON file. * data - A table containing data to be encoded as JSON.                                       |
| **Returns**                                          |  * `true` if successfully saved, otherwise `false`.                                                |

