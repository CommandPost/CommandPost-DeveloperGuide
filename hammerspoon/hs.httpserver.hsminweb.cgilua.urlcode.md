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

| #### [encodetable](#encodetable)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.httpserver.hsminweb.cgilua.urlcode.encodetable(table) -> string                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Encodes the table of key-value pairs as a query string suitable for inclusion in a URL.                                                           |
| **Parameters**                              |  * table - a table of key-value pairs to be converted into a query string         |
| **Returns**                                 |  * a query string as specified in RFC 3986.                  |
| **Notes**                                   |  * the string will be of the form: "key1=value1&key2=value2..." where all of the keys and values are properly escaped using [cgilua.urlcode.escape](#escape).  If you are crafting a URL by hand, the result of this function should be appended to the end of the URL after a "?" character to specify where the query string begins.                        |

| #### [escape](#escape)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.httpserver.hsminweb.cgilua.urlcode.escape(string) -> string                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | URL encodes the provided string, making it safe as a component within a URL.                                                           |
| **Parameters**                              |  * string - the string to encode         |
| **Returns**                                 |  * a string with non-alphanumeric characters percent encoded and spaces converted into "+" as per RFC 3986.                  |
| **Notes**                                   |  * this function assumes that the provided string is a single component and URL encodes *all* non-alphanumeric characters.  Do not use this function to generate a URL query string -- use [cgilua.urlcode.encodetable](#encodetable).                        |

| #### [insertfield](#insertfield)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.httpserver.hsminweb.cgilua.urlcode.insertfield(table, key, value) -> none                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Inserts the specified key and value into the table of key-value pairs.                                                           |
| **Parameters**                              |  * table - the table of arguments being built * key   - the key name * value - the value to assign to the key specified         |
| **Returns**                                 |  * None                  |
| **Notes**                                   |  * If the key already exists in the table, its value is converted to a table (if it isn't already) and the new value is added to the end of the array of values for the key. * This function is used internally by [cgilua.urlcode.parsequery](#parsequery) or can be used to prepare a table of key-value pairs for [cgilua.urlcode.encodetable](#encodetable).                        |

| #### [parsequery](#parsequery)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.httpserver.hsminweb.cgilua.urlcode.parsequery(query, table) -> none                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Parse the query string and store the key-value pairs in the provided table.                                                           |
| **Parameters**                              |  * query - a URL encoded query string, either from a URL or from the body of a POST request encoded in the "x-www-form-urlencoded" format. * table - the table to add the key-value pairs to         |
| **Returns**                                 |  * None                  |
| **Notes**                                   |  * The specification allows for the same key to be assigned multiple values in an encoded string, but does not specify the behavior; by convention, web servers assign these multiple values to the same key in an array (table).  This function follows that convention.  This is most commonly used by forms which allow selecting multiple options via check boxes or in a selection list. * This function uses [cgilua.urlcode.insertfield](#insertfield) to build the key-value table.                        |

| #### [unescape](#unescape)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.httpserver.hsminweb.cgilua.urlcode.unescape(string) -> string                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Removes any URL encoding in the provided string.                                                           |
| **Parameters**                              |  * string - the string to decode         |
| **Returns**                                 |  * a string with all "+" characters converted to spaces and all percent encoded sequences converted to their ascii equivalents.                  |

