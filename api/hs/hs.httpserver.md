# [docs](index.md) » hs.httpserver
---

Simple HTTP server

Notes:
 * Running an HTTP server is potentially dangerous, you should seriously consider the security implications of exposing your Hammerspoon instance to a network - especially to the Internet
 * As a user of Hammerspoon, you are assumed to be highly capable, and aware of the security issues

## Submodules
 * [hs.httpserver.hsminweb](hs.httpserver.hsminweb.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [getInterface](#getinterface)
 * [getName](#getname)
 * [getPort](#getport)
 * [maxBodySize](#maxbodysize)
 * [send](#send)
 * [setCallback](#setcallback)
 * [setInterface](#setinterface)
 * [setName](#setname)
 * [setPassword](#setpassword)
 * [setPort](#setport)
 * [start](#start)
 * [stop](#stop)
 * [websocket](#websocket)

## API Documentation

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.new([ssl], [bonjour]) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new HTTP or HTTPS server                                                                                         |
| **Parameters**                                       | <ul><li>ssl     - An optional boolean. If true, the server will start using HTTPS. Defaults to false.</li></ul><ul><li>bonjour - An optional boolean. If true, the server will advertise itself with Bonjour.  Defaults to true. Note that in order to change this, you must supply a true or false value for the <code>ssl</code> argument.</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.httpserver</code> object</li></ul>            |
| **Notes**                                            | <ul><li>By default, the server will start on a random TCP port and advertise itself with Bonjour. You can check the port with <code>hs.httpserver:getPort()</code></li></ul><ul><li>By default, the server will listen on all network interfaces. You can override this with <code>hs.httpserver:setInterface()</code> before starting the server</li></ul><ul><li>Currently, in HTTPS mode, the server will use a self-signed certificate, which most browsers will warn about. If you want/need to be able to use <code>hs.httpserver</code> with a certificate signed by a trusted Certificate Authority, please file an bug on Hammerspoon requesting support for this.</li></ul>                 |

### Methods

#### [getInterface](#getinterface)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:getInterface() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the network interface the server is configured to listen on                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the network interface name, or nil if the server will listen on all interfaces</li></ul>            |

#### [getName](#getname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:getName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Bonjour name the server is configured to advertise itself as                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the Bonjour name of this server</li></ul>            |
| **Notes**                                            | <ul><li>This is not the hostname of the server, just its name in Bonjour service lists (e.g. Safari's Bonjour bookmarks menu)</li></ul>                 |

#### [getPort](#getport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:getPort() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TCP port the server is configured to listen on                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the TCP port</li></ul>            |

#### [maxBodySize](#maxbodysize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:maxBodySize([size]) -> object | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the maximum allowed body size for an incoming HTTP request.                                                                                         |
| **Parameters**                                       | <ul><li>size - An optional integer value specifying the maximum body size allowed for an incoming HTTP request in bytes.  Defaults to 10485760 (10 MB).</li></ul>   |
| **Returns**                                          | <ul><li>If a new size is specified, returns the <code>hs.httpserver</code> object; otherwise the current value.</li></ul>            |
| **Notes**                                            | <ul><li>Because the Hammerspoon http server processes incoming requests completely in memory, this method puts a limit on the maximum size for a POST or PUT request.</li></ul>                 |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:send(message) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends a message to the websocket client                                                                                         |
| **Parameters**                                       | <ul><li>message - A string containing the message to send</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.httpserver</code> object</li></ul>            |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:setCallback([callback]) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the request handling callback for an HTTP server object                                                                                         |
| **Parameters**                                       | <ul><li>callback - An optional function that will be called to process each incoming HTTP request, or nil to remove an existing callback. See the notes section below for more information about this callback</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.httpserver</code> object</li></ul>            |
| **Notes**                                            | <ul><li>The callback will be passed four arguments:</li></ul><ul><li>A string containing the type of request (i.e. <code>GET</code>/<code>POST</code>/<code>DELETE</code>/etc)</li></ul><ul><li>A string containing the path element of the request (e.g. <code>/index.html</code>)</li></ul><ul><li>A table containing the request headers</li></ul><ul><li>A string containing the raw contents of the request body, or the empty string if no body is included in the request.</li></ul><ul><li>The callback <em>must</em> return three values:</li></ul><ul><li>A string containing the body of the response</li></ul><ul><li>An integer containing the response code (e.g. 200 for a successful request)</li></ul><ul><li>A table containing additional HTTP headers to set (or an empty table, <code>{}</code>, if no extra headers are required)</li></ul>                 |

#### [setInterface](#setinterface)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:setInterface(interface) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the network interface the server is configured to listen on                                                                                         |
| **Parameters**                                       | <ul><li>interface - A string containing an interface name</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.httpserver</code> object</li></ul>            |
| **Notes**                                            | <ul><li>As well as real interface names (e.g. <code>en0</code>) the following values are valid:</li></ul><ul><li>An IP address of one of your interfaces</li></ul><ul><li>localhost</li></ul><ul><li>loopback</li></ul><ul><li>nil (which means all interfaces, and is the default)</li></ul>                 |

#### [setName](#setname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:setName(name) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the Bonjour name the server should advertise itself as                                                                                         |
| **Parameters**                                       | <ul><li>name - A string containing the Bonjour name for the server</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.httpserver</code> object</li></ul>            |
| **Notes**                                            | <ul><li>This is not the hostname of the server, just its name in Bonjour service lists (e.g. Safari's Bonjour bookmarks menu)</li></ul>                 |

#### [setPassword](#setpassword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:setPassword([password]) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets a password for an HTTP server object                                                                                         |
| **Parameters**                                       | <ul><li>password - An optional string that contains the server password, or nil to remove an existing password</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.httpserver</code> object</li></ul>            |
| **Notes**                                            | <ul><li>It is not currently possible to set multiple passwords for different users, or passwords only on specific paths</li></ul>                 |

#### [setPort](#setport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:setPort(port) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the TCP port the server is configured to listen on                                                                                         |
| **Parameters**                                       | <ul><li>port - An integer containing a TCP port to listen on</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.httpserver</code> object</li></ul>            |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:start() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts an HTTP server object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.httpserver</code> object</li></ul>            |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:stop() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops an HTTP server object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.httpserver</code> object</li></ul>            |

#### [websocket](#websocket)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver:websocket(path, callback) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables a websocket endpoint on the HTTP server                                                                                         |
| **Parameters**                                       | <ul><li>path - A string containing the websocket path such as '/ws'</li></ul><ul><li>callback - A function returning a string for each recieved websocket message</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.httpserver</code> object</li></ul>            |
| **Notes**                                            | <ul><li>The callback is passed one string parameter containing the received message</li></ul><ul><li>The callback must return a string containing the response message</li></ul><ul><li>Given a path '/mysock' and a port of 8000, the websocket URL is as follows:</li></ul><ul><li>ws://localhost:8000/mysock</li></ul><ul><li>wss://localhost:8000/mysock (if SSL enabled)</li></ul>                 |

