# [docs](index.md) » hs.httpserver.hsminweb
---

Minimalist Web Server for Hammerspoon

This module aims to be a minimal, but (mostly) standards-compliant web server for use within Hammerspoon.  Expanding upon the Hammerspoon module, `hs.httpserver`, this module adds support for serving static pages stored at a specified document root as well as serving dynamic content from Lua Template Files interpreted within the Hammerspoon environment and external executables which support the CGI/1.1 framework.

This module aims to provide a fully functional, and somewhat extendable, web server foundation, but will never replace a true dedicated web server application.  Some limitations include:
 * It is single threaded within the Hammerspoon environment and can only serve one resource at a time
 * As with all Hammerspoon modules, while dynamic content is being generated, Hammerspoon cannot respond to other callback functions -- a complex or time consuming script may block other Hammerspoon activity in a noticeable manner.
 * All document requests and responses are handled in memory only -- because of this, maximum resource size is limited to what you are willing to allow Hammerspoon to consume and memory limitations of your computer.

While some of these limitations may be mitigated to an extent in the future with additional modules and additions to `hs.httpserver`, Hammerspoon's web serving capabilities will never replace a dedicated web server when volume or speed is required.

An example web site is provided in the `hsdocs` folder of the `hs.doc` module.  This web site can serve documentation for Hammerspoon dynamically generated from the json file included with the Hammerspoon application for internal documentation.  It serves as a basic example of what is possible with this module.

You can start this web server by typing the following into your Hammerspoon console:
`require("hs.doc.hsdocs").start()` and then visiting `http://localhost:12345/` with your web browser.

