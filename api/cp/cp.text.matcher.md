# [docs](index.md) » cp.text.matcher
---

This module provides support for loading, manipulating, and comparing unicode text data.

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
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns a matcher for the specified pattern. This follows the conventions of the standard [LUA Patterns](https://www.lua.org/pil/20.2.html) API. This will return a reusable, compiled parser for the given pattern.                                                                                         |
| **Parameters**                                       | <ul><li>`pattern`	- The pattern to parse</li><li>`plain`		- If `true`, the pattern is not parsed and the provided text must match exactly.</li></ul> |

### Methods

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher:find(value[, start]) -> number, number, ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Processes the text, returning the start position, the end position, followed by any capture group values.                                                                                         |
| **Parameters**                                       | <ul><li>`value`		- The `cp.text` value to process.</li><li>`start`		- If specified, indicates the starting position to process from. Defaults to `1`.</li></ul> |
| **Returns**                                          | <ul><li>The start position for the match, end position, and the list of capture group values.</li></ul>          |

#### [gmatch](#gmatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher:gmatch(value) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an iterator function that, each time it is called, returns the next captures from pattern over string s. If pattern specifies no captures, then the whole match is produced in each call.                                                                                         |
| **Parameters**                                       | <ul><li>`value`		- The `cp.text` value to process.</li></ul> |
| **Returns**                                          | <ul><li>The iterator function.</li></ul>          |

#### [gsub](#gsub)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher:gsub(value, repl, limit) -> text, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a copy of `value` in which all (or the first `n`, if given) occurrences of the pattern have been replaced by a replacement string specified by `repl`, which can be text, a string, a table, or a function. gsub also returns, as its second value, the total number of matches that occurred.                                                                                         |
| **Parameters**                                       | <ul><li>`value`	- The text or string value to process.</li><li>`repl`	- The replacement text/string/table/function</li><li>`limit`	- The maximum number of times to do the replacement. Defaults to unlimited.</li></ul> |
| **Returns**                                          | <ul><li>`text`	- The text value with replacements.</li><li>`number`	- The number of matches that occurred.</li></ul>          |
| **Notes**                                            | <ul><li>If repl is text or a string, then its value is used for replacement. The character `%` works as an escape character: any sequence in repl of the form `%n`, with `n` between `1` and `9`, stands for the value of the `n`-th captured substring (see below). The sequence `%0` stands for the whole match. The sequence `%%` stands for a single `%`.</li><li>If `repl` is a table, then the table is queried for every match, using the first capture as the key; if the pattern specifies no captures, then the whole match is used as the key.</li><li>If `repl` is a function, then this function is called every time a match occurs, with all captured substrings passed as arguments, in order; if the pattern specifies no captures, then the whole match is passed as a sole argument.</li><li>If the value returned by the table query or by the function call is a string or a number, then it is used as the replacement string; otherwise, if it is `false` or `nil`, then there is no replacement (that is, the original match is kept in the string).</li></ul>                |

#### [match](#match)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher:match(value[, start]) -> ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Looks for the first match of the pattern in the string `value`. If it finds one, then match returns the captures from the pattern; otherwise it returns `nil`. If pattern specifies no captures, then the whole match is returned. A third, optional numerical argument init specifies where to start the search; its default value is `1` and can be negative.                                                                                         |
| **Parameters**                                       | <ul><li>`value`		- The `cp.text` value to process.</li><li>`start`		- If specified, indicates the starting position to process from. Defaults to `1`.</li></ul> |
| **Returns**                                          | <ul><li>The capture results, the whole match, or `nil`.</li></ul>          |

