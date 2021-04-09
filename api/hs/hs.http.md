# [docs](index.md) » hs.http
---

Perform HTTP requests

## API Overview
* Variables - Configurable values
 * [htmlEntities](#htmlentities)
* Functions - API calls offered directly by the extension
 * [asyncGet](#asyncget)
 * [asyncPost](#asyncpost)
 * [convertHtmlEntities](#converthtmlentities)
 * [doAsyncRequest](#doasyncrequest)
 * [doRequest](#dorequest)
 * [encodeForQuery](#encodeforquery)
 * [get](#get)
 * [post](#post)
 * [registerEntity](#registerentity)
 * [urlParts](#urlparts)

## API Documentation

### Variables

#### [htmlEntities](#htmlentities)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.htmlEntities[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A collection of common HTML Entities (&whatever;) and their UTF8 equivalents.  To retrieve the UTF8 sequence for a given entity, reference the table as `hs.http.htmlEntities["&key;"]` where `key` is the text of the entity's name or a numeric reference like `#number`. |
| **Notes**                                            | <ul><li>This list is likely not complete.  It is based on the list of common entities described at http://www.freeformatter.com/html-entities.html.</li><li>Additional entities can be temporarily added via the <code>hs.http.registerEntity(...)</code> function.  If you feel you have a more official list of entities which contains items which are currently not included by default, please open up an issue at https://github.com/Hammerspoon/hammerspoon and your link will be considered.</li><li>To see a list of the currently defined entities, a __tostring meta-method is included so that referencing the table directly as a string will return the current definitions.</li><li>For reference, this meta-method is essentially the following:</li></ul> |

### Functions

#### [asyncGet](#asyncget)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.asyncGet(url, headers, callback)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends an HTTP GET request asynchronously |
| **Parameters**                                       | <ul><li>url - A string containing the URL to retrieve</li><li>headers - A table containing string keys and values representing the request headers, or nil to add no headers</li><li>callback - A function to be called when the request succeeds or fails. The function will be passed three parameters:</li><li>A number containing the HTTP response status</li><li>A string containing the response body</li><li>A table containing the response headers</li></ul> |
| **Notes**                                            | <ul><li>If authentication is required in order to download the request, the required credentials must be specified as part of the URL (e.g. "http://user:password@host.com/"). If authentication fails, or credentials are missing, the connection will attempt to continue without credentials.</li></ul> |

#### [asyncPost](#asyncpost)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.asyncPost(url, data, headers, callback)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends an HTTP POST request asynchronously |
| **Parameters**                                       | <ul><li>url - A string containing the URL to submit to</li><li>data - A string containing the request body, or nil to send no body</li><li>headers - A table containing string keys and values representing the request headers, or nil to add no headers</li><li>callback - A function to be called when the request succeeds or fails. The function will be passed three parameters:</li><li>A number containing the HTTP response status</li><li>A string containing the response body</li><li>A table containing the response headers</li></ul> |
| **Notes**                                            | <ul><li>If authentication is required in order to download the request, the required credentials must be specified as part of the URL (e.g. "http://user:password@host.com/"). If authentication fails, or credentials are missing, the connection will attempt to continue without credentials.</li></ul> |

#### [convertHtmlEntities](#converthtmlentities)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.convertHtmlEntities(inString) -> outString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Convert all recognized HTML Entities in the `inString` to appropriate UTF8 byte sequences and returns the converted text. |
| **Parameters**                                       | <ul><li>inString -- A string containing any number of HTML Entities (&whatever;) in the text.</li></ul> |
| **Returns**                                          | <ul><li>outString -- the input string with all recognized HTML Entity sequences converted to UTF8 byte sequences.</li></ul> |
| **Notes**                                            | <ul><li>Recognized HTML Entities are those registered in <code>hs.http.htmlEntities</code> or numeric entity sequences: &amp;#n; where <code>n</code> can be any integer number.</li><li>This function is especially useful as a post-filter to data retrieved by the <code>hs.http.get</code> and <code>hs.http.asyncGet</code> functions.</li></ul> |

#### [doAsyncRequest](#doasyncrequest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.doAsyncRequest(url, method, data, headers, callback, [cachePolicy])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates an HTTP request and executes it asynchronously |
| **Parameters**                                       | <ul><li>url - A string containing the URL</li><li>method - A string containing the HTTP method to use (e.g. "GET", "POST", etc)</li><li>data - A string containing the request body, or nil to send no body</li><li>headers - A table containing string keys and values representing request header keys and values, or nil to add no headers</li><li>callback - A function to called when the response is received. The function should accept three arguments:</li><li>code - A number containing the HTTP response code</li><li>body - A string containing the body of the response</li><li>headers - A table containing the HTTP headers of the response</li><li>cachePolicy - An optional string containing the cache policy ("protocolCachePolicy", "ignoreLocalCache", "ignoreLocalAndRemoteCache", "returnCacheOrLoad", "returnCacheDontLoad" or "reloadRevalidatingCache"). Defaults to <code>protocolCachePolicy</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>If authentication is required in order to download the request, the required credentials must be specified as part of the URL (e.g. "http://user:password@host.com/"). If authentication fails, or credentials are missing, the connection will attempt to continue without credentials.</li><li>If the Content-Type response header begins <code>text/</code> then the response body return value is a UTF8 string. Any other content type passes the response body, unaltered, as a stream of bytes.</li></ul> |

#### [doRequest](#dorequest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.doRequest(url, method, [data, headers, cachePolicy]) -> int, string, table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates an HTTP request and executes it synchronously |
| **Parameters**                                       | <ul><li>url - A string containing the URL</li><li>method - A string containing the HTTP method to use (e.g. "GET", "POST", etc)</li><li>data - An optional string containing the data to POST to the URL, or nil to send no data</li><li>headers - An optional table of string keys and values used as headers for the request, or nil to add no headers</li><li>cachePolicy - An optional string containing the cache policy ("protocolCachePolicy", "ignoreLocalCache", "ignoreLocalAndRemoteCache", "returnCacheOrLoad", "returnCacheDontLoad" or "reloadRevalidatingCache"). Defaults to <code>protocolCachePolicy</code>.</li></ul> |
| **Returns**                                          | <ul><li>A number containing the HTTP response status code</li><li>A string containing the response body</li><li>A table containing the response headers</li></ul> |
| **Notes**                                            | <ul><li>If authentication is required in order to download the request, the required credentials must be specified as part of the URL (e.g. "http://user:password@host.com/"). If authentication fails, or credentials are missing, the connection will attempt to continue without credentials.</li></ul> |

#### [encodeForQuery](#encodeforquery)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.encodeForQuery(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a copy of the provided string in which characters that are not valid within an HTTP query key or value are escaped with their %## equivalent. |
| **Parameters**                                       | <ul><li>originalString - the string to make safe as a key or value for a query</li></ul> |
| **Returns**                                          | <ul><li>the converted string</li></ul> |
| **Notes**                                            | <ul><li>The intent of this function is to provide a valid key or a valid value for a query string, not to validate the entire query string.  For this reason, ?, =, +, and &amp; are included in the converted characters.</li></ul> |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.get(url, headers) -> int, string, table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends an HTTP GET request to a URL |
| **Parameters**                                       | <ul><li>url - A string containing the URL to retrieve</li><li>headers - A table containing string keys and values representing the request headers, or nil to add no headers</li></ul> |
| **Returns**                                          | <ul><li>A number containing the HTTP response status</li><li>A string containing the response body</li><li>A table containing the response headers</li></ul> |
| **Notes**                                            | <ul><li>If authentication is required in order to download the request, the required credentials must be specified as part of the URL (e.g. "http://user:password@host.com/"). If authentication fails, or credentials are missing, the connection will attempt to continue without credentials.</li></ul> |

#### [post](#post)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.post(url, data, headers) -> int, string, table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends an HTTP POST request to a URL |
| **Parameters**                                       | <ul><li>url - A string containing the URL to submit to</li><li>data - A string containing the request body, or nil to send no body</li><li>headers - A table containing string keys and values representing the request headers, or nil to add no headers</li></ul> |
| **Returns**                                          | <ul><li>A number containing the HTTP response status</li><li>A string containing the response body</li><li>A table containing the response headers</li></ul> |
| **Notes**                                            | <ul><li>If authentication is required in order to download the request, the required credentials must be specified as part of the URL (e.g. "http://user:password@host.com/"). If authentication fails, or credentials are missing, the connection will attempt to continue without credentials.</li></ul> |

#### [registerEntity](#registerentity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.registerEntity(entity, codepoint) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Registers an HTML Entity with the specified Unicode codepoint which can later referenced in your code as `hs.http.htmlEntity[entity]` for convenience and readability. |
| **Parameters**                                       | <ul><li>entity -- The full text of the HTML Entity as it appears in HTML encoded documents.  A proper entity starts with &amp; and ends with ; and entity labels which do not meet this will have them added -- future dereferences to get the corresponding UTF8 <em>must</em> include this initiator and terminator or they will not be recognized.</li><li>codepoint -- a Unicode codepoint in numeric or <code>U+xxxx</code> format to register with as the given entity.</li></ul> |
| **Returns**                                          | <ul><li>Returns the UTF8 byte sequence for the entity registered.</li></ul> |
| **Notes**                                            | <ul><li>If an entity label was previously registered, this will overwrite the previous value with a new one.</li><li>The return value is merely syntactic sugar and you do not need to save it locally; it can be safely ignored -- future access to the pre-converted entity should be retrieved as <code>hs.http.htmlEntities[entity]</code> in your code.  It looks good when invoked from the console, though ☺.</li></ul> |

#### [urlParts](#urlparts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.http.urlParts(url) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table of keys containing the individual components of the provided url. |
| **Parameters**                                       | <ul><li>url - the url to parse into it's individual components</li></ul> |
| **Returns**                                          | <ul><li>a table containing any of the following keys which apply to the specified url:</li><li>absoluteString           - The URL string for the URL as an absolute URL.</li><li>absoluteURL              - An absolute URL that refers to the same resource as the provided URL.</li><li>baseURL                  - the base URL, if the URL is relative</li><li>fileSystemRepresentation - the URL’s unescaped path specified as a file system path</li><li>fragment                 - the fragment, if specified in the URL</li><li>host                     - the host for the URL</li><li>isFileURL                - a boolean value indicating whether or not the URL represents a local file</li><li>lastPathComponent        - the last path component specified in the URL</li><li>parameterString          - the parameter string, if specified in the URL</li><li>password                 - the password, if specified in the URL</li><li>path                     - the unescaped path specified in the URL</li><li>pathComponents           - an array containing the path components of the URL</li><li>pathExtension            - the file extension, if specified in the URL</li><li>port                     - the port, if specified in the URL</li><li>query                    - the query, if specified in the URL</li><li>queryItems               - if the URL contains a query string, then this field contains an array of the unescaped key-value pairs for each item. Each key-value pair is represented as a table in the array to preserve order.  See notes for more information.</li><li>relativePath             - the relative path of the URL without resolving against its base URL. If the path has a trailing slash it is stripped. If the URL is already an absolute URL, this contains the same value as path.</li><li>relativeString           - a string representation of the relative portion of the URL. If the URL is already an absolute URL this contains the same value as absoluteString.</li><li>resourceSpecifier        - the resource specified in the URL</li><li>scheme                   - the scheme of the URL</li><li>standardizedURL          - the URL with any instances of ".." or "." removed from its path</li><li>user                     - the username, if specified in the URL</li></ul> |
| **Notes**                                            | <ul><li>This function assumes that the URL conforms to RFC 1808.  If the URL is malformed or does not conform to RFC1808, then many of these fields may be missing.</li></ul> |

