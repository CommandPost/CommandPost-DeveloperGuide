# [docs](index.md) » cp.utf16
---

A pure-LUA implementation of UTF-16 decoding

## Submodules
 * [cp.utf16.be](cp.utf16.be.md)
 * [cp.utf16.le](cp.utf16.le.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [char](#char)
 * [codepoint](#codepoint)
 * [codes](#codes)
 * [offset](#offset)

## API Documentation

### Functions

#### [char](#char)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.utf16.char(bigEndian, ...) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Receives zero or more integers, converts each one to its corresponding UTF-16 byte sequence and returns a string with the concatenation of all these sequences.                                                                                         |
| **Parameters**                                       |  * `bigEndian`	- If `true`, the output will list the 'big' bytes first * `...`		- The list of UCL codepoint integers to convert.                                       |
| **Returns**                                          |  * All the codepoints converted to UTF-16, concatonated into a string.                                                |

#### [codepoint](#codepoint)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.utf16.codepoint(bigEndian, s [, i [, j]]) -> integer...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the codepoints (as integers) from all characters in `s` that start between byte position `i` and `j` (both included). The default for `i` is 1 and for `j` is `i`. It raises an error if it meets any invalid byte sequence.                                                                                         |
| **Parameters**                                       |  * `bigEndian`		- (optional) If set to `true`, the string is encoded in 'big-endian' format. * `s`				- The string * `i`				- The starting index. Defaults to `1`. * `j`				- The ending index. Defaults to `i`.                                       |
| **Returns**                                          |  * a list of codepoint integers for all characters in the matching range.                                                |

#### [codes](#codes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.utf16.codes(bigEndian, s) -> iterator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns values so that the construction                                                                                         |
| **Parameters**                                       |  * `bigEndian`		- If `true`, the provided string is in 'big-endian' encoding. * `s`				- The string to iterate through.                                       |
| **Returns**                                          |  * An iterator                                                |

#### [offset](#offset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.utf16.offset (bigEndian, s, n [, i]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the position (in bytes) where the encoding of the `n`-th character of `s` (counting from position `i`) starts. A negative `n` gets characters before position `i`. The default for `i` is 1 when `n` is non-negative and `#s + 1` otherwise, so that `utf8.offset(s, -n)` gets the offset of the `n`-th character from the end of the string. If the specified character is neither in the subject nor right after its end, the function returns nil.                                                                                         |
| **Parameters**                                       |  * `bigEndian`		- If `true`, the encoding is 'big-endian'. Defaults to `false` * `s`				- The string * `n`				- The character number to find. * `i`				- The initial position to start from.                                       |
| **Returns**                                          |  * The index                                                |

