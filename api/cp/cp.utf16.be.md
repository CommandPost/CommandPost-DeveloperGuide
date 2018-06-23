# [docs](index.md) » cp.utf16.be
---

A pure-LUA implementation of UTF-16 decoding with big-endian ordering.

## API Overview
* Functions - API calls offered directly by the extension
 * [char](#char)
 * [codepoint](#codepoint)
 * [codes](#codes)
 * [len](#len)
 * [offset](#offset)

## API Documentation

### Functions

#### [char](#char)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.utf16.be.char(...) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Receives zero or more integers, converts each one to its corresponding UTF-16 byte sequence and returns a string with the concatenation of all these sequences.                                                                                         |
| **Parameters**                                       | <ul><li><code>...</code>        - The list of UCL codepoint integers to convert.</li></ul>   |
| **Returns**                                          | <ul><li>All the codepoints converted to UTF-16, concatonated into a string.</li></ul>            |

#### [codepoint](#codepoint)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.utf16.be.codepoint(s [, i [, j]]) -> integer...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the codepoints (as integers) from all characters in `s` that start between byte position `i` and `j` (both included). The default for `i` is 1 and for `j` is `i`. It raises an error if it meets any invalid byte sequence.                                                                                         |
| **Parameters**                                       | <ul><li><code>s</code>              - The string</li></ul><ul><li><code>i</code>              - The starting index. Defaults to <code>1</code>.</li></ul><ul><li><code>j</code>              - The ending index. Defaults to <code>i</code>.</li></ul>   |
| **Returns**                                          | <ul><li>a list of codepoint integers for all characters in the matching range.</li></ul>            |

#### [codes](#codes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.utf16.be.codes(s) -> iterator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns values so that the construction                                                                                         |
| **Parameters**                                       | <ul><li><code>s</code>              - The string to iterate through.</li></ul>   |
| **Returns**                                          | <ul><li>An iterator</li></ul>            |

#### [len](#len)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.utf16.be.len (s [, i [, j]]) -> number | boolean, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the number of UTF-16 characters in string `s` that start between positions `i` and `j` (both inclusive). The default for `i` is 1 and for `j` is -1. If it finds any invalid byte sequence, returns a false value plus the position of the first invalid byte.                                                                                         |
| **Parameters**                                       | <ul><li><code>s</code>              - The UTF-16 string</li></ul><ul><li><code>i</code>              - The starting index. Defaults to <code>1</code>.</li></ul><ul><li><code>j</code>              - The ending index. Defaults to <code>-1</code>.</li></ul>   |
| **Returns**                                          | <ul><li>the length, or <code>false</code> and the first invalid byte index.</li></ul>            |

#### [offset](#offset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.utf16.be.offset (s, n [, i]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the position (in bytes) where the encoding of the `n`-th character of `s` (counting from position `i`) starts. A negative `n` gets characters before position `i`. The default for `i` is 1 when `n` is non-negative and `#s + 1` otherwise, so that `utf8.offset(s, -n)` gets the offset of the `n`-th character from the end of the string. If the specified character is neither in the subject nor right after its end, the function returns nil.                                                                                         |
| **Parameters**                                       | <ul><li><code>s</code>              - The string</li></ul><ul><li><code>n</code>              - The character number to find.</li></ul><ul><li><code>i</code>              - The initial position to start from.</li></ul>   |
| **Returns**                                          | <ul><li>The index</li></ul>            |

