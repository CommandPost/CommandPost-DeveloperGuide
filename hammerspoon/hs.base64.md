# [docs](index.md) » hs.base64
---

Base64 encoding and decoding

Portions sourced from (https://gist.github.com/shpakovski/1902994).

## API Overview
* Functions - API calls offered directly by the extension
** [decode](#decode)
** [encode](#encode)

## API Documentation

### Functions

#### [decode](#decode)
| | |
|-|-|
| Signature   | hs.base64.decode(str) -> val  |
| Type        | Function |
| Description | Decodes a given base64 string |
| Parameters |  * str - A base64 encoded string | | Returns |  * A string containing the decoded data | 
#### [encode](#encode)
| | |
|-|-|
| Signature   | hs.base64.encode(val[,width]) -> str  |
| Type        | Function |
| Description | Encodes a given string to base64 |
| Parameters |  * val - A string to encode as base64 * width - Optional line width to split the string into (usually 64 or 76) | | Returns |  * A string containing the base64 representation of the input string | 