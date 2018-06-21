# [docs](index.md) » hs.base64
---

Base64 encoding and decoding

Portions sourced from (https://gist.github.com/shpakovski/1902994).

## API Overview
* Functions - API calls offered directly by the extension
 * [decode](#decode)
 * [encode](#encode)

## API Documentation

### Functions

#### [decode](#decode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.base64.decode(str) -> val` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Decodes a given base64 string                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">str - A base64 encoded string</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing the decoded data</li></ul>          |

#### [encode](#encode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.base64.encode(val[,width]) -> str` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Encodes a given string to base64                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">val - A string to encode as base64</li><li markdown="1">width - Optional line width to split the string into (usually 64 or 76)</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing the base64 representation of the input string</li></ul>          |

