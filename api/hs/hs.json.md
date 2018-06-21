# [docs](index.md) » hs.json
---

JSON encoding and decoding

This module is based partially on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).


## API Overview
* Functions - API calls offered directly by the extension
 * [decode](#decode)
 * [encode](#encode)

## API Documentation

### Functions

#### [decode](#decode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.json.decode(jsonString) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Decodes JSON into a table                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">jsonString - A string containing some JSON data</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table representing the supplied JSON data</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This is useful for retrieving some of the more complex lua table structures as a persistent setting (see `hs.settings`)</li></ul>                |

#### [encode](#encode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.json.encode(val[, prettyprint]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Encodes a table as JSON                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">val - A table containing data to be encoded as JSON</li><li markdown="1">prettyprint - An optional boolean, true to format the JSON for human readability, false to format the JSON for size efficiency. Defaults to false</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing a JSON representation of the supplied table</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This is useful for storing some of the more complex lua table structures as a persistent setting (see `hs.settings`)</li></ul>                |

