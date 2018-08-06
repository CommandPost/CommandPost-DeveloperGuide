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
| **Type**                                             | Constant |
| **Description**                                      | The list of supported encoding formats: |

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.is(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided value is a `text` instance. |
| **Parameters**                                       | <ul><li><code>value</code>  - The value to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the value is a <code>text</code> instance.</li></ul> |

### Constructors

#### [char](#char)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.char(...) -> text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns the list of one or more codepoint items into a text value, concatenating the results. |
| **Parameters**                                       | <ul><li><code>...</code>    - The list of codepoint integers.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.text</code> value for the list of codepoint values.</li></ul> |

#### [fromCodepoints](#fromcodepoints)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.fromCodepoints(codepoints[, i[, j]]) -> text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns a new `text` instance representing the specified array of codepoints. Since `i` and `j` default to the first |
| **Parameters**                                       | <ul><li><code>codepoints</code> - The array of codepoint integers.</li><li><code>i</code>          - The starting index to read from codepoints. Defaults to <code>1</code>.</li><li><code>j</code>          - The ending index to read from codepoints. Default to <code>-1</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>text</code> instance.</li></ul> |
| **Notes**                                            | <ul><li>You can use a <em>negative</em> value for <code>i</code> and <code>j</code>. If so, it will count back from then end of the <code>codepoints</code> array.</li><li>If the codepoint array begins with a Byte-Order Marker (BOM), the BOM is skipped in the resulting text.</li></ul> |

#### [fromFile](#fromfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.fromFile(path[, encoding]) -> text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns a new `text` instance representing the text loaded from the specified path. If no encoding is specified, |
| **Parameters**                                       | <ul><li><code>value</code>      - The value to turn into a unicode text instance.</li><li><code>encoding</code>   - One of the falues from <code>text.encoding</code>: <code>utf8</code>, <code>utf16le</code>, or <code>utf16be</code>. Defaults to <code>utf8</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>text</code> instance.</li></ul> |

#### [fromString](#fromstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.fromString(value[, encoding]) -> text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns a new `text` instance representing the string value of the specified value. If no encoding is specified, |
| **Parameters**                                       | <ul><li><code>value</code>      - The value to turn into a unicode text instance.</li><li><code>encoding</code>   - One of the falues from <code>text.encoding</code>: <code>utf8</code>, <code>utf16le</code>, or <code>utf16be</code>. Defaults to <code>utf8</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>text</code> instance.</li></ul> |
| **Notes**                                            | <ul><li>Calling <code>text(value)</code> is the same as calling <code>text.fromString(value, text.encoding.utf8)</code>, so simple text can be initialized via <code>local x = text "foo"</code> when the <code>.lua</code> file's encoding is UTF-8.</li></ul> |

### Methods

#### [encode](#encode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:encode([encoding]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the text as an encoded `string` value. |
| **Parameters**                                       | <ul><li><code>encoding</code>   - The encoding to use when converting. Defaults to <code>cp.text.encoding.utf8</code>.</li></ul> |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:find(pattern [, init [, plain]])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Looks for the first match of pattern in the string `value`. If it finds a match, then find returns the indices of `value` where this occurrence starts and ends; otherwise, it returns `nil`. A third, optional numerical argument `init` specifies where to start the search; its default value is `1` and can be negative. A value of `true` as a fourth, optional argument plain turns off the pattern matching facilities, so the function does a plain "find substring" operation, with no characters in pattern being considered "magic". Note that if plain is given, then `init` must be given as well. |
| **Returns**                                          | <ul><li>the start index, the end index, followed by any captures</li></ul> |

#### [len](#len)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:len() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the number of codepoints in the text. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The number of codepoints.</li></ul> |

#### [match](#match)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:match(pattern[, start]) -> ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Looks for the first match of the `pattern` in the text value. If it finds one, then match returns the captures from the pattern; otherwise it returns `nil`. If pattern specifies no captures, then the whole match is returned. A third, optional numerical argument `init` specifies where to start the search; its default value is `1` and can be negative. |
| **Parameters**                                       | <ul><li><code>pattern</code>    - The text pattern to process.</li><li><code>start</code>      - If specified, indicates the starting position to process from. Defaults to <code>1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The capture results, the whole match, or <code>nil</code>.</li></ul> |

#### [sub](#sub)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text:sub(i [, j]) -> cp.text` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the substring of this text that starts at `i` and continues until `j`; `i` and `j` can be negative. |

