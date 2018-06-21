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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">jsonString - A string containing some JSON data</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table representing the supplied JSON data</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This is useful for retrieving some of the more complex lua table structures as a persistent setting (see `hs.settings`)</li></ul>                |

#### [encode](#encode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.encode(val[, prettyprint]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Encodes a table as JSON                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">val - A table containing data to be encoded as JSON</li><li markdown="1">prettyprint - An optional boolean, true to format the JSON for human readability, false to format the JSON for size efficiency. Defaults to false</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing a JSON representation of the supplied table</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This is useful for storing some of the more complex lua table structures as a persistent setting (see `hs.settings`)</li></ul>                |

#### [prop](#prop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.prop(folder, filename, defaultValue) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a `cp.prop` instance for a JSON file.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - The path to the JSON folder (i.e. "~/Library/Caches")</li><li markdown="1">folder - The folder containing the JSON file (i.e. "Final Cut Pro")</li><li markdown="1">filename - The filename of the JSON file (i.e. "Test.json")</li><li markdown="1">defaultValue - The default value if the JSON file doesn't exist yet.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `cp.prop` instance.</li></ul>          |

#### [read](#read)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.read(path) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Attempts to read the specified path as a JSON file.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path      - The JSON file path.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The JSON file converted into table, or `nil`.</li></ul>          |

#### [write](#write)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.write(path, data) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Writes data to a JSON file.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - The path to where you want to save the JSON file.</li><li markdown="1">data - A table containing data to be encoded as JSON.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successfully saved, otherwise `false`.</li></ul>          |

