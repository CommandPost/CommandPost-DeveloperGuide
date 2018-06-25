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
| **Parameters**                                       | <ul><br /><li>jsonString - A string containing some JSON data</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table representing the supplied JSON data</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This is useful for retrieving some of the more complex lua table structures as a persistent setting (see <code>hs.settings</code>)</li><br /></ul>                                             |

#### [encode](#encode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.json.encode(val[, prettyprint]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Encodes a table as JSON                                                                                         |
| **Parameters**                                       | <ul><br /><li>val - A table containing data to be encoded as JSON * prettyprint - An optional boolean, true to format the JSON for human readability, false to format the JSON for size efficiency. Defaults to false</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string containing a JSON representation of the supplied table</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This is useful for storing some of the more complex lua table structures as a persistent setting (see <code>hs.settings</code>)</li><br /></ul>                                             |

