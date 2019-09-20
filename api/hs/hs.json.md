# [docs](index.md) » hs.json
---

JSON encoding and decoding

This module is based partially on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).


## API Overview
* Functions - API calls offered directly by the extension
 * [decode](#decode)
 * [encode](#encode)
 * [read](#read)
 * [write](#write)

## API Documentation

### Functions

#### [decode](#decode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.json.decode(jsonString) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Decodes JSON into a table |
| **Parameters**                                       | <ul><li>jsonString - A string containing some JSON data</li></ul> |
| **Returns**                                          | <ul><li>A table representing the supplied JSON data</li></ul> |
| **Notes**                                            | <ul><li>This is useful for retrieving some of the more complex lua table structures as a persistent setting (see <code>hs.settings</code>)</li></ul> |

#### [encode](#encode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.json.encode(val[, prettyprint]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Encodes a table as JSON |
| **Parameters**                                       | <ul><li>val - A table containing data to be encoded as JSON</li><li>prettyprint - An optional boolean, true to format the JSON for human readability, false to format the JSON for size efficiency. Defaults to false</li></ul> |
| **Returns**                                          | <ul><li>A string containing a JSON representation of the supplied table</li></ul> |
| **Notes**                                            | <ul><li>This is useful for storing some of the more complex lua table structures as a persistent setting (see <code>hs.settings</code>)</li></ul> |

#### [read](#read)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.json.read(path) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Decodes JSON file into a table. |
| **Parameters**                                       | <ul><li>path - The path and filename of the JSON file to read.</li></ul> |
| **Returns**                                          | <ul><li>A table representing the supplied JSON data, or <code>nil</code> if an error occurs.</li></ul> |

#### [write](#write)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.json.write(data, path, [prettyprint], [replace]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Encodes a table as JSON to a file |
| **Parameters**                                       | <ul><li>data - A table containing data to be encoded as JSON</li><li>path - The path and filename of the JSON file to write to</li><li>prettyprint - An optional boolean, <code>true</code> to format the JSON for human readability, <code>false</code> to format the JSON for size efficiency. Defaults to <code>false</code></li><li>replace - An optional boolean, <code>true</code> to replace an existing file at the same path if one exists. Defaults to <code>false</code></li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code> if an error has occurred</li></ul> |

