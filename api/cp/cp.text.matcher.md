# [docs](index.md) » cp.text.matcher
---

This module provides support for loading, manipulating, and comparing unicode text data.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [matcher](#matcher)
* Methods - API calls which can only be made on an object returned by a constructor
 * [find](#find)
 * [gmatch](#gmatch)
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

#### [match](#match)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.text.matcher:match(value[, start]) -> ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Looks for the first match of the pattern in the string `value`. If it finds one, then match returns the captures from the pattern; otherwise it returns `nil`. If pattern specifies no captures, then the whole match is returned. A third, optional numerical argument init specifies where to start the search; its default value is `1` and can be negative.                                                                                         |
| **Parameters**                                       | <ul><li>`value`		- The `cp.text` value to process.</li><li>`start`		- If specified, indicates the starting position to process from. Defaults to `1`.</li></ul> |
| **Returns**                                          | <ul><li>The capture results, the whole match, or `nil`.</li></ul>          |