## Submodules
 * [hs.httpserver.hsminweb.cgilua](hs.httpserver.hsminweb.cgilua.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [dateFormatString](#dateformatstring)
 * [statusCodes](#statuscodes)
* Variables - Configurable values
 * [_accessLog](#_accesslog)
 * [_errorHandlers](#_errorhandlers)
 * [_serverAdmin](#_serveradmin)
 * [_supportMethods](#_supportmethods)
 * [log](#log)
* Functions - API calls offered directly by the extension
 * [formattedDate](#formatteddate)
 * [urlParts](#urlparts)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [accessList](#accesslist)
 * [allowDirectory](#allowdirectory)
 * [bonjour](#bonjour)
 * [cgiEnabled](#cgienabled)
 * [cgiExtensions](#cgiextensions)
 * [directoryIndex](#directoryindex)
 * [dnsLookup](#dnslookup)
 * [documentRoot](#documentroot)
 * [interface](#interface)
 * [luaTemplateExtension](#luatemplateextension)
 * [maxBodySize](#maxbodysize)
 * [name](#name)
 * [password](#password)
 * [port](#port)
 * [queryLogging](#querylogging)
 * [scriptTimeout](#scripttimeout)
 * [ssl](#ssl)
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constants

#### [dateFormatString](#dateformatstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.dateFormatString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A format string, usable with `os.date`, which will display a date in the format expected for HTTP communications as described in RFC 822, updated by RFC 1123. |

#### [statusCodes](#statuscodes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.statusCodes` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | HTTP Response Status Codes |
| **Notes**                                            | <ul><li>The keys and labels in this table have been combined from a variety of sources including, but not limited to:   * "Official" list at https://en.wikipedia.org/wiki/List_of_HTTP_status_codes   * KeplerProject's wsapi at https://github.com/keplerproject/wsapi   * IIS additions from https://support.microsoft.com/en-us/kb/943891 * This table has metatable additions which allow you to review its contents from the Hammerspoon console by typing <code>hs.httpserver.hsminweb.statusCodes</code></li></ul> |

### Variables

#### [_accessLog](#_accesslog)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb._accessLog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Accessed as `self._accessLog`.  If query logging is enabled for the web server, an Apache style common log entry will be appended to this string for each request.  See [hs.httpserver.hsminweb:queryLogging](#queryLogging). |

#### [_errorHandlers](#_errorhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb._errorHandlers` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Accessed as `self._errorHandlers[errorCode]`.  A table whose keyed entries specify the function to generate the error response page for an HTTP error. |

#### [_serverAdmin](#_serveradmin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb._serverAdmin` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Accessed as `self._serverAdmin`.  A string containing the administrator for the web server.  Defaults to the currently logged in user's short form username and the computer's localized name as returned by `hs.host.localizedName()` (e.g. "user@computer"). |

#### [_supportMethods](#_supportmethods)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb._supportMethods` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Accessed as `self._supportMethods[method]`.  A table whose keyed entries specify whether or not a specified HTTP method is supported by this server. |

#### [log](#log)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.log` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The `hs.logger` instance for the `hs.httpserver.hsminweb` module. See the documentation for `hs.logger` for more information. |

### Functions

#### [formattedDate](#formatteddate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.formattedDate([date]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the current or specified time in the format expected for HTTP communications as described in RFC 822, updated by RFC 1123. |
| **Parameters**                                       | <ul><li>date - an optional integer specifying the date as the number of seconds since 00:00:00 UTC on 1 January 1970.  Defaults to the current time as returned by <code>os.time()</code></li></ul> |
| **Returns**                                          | <ul><li>the time indicated as a string in the format expected for HTTP communications as described in RFC 822, updated by RFC 1123.</li></ul> |

#### [urlParts](#urlparts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.urlParts(url) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Parse the specified URL into it's constituant parts. |
| **Parameters**                                       | <ul><li>url - the url to parse</li></ul> |
| **Returns**                                          | <ul><li>a table containing the constituant parts of the provided url.  The table will contain one or more of the following key-value pairs:   * fragment           - the anchor name a URL refers to within an HTML document.  Appears after '#' at the end of a URL.  Note that not all web clients include this in an HTTP request since its normal purpose is to indicate where to scroll to within a page after the content has been retrieved.   * host               - the host name portion of the URL, if any   * lastPathComponent  - the last component of the path portion of the URL   * password           - the password specified in the URL.  Note that this is not the password that would be entered when using Basic or Digest authentication; rather it is a password included in the URL itself -- for security reasons, use of this field has been deprecated in most situations and modern browsers will often prompt for confirmation before allowing URL's which contain a password to be transmitted.   * path               - the full path specified in the URL   * pathComponents     - an array containing the path components as individual strings.  Components which specify a sub-directory of the path will end with a "/" character.   * pathExtension      - if the final component of the path refers to a file, the file's extension, if any.   * port               - the port specified in the URL, if any   * query              - the portion of the URL after a '?' character, if any; used to contain query information often from a form submitting it's input with the GET method.   * resourceSpecifier  - the portion of the URL after the scheme   * scheme             - the URL scheme; for web traffic, this will be "http" or "https"   * standardizedURL    - the URL with any path components of ".." or "." normalized.  The use of ".." that would cause the URL to refer to something preceding its root is simply removed.   * URL                - the URL as it was provided to this function (no changes)   * user               - the user name specified in the URL.  Note that this is not the user name that would be entered when using Basic or Digest authentication; rather it is a user name included in the URL itself -- for security reasons, use of this field has been deprecated in most situations and modern browsers will often prompt for confirmation before allowing URL's which contain a user name to be transmitted.</li></ul> |
| **Notes**                                            | <ul><li>This function differs from the similar function <code>hs.http.urlParts</code> in a few ways:   * To simplify the logic used by this module to determine if a request for a directory is properly terminated with a "/", the path components returned by this function do not remove this character from the component, if present.   * Some extraneous or duplicate keys have been removed.   * This function is patterned after RFC 3986 while <code>hs.http.urlParts</code> uses OS X API functions which are patterned after RFC 1808. RFC 3986 obsoletes 1808.  The primary distinction that affects this module is in regards to <code>parameters</code> for path components in the URI -- RFC 3986 disallows them in schema based URI's (like the URL's that are used for web based traffic).</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.new([documentRoot]) -> hsminwebTable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Create a new hsminweb table object representing a Hammerspoon Web Server. |
| **Parameters**                                       | <ul><li>documentRoot - an optional string specifying the document root for the new web server.  Defaults to the Hammerspoon users <code>Sites</code> sub-directory (i.e. <code>os.getenv("HOME").."/Sites"</code>).</li></ul> |
| **Returns**                                          | <ul><li>a table representing the hsminweb object.</li></ul> |
| **Notes**                                            | <ul><li>a web server's document root is the directory which contains the documents or files to be served by the web server. * while an hs.minweb object is actually represented by a Lua table, it has been assigned a meta-table which allows methods to be called directly on it like a user-data object.  For most purposes, you should think of this table as the module's userdata.</li></ul> |

### Methods

#### [accessList](#accesslist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:accessList([table]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the access-list table for the hsminweb web server |
| **Parameters**                                       | <ul><li>table - an optional table or <code>nil</code> containing the access list for the web server, default <code>nil</code>.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>The access-list feature works by comparing the request headers against a list of tests which either accept or reject the request.  If no access list is set (i.e. it is assigned a value of <code>nil</code>), then all requests are served.  If a table is passed into this method, then any request which is not explicitly accepted by one of the tests provided is rejected (i.e. there is an implicit "reject" at the end of the list). * The access-list table is a list of tests which are evaluated in order.  The first test which matches a given request determines whether or not the request is accepted or rejected. * Each entry in the access-list table is also a table with the following format:   * { 'header', 'value', isPattern, isAccepted }     * header     - a string value matching the name of a header.  While the header name must match exactly, the comparison is case-insensitive (i.e. "X-Remote-addr" and "x-remote-addr" will both match the actual header name used, which is "X-Remote-Addr").     * value      - a string value specifying the value to compare the header key's value to.     * isPattern  - a boolean indicating whether or not the header key's value should be compared to <code>value</code> as a pattern match (true) -- see Lua documentation 6.4.1, <code>help.lua._man._6_4_1</code> in the console, or as an exact match (false)     * isAccepted - a boolean indicating whether or not a match should be accepted (true) or rejected (false)   * A special entry of the form { '*', '*', '*', true } accepts all further requests and can be used as the final entry if you wish for the access list to function as a list of requests to reject, but to accept any requests which do not match a previous test.   * A special entry of the form { '*', '*', '*', false } rejects all further requests and can be used as the final entry if you wish for the access list to function as a list of requests to accept, but to reject any requests which do not match a previous test.  This is the implicit "default" final test if a table is assigned with the access-list method and does not actually need to be specified, but is included for completeness.   * Note that any entry after an entry in which the first two parameters are equal to '*' will never actually be used.</li></ul> |

#### [allowDirectory](#allowdirectory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:allowDirectory([flag]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the whether or not a directory index is returned when the requested URL specifies a directory and no file matching an entry in the directory indexes table is found. |
| **Parameters**                                       | <ul><li>flag - an optional boolean, defaults to false, indicating whether or not a directory index can be returned when a default file cannot be located.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>if this value is false, then an attempt to retrieve a URL specifying a directory that does not contain a default file as identified by one of the entries in the <a href="#directoryIndex">hs.httpserver.hsminweb:directoryIndex</a> list will result in a "403.2" error.</li></ul> |

#### [bonjour](#bonjour)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:bonjour([flag]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the whether or not the web server should advertise itself via Bonjour when it is running. |
| **Parameters**                                       | <ul><li>flag - an optional boolean, defaults to true, indicating whether or not the server should advertise itself via Bonjour when it is running.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>this flag can only be changed when the server is not running (i.e. the <a href="#start">hs.httpserver.hsminweb:start</a> method has not yet been called, or the <a href="#stop">hs.httpserver.hsminweb:stop</a> method is called first.)</li></ul> |

#### [cgiEnabled](#cgienabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:cgiEnabled([flag]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the whether or not CGI file execution is enabled. |
| **Parameters**                                       | <ul><li>flag - an optional boolean, defaults to false, indicating whether or not CGI script execution is enabled for the web server.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |

#### [cgiExtensions](#cgiextensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:cgiExtensions([table]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the file extensions which identify files which should be executed as CGI scripts to provide the results to an HTTP request. |
| **Parameters**                                       | <ul><li>table - an optional table or <code>nil</code>, defaults to <code>{ "cgi", "pl" }</code>, specifying a list of file extensions which indicate that a file should be executed as CGI scripts to provide the content for an HTTP request.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>this list is ignored if <a href="#cgiEnabled">hs.httpserver.hsminweb:cgiEnabled</a> is not also set to true.</li></ul> |

#### [directoryIndex](#directoryindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:directoryIndex([table]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the file names to look for when the requested URL specifies a directory. |
| **Parameters**                                       | <ul><li>table - an optional table or <code>nil</code>, defaults to <code>{ "index.html", "index.htm" }</code>, specifying a list of file names to look for when the requested URL specifies a directory.  If a file with one of the names is found in the directory, this file is served instead of the directory.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>Files listed in this table are checked in order, so the first matched is served.  If no file match occurs, then the server will return a generated list of the files in the directory, or a "403.2" error, depending upon the value controlled by <a href="#allowDirectory">hs.httpserver.hsminweb:allowDirectory</a>.</li></ul> |

#### [dnsLookup](#dnslookup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:dnsLookup([flag]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the whether or not DNS lookups are performed. |
| **Parameters**                                       | <ul><li>flag - an optional boolean, defaults to false, indicating whether or not DNS lookups are performed.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>DNS lookups can be time consuming or even block Hammerspoon for a short time, so they are disabled by default. * Currently DNS lookups are (optionally) performed for CGI scripts, but may be added for other purposes in the future (logging, etc.).</li></ul> |

#### [documentRoot](#documentroot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:documentRoot([path]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the document root for the web server. |
| **Parameters**                                       | <ul><li>path - an optional string, default <code>os.getenv("HOME") .. "/Sites"</code>, specifying where documents for the web server should be served from.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |

#### [interface](#interface)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:interface([interface]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the network interface that the hsminweb web server will listen on |
| **Parameters**                                       | <ul><li>interface - an optional string, or nil, specifying the network interface the web server will listen on.  An explicit nil specifies that the web server should listen on all active interfaces for the machine.  Defaults to nil.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>See <code>hs.httpserver.setInterface</code> for a description of valid values that can be specified as the <code>interface</code> argument to this method. * the interface can only be specified before the hsminweb web server has been started.  If you wish to change the listening interface for a running web server, you must stop it with <a href="#stop">hs.httpserver.hsminweb:stop</a> before invoking this method and then restart it with <a href="#start">hs.httpserver.hsminweb:start</a>.</li></ul> |

#### [luaTemplateExtension](#luatemplateextension)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:luaTemplateExtension([string]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the extension of files which contain Lua code which should be executed within Hammerspoon to provide the results to an HTTP request. |
| **Parameters**                                       | <ul><li>string - an optional string or <code>nil</code>, defaults to <code>nil</code>, specifying the file extension which indicates that a file should be executed as Lua code within the Hammerspoon environment to provide the content for an HTTP request.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>This extension is checked after the extensions given to <a href="#cgiExtensions">hs.httpserver.hsminweb:cgiExtensions</a>; this means that if the same extension set by this method is also in the CGI extensions list, then the file will be interpreted as a CGI script and ignore this setting.</li></ul> |

#### [maxBodySize](#maxbodysize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:maxBodySize([size]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the maximum body size for an HTTP request |
| **Parameters**                                       | <ul><li>size - An optional integer value specifying the maximum body size allowed for an incoming HTTP request in bytes.  Defaults to 10485760 (10 MB).</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>Because the Hammerspoon http server processes incoming requests completely in memory, this method puts a limit on the maximum size for a POST or PUT request. * If the request body excedes this size, <code>hs.httpserver</code> will respond with a status code of 405 for the method before this module ever receives the request.</li></ul> |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:name([name]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the name the web server uses in Bonjour advertisement when the web server is running. |
| **Parameters**                                       | <ul><li>name - an optional string specifying the name the server advertises itself as when Bonjour is enabled and the web server is running.  Defaults to <code>nil</code>, which causes the server to be advertised with the computer's name as defined in the Sharing preferences panel for the computer.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |

#### [password](#password)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:password([password]) -> hsminwebTable | boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Set a password for the hsminweb web server, or return a boolean indicating whether or not a password is currently set for the web server. |
| **Parameters**                                       | <ul><li>password - An optional string that contains the server password, or an explicit <code>nil</code> to remove an existing password.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or a boolean indicathing whether or not a password has been set if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>the password, if set, is server wide and causes the server to use the Basic authentication scheme with an empty string for the username. * this module is an extension to the Hammerspoon core module <code>hs.httpserver</code>, so it has the same limitations regarding server passwords. See the documentation for <code>hs.httpserver.setPassword</code> (<code>help.hs.httpserver.setPassword</code> in the Hammerspoon console).</li></ul> |

#### [port](#port)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:port([port]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the name the port the web server listens on |
| **Parameters**                                       | <ul><li>port - an optional integer specifying the TCP port the server listens for requests on when it is running.  Defaults to <code>nil</code>, which causes the server to randomly choose a port when it is started.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>due to security restrictions enforced by OS X, the port must be a number greater than 1023</li></ul> |

#### [queryLogging](#querylogging)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:queryLogging([flag]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the whether or not requests to this web server are logged. |
| **Parameters**                                       | <ul><li>flag - an optional boolean, defaults to false, indicating whether or not query requests are logged.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>If logging is enabled, an Apache common style log entry is appended to <a href="#_accessLog">self._accesslog</a> for each request made to the web server. * Error messages during content generation are always logged to the Hammerspoon console via the <code>hs.logger</code> instance saved to <a href="#log">hs.httpserver.hsminweb.log</a>.</li></ul> |

#### [scriptTimeout](#scripttimeout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:scriptTimeout([integer]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the timeout for a CGI script |
| **Parameters**                                       | <ul><li>integer - an optional integer, defaults to 30, specifying the length of time in seconds a CGI script should be allowed to run before being forcibly terminated if it has not yet completed its task.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>With the current functionality available in <code>hs.httpserver</code>, any script which is expected to return content for an HTTP request must run in a blocking manner -- this means that no other Hammerspoon activity can be occurring while the script is executing.  This parameter lets you set the maximum amount of time such a script can hold things up before being terminated. * An alternative implementation of at least some of the methods available in <code>hs.httpserver</code> is being considered which may make it possible to use <code>hs.task</code> for these scripts, which would alleviate this blocking behavior.  However, even if this is addressed, a timeout for scripts is still desirable so that a client making a request doesn't sit around waiting forever if a script is malformed.</li></ul> |

#### [ssl](#ssl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:ssl([flag]) -> hsminwebTable | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the whether or not the web server utilizes SSL for HTTP request and response communications. |
| **Parameters**                                       | <ul><li>flag - an optional boolean, defaults to false, indicating whether or not the server utilizes SSL for HTTP request and response traffic.</li></ul> |
| **Returns**                                          | <ul><li>the hsminwebTable object if a parameter is provided, or the current value if no parameter is specified.</li></ul> |
| **Notes**                                            | <ul><li>this flag can only be changed when the server is not running (i.e. the <a href="#start">hs.httpserver.hsminweb:start</a> method has not yet been called, or the <a href="#stop">hs.httpserver.hsminweb:stop</a> method is called first.) * this module is an extension to the Hammerspoon core module <code>hs.httpserver</code>, so it has the same considerations regarding SSL. See the documentation for <code>hs.httpserver.new</code> (<code>help.hs.httpserver.new</code> in the Hammerspoon console).</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:start() -> hsminwebTable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Start serving pages for the hsminweb web server. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the hsminWebTable object</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb:stop() -> hsminwebTable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stop serving pages for the hsminweb web server. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the hsminWebTable object</li></ul> |
| **Notes**                                            | <ul><li>this method is called automatically during garbage collection.</li></ul> |

