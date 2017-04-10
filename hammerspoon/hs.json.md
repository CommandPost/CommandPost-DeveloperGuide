# [docs](../hammerspoon/index.md) » hs.json
---

JSON encoding and decoding

This module is based partially on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).


## API Overview
* Functions - API calls offered directly by the extension
 * [decode](#decode)
 * [encode](#encode)

## API Documentation

### Functions

| [decode](#decode)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.json.decode(jsonString) -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Decodes JSON into a table                                                                     |
| **Parameters**                              | <ul><li>jsonString - A string containing some JSON data</li></ul> |
| **Returns**                                 | <ul><li>A table representing the supplied JSON data</li></ul>          |
| **Notes**                                   | <ul><li>This is useful for retrieving some of the more complex lua table structures as a persistent setting (see `hs.settings`)</li></ul>                |

| [encode](#encode)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.json.encode(val[, prettyprint]) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Encodes a table as JSON                                                                     |
| **Parameters**                              | <ul><li>val - A table containing data to be encoded as JSON</li><li>prettyprint - An optional boolean, true to format the JSON for human readability, false to format the JSON for size efficiency. Defaults to false</li></ul> |
| **Returns**                                 | <ul><li>A string containing a JSON representation of the supplied table</li></ul>          |
| **Notes**                                   | <ul><li>This is useful for storing some of the more complex lua table structures as a persistent setting (see `hs.settings`)</li></ul>                |

