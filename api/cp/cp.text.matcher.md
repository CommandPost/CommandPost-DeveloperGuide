# [docs](index.md) » cp.text.matcher
---

Adapted from 'utf8.lua' (https://github.com/Stepets/utf8.lua)

Copyright (c) 2006-2007, Kyle Smith
All rights reserved.

Contributors:
    Alimov Stepan
    David Peterson

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

    * Redistributions of source code must retain the above copyright notice,
      this list of conditions and the following disclaimer.
    * Redistributions in binary form must reproduce the above copyright
      notice, this list of conditions and the following disclaimer in the
      documentation and/or other materials provided with the distribution.
    * Neither the name of the author nor the names of its contributors may be
      used to endorse or promote products derived from this software without
      specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [matcher](#matcher)
* Methods - API calls which can only be made on an object returned by a constructor
 * [find](#find)
 * [gmatch](#gmatch)
 * [gsub](#gsub)
 * [match](#match)

## API Documentation

### Constructors

#### [matcher](#matcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher(pattern[, plain]) -> cp.text.matcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns a matcher for the specified pattern. This follows the conventions of the standard [LUA Patterns](https://www.lua.org/pil/20.2.html) API. This will return a reusable, compiled parser for the given pattern. |
| **Parameters**                                       | <ul><li><code>pattern</code>    - The pattern to parse * <code>plain</code>        - If <code>true</code>, the pattern is not parsed and the provided text must match exactly.Returns:* New <code>cp.text.matcher</code> for the pattern.</li></ul> |
| **Returns**                                          | <ul><li>New <code>cp.text.matcher</code> for the pattern.</li></ul> |

### Methods

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher:find(value[, start]) -> number, number, ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Processes the text, returning the start position, the end position, followed by any capture group values. |
| **Parameters**                                       | <ul><li><code>value</code>      - The <code>cp.text</code> value to process. * <code>start</code>     - If specified, indicates the starting position to process from. Defaults to <code>1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The start position for the match, end position, and the list of capture group values.</li></ul> |

#### [gmatch](#gmatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher:gmatch(value) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an iterator function that, each time it is called, returns the next captures from pattern over string s. If pattern specifies no captures, then the whole match is produced in each call. |
| **Parameters**                                       | <ul><li><code>value</code>      - The <code>cp.text</code> value to process.</li></ul> |
| **Returns**                                          | <ul><li>The iterator function.</li></ul> |

#### [gsub](#gsub)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher:gsub(value, repl, limit) -> text, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a copy of `value` in which all (or the first `n`, if given) occurrences of the pattern have been replaced by a replacement string specified by `repl`, which can be text, a string, a table, or a function. gsub also returns, as its second value, the total number of matches that occurred. |
| **Parameters**                                       | <ul><li><code>value</code>  - The text or string value to process. * <code>repl</code> - The replacement text/string/table/function * <code>limit</code>  - The maximum number of times to do the replacement. Defaults to unlimited.</li></ul> |
| **Returns**                                          | <ul><li><code>text</code>   - The text value with replacements. * <code>number</code>  - The number of matches that occurred.</li></ul> |
| **Notes**                                            | <ul><li>If repl is text or a string, then its value is used for replacement. The character <code>%</code> works as an escape character: any sequence in repl of the form <code>%n</code>, with <code>n</code> between <code>1</code> and <code>9</code>, stands for the value of the <code>n</code>-th captured substring (see below). The sequence <code>%0</code> stands for the whole match. The sequence <code>%%</code> stands for a single <code>%</code>. * If <code>repl</code> is a table, then the table is queried for every match, using the first capture as the key; if the pattern specifies no captures, then the whole match is used as the key. * If <code>repl</code> is a function, then this function is called every time a match occurs, with all captured substrings passed as arguments, in order; if the pattern specifies no captures, then the whole match is passed as a sole argument. * If the value returned by the table query or by the function call is a string or a number, then it is used as the replacement string; otherwise, if it is <code>false</code> or <code>nil</code>, then there is no replacement (that is, the original match is kept in the string).</li></ul> |

#### [match](#match)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher:match(value[, start]) -> ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Looks for the first match of the pattern in the string `value`. If it finds one, then match returns the captures from the pattern; otherwise it returns `nil`. If pattern specifies no captures, then the whole match is returned. A third, optional numerical argument init specifies where to start the search; its default value is `1` and can be negative. |
| **Parameters**                                       | <ul><li><code>value</code>      - The <code>cp.text</code> value to process. * <code>start</code>     - If specified, indicates the starting position to process from. Defaults to <code>1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The capture results, the whole match, or <code>nil</code>.</li></ul> |

