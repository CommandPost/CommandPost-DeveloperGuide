# [docs](index.md) » cp.text
---

This module provides support for loading, manipulating, and comparing unicode text data.
It works by storing characters with their Unicode 'codepoint` value. In practice, this means that every character is a 64-bit integer, so a `text` value will use substantially more memory than the equivalent encoded `string` value.

The advantages of `text` over `string` representations for Unicode are:
 * comparisons, equality checks, etc. actually work for Unicode text and are not encoding-dependent.
 * direct access to codepoint values.

The advantages of `string` representations for Unicode are:
 * compactness.
 * reading/writing to files via the standard `io` library.

## Strings and Unicode

LUA has limited built-in support for Unicode text. `string` values are "8-bit clean", which means it is an array of 8-bit characters. This is also how binary data from files is usually loaded, as 8-bit 'bytes'. Unicode characters can be up to 32-bits, so there are several standard ways to represent Unicode characters using 8-bit characters. Without going into detail, the most common encodings are called 'UTF-8' and 'UTF-16'. There are two variations of 'UTF-16', depending on the hardware architecture, known as 'big-endian' and 'little-endian'.

The built-in functions for `string`, such as `match`, `gsub` and even `len` will not work as expected when a string contains Unicode text. As such, this library fills some of the gaps for common operations when working with Unicode text.

## Examples

You can convert to and from `string` and `text` values like so:

```lua
local text = require("cp.text")

local simpleString		= "foobar"
local simpleText		= text(stringValue)
local utf8String		= "a丽𐐷"				-- contains non-ascii characters, defaults to UTF-8.
local unicodeText		= text "a丽𐐷"			-- contains non-ascii characters, converts from a UTF-8 string.
local utf8String		= tostring(unicodeText) -- `tostring` will default to UTF-8 encoding
local utf16leString		= unicodeText:encode(text.encoding.utf16le) -- or you can be more specific
```

Note that `text` values are not in any specific encoding, since they are stored as 64-bit integer `code-points` rather than 8-bit characers.

## Submodules
 * [cp.text.matcher](cp.text.matcher.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [encoding](#encoding)
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [char](#char)
 * [fromCodepoints](#fromcodepoints)
 * [fromFile](#fromfile)
 * [fromString](#fromstring)
* Methods - API calls which can only be made on an object returned by a constructor
 * [encode](#encode)
 * [find](#find)
 * [len](#len)
 * [match](#match)
 * [sub](#sub)

## API Documentation

### Constants

#### [encoding](#encoding)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.encoding` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The list of supported encoding formats:                                                                                         |

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.is(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the provided value is a `text` instance.                                                                                         |
| **Parameters**                                       |  * `value`	- The value to check                                       |
| **Returns**                                          |  * `true` if the value is a `text` instance.                                                |

### Constructors

#### [char](#char)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.char(...) -> text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns the list of one or more codepoint items into a text value, concatenating the results.                                                                                         |
| **Parameters**                                       |  * `...`	- The list of codepoint integers.                                       |
| **Returns**                                          |  * The `cp.text` value for the list of codepoint values.                                                |

#### [fromCodepoints](#fromcodepoints)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.fromCodepoints(codepoints[, i[, j]]) -> text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns a new `text` instance representing the specified array of codepoints. Since `i` and `j` default to the first                                                                                         |
| **Parameters**                                       |  * `codepoints`	- The array of codepoint integers. * `i`			- The starting index to read from codepoints. Defaults to `1`. * `j`			- The ending index to read from codepoints. Default to `-1`.                                       |
| **Returns**                                          |  * A new `text` instance.                                                |
| **Notes**                                            |  * You can use a *negative* value for `i` and `j`. If so, it will count back from then end of the `codepoints` array. * If the codepoint array begins with a Byte-Order Marker (BOM), the BOM is skipped in the resulting text.                                                      |

#### [fromFile](#fromfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.fromFile(path[, encoding]) -> text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns a new `text` instance representing the text loaded from the specified path. If no encoding is specified,                                                                                         |
| **Parameters**                                       |  * `value`		- The value to turn into a unicode text instance. * `encoding`	- One of the falues from `text.encoding`: `utf8`, `utf16le`, or `utf16be`. Defaults to `utf8`.                                       |
| **Returns**                                          |  * A new `text` instance.                                                |

#### [fromString](#fromstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.fromString(value[, encoding]) -> text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns a new `text` instance representing the string value of the specified value. If no encoding is specified,                                                                                         |
| **Parameters**                                       |  * `value`		- The value to turn into a unicode text instance. * `encoding`	- One of the falues from `text.encoding`: `utf8`, `utf16le`, or `utf16be`. Defaults to `utf8`.                                       |
| **Returns**                                          |  * A new `text` instance.                                                |
| **Notes**                                            |  * Calling `text(value)` is the same as calling `text.fromString(value, text.encoding.utf8)`, so simple text can be initialized via `local x = text "foo"` when the `.lua` file's encoding is UTF-8.                                                      |

### Methods

#### [encode](#encode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:encode([encoding]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the text as an encoded `string` value.                                                                                         |
| **Parameters**                                       |  * `encoding`	- The encoding to use when converting. Defaults to `cp.text.encoding.utf8`.                                       |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:find(pattern [, init [, plain]])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Looks for the first match of pattern in the string `value`. If it finds a match, then find returns the indices of `value` where this occurrence starts and ends; otherwise, it returns `nil`. A third, optional numerical argument `init` specifies where to start the search; its default value is `1` and can be negative. A value of `true` as a fourth, optional argument plain turns off the pattern matching facilities, so the function does a plain "find substring" operation, with no characters in pattern being considered "magic". Note that if plain is given, then `init` must be given as well.                                                                                         |
| **Returns**                                          |  * the start index, the end index, followed by any captures                                                |

#### [len](#len)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:len() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the number of codepoints in the text.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The number of codepoints.                                                |

#### [match](#match)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:match(pattern[, start]) -> ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Looks for the first match of the `pattern` in the text value. If it finds one, then match returns the captures from the pattern; otherwise it returns `nil`. If pattern specifies no captures, then the whole match is returned. A third, optional numerical argument `init` specifies where to start the search; its default value is `1` and can be negative.                                                                                         |
| **Parameters**                                       |  * `pattern`	- The text pattern to process. * `start`		- If specified, indicates the starting position to process from. Defaults to `1`.                                       |
| **Returns**                                          |  * The capture results, the whole match, or `nil`.                                                |

#### [sub](#sub)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:sub(i [, j]) -> cp.text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the substring of this text that starts at `i` and continues until `j`; `i` and `j` can be negative.                                                                                         |

