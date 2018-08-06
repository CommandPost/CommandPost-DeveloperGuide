# [docs](index.md) » hs.httpserver.hsminweb.cgilua.urlcode
---

Support functions for the CGILua compatibility module for encoding and decoding URL components in accordance with RFC 3986.

## API Overview
* Functions - API calls offered directly by the extension
 * [encodetable](#encodetable)
 * [escape](#escape)
 * [insertfield](#insertfield)
 * [parsequery](#parsequery)
 * [unescape](#unescape)

## API Documentation

### Functions

#### [encodetable](#encodetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.cgilua.urlcode.encodetable(table) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Encodes the table of key-value pairs as a query string suitable for inclusion in a URL. |
| **Parameters**                                       | <ul><li>table - a table of key-value pairs to be converted into a query string</li></ul> |
| **Returns**                                          | <ul><li>a query string as specified in RFC 3986.</li></ul> |
| **Notes**                                            | <ul><li>the string will be of the form: "key1=value1&amp;key2=value2..." where all of the keys and values are properly escaped using <a href="#escape">cgilua.urlcode.escape</a>.  If you are crafting a URL by hand, the result of this function should be appended to the end of the URL after a "?" character to specify where the query string begins.</li></ul> |

#### [escape](#escape)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.cgilua.urlcode.escape(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | URL encodes the provided string, making it safe as a component within a URL. |
| **Parameters**                                       | <ul><li>string - the string to encode</li></ul> |
| **Returns**                                          | <ul><li>a string with non-alphanumeric characters percent encoded and spaces converted into "+" as per RFC 3986.</li></ul> |
| **Notes**                                            | <ul><li>this function assumes that the provided string is a single component and URL encodes <em>all</em> non-alphanumeric characters.  Do not use this function to generate a URL query string -- use <a href="#encodetable">cgilua.urlcode.encodetable</a>.</li></ul> |

#### [insertfield](#insertfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.cgilua.urlcode.insertfield(table, key, value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Inserts the specified key and value into the table of key-value pairs. |
| **Parameters**                                       | <ul><li>table - the table of arguments being built</li><li>key   - the key name</li><li>value - the value to assign to the key specified</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>If the key already exists in the table, its value is converted to a table (if it isn't already) and the new value is added to the end of the array of values for the key.</li><li>This function is used internally by <a href="#parsequery">cgilua.urlcode.parsequery</a> or can be used to prepare a table of key-value pairs for <a href="#encodetable">cgilua.urlcode.encodetable</a>.</li></ul> |

#### [parsequery](#parsequery)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.cgilua.urlcode.parsequery(query, table) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Parse the query string and store the key-value pairs in the provided table. |
| **Parameters**                                       | <ul><li>query - a URL encoded query string, either from a URL or from the body of a POST request encoded in the "x-www-form-urlencoded" format.</li><li>table - the table to add the key-value pairs to</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>The specification allows for the same key to be assigned multiple values in an encoded string, but does not specify the behavior; by convention, web servers assign these multiple values to the same key in an array (table).  This function follows that convention.  This is most commonly used by forms which allow selecting multiple options via check boxes or in a selection list.</li><li>This function uses <a href="#insertfield">cgilua.urlcode.insertfield</a> to build the key-value table.</li></ul> |

#### [unescape](#unescape)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.cgilua.urlcode.unescape(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes any URL encoding in the provided string. |
| **Parameters**                                       | <ul><li>string - the string to decode</li></ul> |
| **Returns**                                          | <ul><li>a string with all "+" characters converted to spaces and all percent encoded sequences converted to their ascii equivalents.</li></ul> |

