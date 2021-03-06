# [docs](index.md) » hs.socket
---

Talk to custom protocols using asynchronous TCP sockets

For UDP sockets see [`hs.socket.udp`](./hs.socket.udp.html)

`hs.socket` is implemented with [CocoaAsyncSocket](https://github.com/robbiehanson/CocoaAsyncSocket). CocoaAsyncSocket's [tagging features](https://github.com/robbiehanson/CocoaAsyncSocket/wiki/Intro_GCDAsyncSocket#reading--writing) provide a handy way to implement custom protocols.

For example, you can easily implement a basic HTTP client as follows (though using [`hs.http`](./hs.http.html) is recommended for the real world):

<pre style="font-size:10px">
local TAG_HTTP_HEADER, TAG_HTTP_CONTENT = 1, 2
local body = ""
local function httpCallback(data, tag)
  if tag == TAG_HTTP_HEADER then
    print(tag, "TAG_HTTP_HEADER"); print(data)
    local contentLength = data:match("\r\nContent%-Length: (%d+)\r\n")
    client:read(tonumber(contentLength), TAG_HTTP_CONTENT)
  elseif tag == TAG_HTTP_CONTENT then
    print(tag, "TAG_HTTP_CONTENT"); print(data)
    body = data
  end
end

client = hs.socket.new(httpCallback):connect("google.com", 80)
client:write("GET /index.html HTTP/1.0\r\nHost: google.com\r\n\r\n")
client:read("\r\n\r\n", TAG_HTTP_HEADER)
</pre>

Resulting in the following console output (adjust log verbosity with `hs.socket.setLogLevel()`) :

<pre style="font-size:10px">
            LuaSkin: (secondary thread): TCP socket connected
            LuaSkin: (secondary thread): Data written to TCP socket
            LuaSkin: (secondary thread): Data read from TCP socket
1 TAG_HTTP_HEADER
HTTP/1.0 301 Moved Permanently
Location: http://www.google.com/index.html
Content-Type: text/html; charset=UTF-8
Date: Thu, 03 Mar 2016 08:38:02 GMT
Expires: Sat, 02 Apr 2016 08:38:02 GMT
Cache-Control: public, max-age=2592000
Server: gws
Content-Length: 229
X-XSS-Protection: 1; mode=block
X-Frame-Options: SAMEORIGIN

            LuaSkin: (secondary thread): Data read from TCP socket
2 TAG_HTTP_CONTENT
&lt;HTML&gt;&lt;HEAD&gt;&lt;meta http-equiv=&quot;content-type&quot; content=&quot;text/html;charset=utf-8&quot;&gt;
&lt;TITLE&gt;301 Moved&lt;/TITLE&gt;&lt;/HEAD&gt;&lt;BODY&gt;
&lt;H1&gt;301 Moved&lt;/H1&gt;
The document has moved
&lt;A HREF=&quot;http://www.google.com/index.html&quot;&gt;here&lt;/A&gt;.
&lt;/BODY&gt;&lt;/HTML&gt;
            LuaSkin: (secondary thread): TCP socket disconnected Socket closed by remote peer
</pre>



## Submodules
 * [hs.socket.udp](hs.socket.udp.md)

## API Overview
* Variables - Configurable values
 * [timeout](#timeout)
* Functions - API calls offered directly by the extension
 * [parseAddress](#parseaddress)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [server](#server)
* Methods - API calls which can only be made on an object returned by a constructor
 * [connect](#connect)
 * [connected](#connected)
 * [connections](#connections)
 * [disconnect](#disconnect)
 * [info](#info)
 * [listen](#listen)
 * [read](#read)
 * [receive](#receive)
 * [send](#send)
 * [setCallback](#setcallback)
 * [setTimeout](#settimeout)
 * [startTLS](#starttls)
 * [write](#write)

## API Documentation

### Variables

#### [timeout](#timeout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.timeout` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Timeout for the socket operations, in seconds. New [`hs.socket`](#new) objects will be created with this timeout value, but can individually change it with the [`setTimeout`](#setTimeout) method |

### Functions

#### [parseAddress](#parseaddress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.parseAddress(sockaddr) -> table or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Parses a binary socket address structure into a readable table |
| **Parameters**                                       | <ul><li>sockaddr - A binary socket address structure, usually obtained from the <a href="#info"><code>info</code></a> method or in <a href="./hs.socket.udp.html"><code>hs.socket.udp</code></a>'s <a href="./hs.socket.udp.html#setCallback">read callback</a></li></ul> |
| **Returns**                                          | <ul><li>A table describing the address with the following keys or <code>nil</code>:</li><li>host - A string containing the host IP</li><li>port - A number containing the port</li><li>addressFamily - A number containing the address family</li></ul> |
| **Notes**                                            | <ul><li>Some address family definitions from <code>&lt;sys/socket.h&gt;</code>:</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.new([fn]) -> hs.socket object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an unconnected asynchronous TCP socket object |
| **Parameters**                                       | <ul><li>fn - An optional <a href="#setCallback">callback function</a> for reading data from the socket, settable here for convenience</li></ul> |
| **Returns**                                          | <ul><li>An <a href="#new"><code>hs.socket</code></a> object</li></ul> |

#### [server](#server)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.server(port|path[, fn]) -> hs.socket object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates and binds an [`hs.socket`](#new) instance to a port or path (Unix domain socket) for listening |
| **Parameters**                                       | <ul><li>port - A port number [0-65535]. Ports [1-1023] are privileged. Port 0 allows the OS to select any available port</li><li>path - A string containing the path to the Unix domain socket</li><li>fn - An optional <a href="#setCallback">callback function</a> for reading data from the socket, settable here for convenience</li></ul> |
| **Returns**                                          | <ul><li>An <a href="#new"><code>hs.socket</code></a> object</li></ul> |

### Methods

#### [connect](#connect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:connect({host, port}|path[, fn]) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Connects an unconnected [`hs.socket`](#new) instance |
| **Parameters**                                       | <ul><li>host - A string containing the hostname or IP address</li><li>port - A port number [1-65535]</li><li>path - A string containing the path to the Unix domain socket</li><li>fn - An optional single-use callback function to execute after establishing the connection. Receives no parameters</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket</code></a> object or <code>nil</code> if an error occurred</li></ul> |
| **Notes**                                            | <ul><li>Either a host/port pair OR a Unix domain socket path must be supplied. If no port is passed, the first param is assumed to be a path to the socket file</li></ul> |

#### [connected](#connected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:connected() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the connection status of the [`hs.socket`](#new) instance |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if connected, otherwise <code>false</code></li></ul> |

#### [connections](#connections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:connections() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the number of connections to the socket, which is at most 1 for default (non-listening) sockets |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The number of connections to the socket</li></ul> |

#### [disconnect](#disconnect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:disconnect() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Disconnects the [`hs.socket`](#new) instance, freeing it for reuse |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket</code></a> object</li></ul> |
| **Notes**                                            | <ul><li>If called on a listening socket with multiple connections, each client is disconnected</li></ul> |

#### [info](#info)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:info() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns information on the [`hs.socket`](#new) instance |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the following keys:</li><li>connectedAddress - <code>string</code> (<code>sockaddr</code> struct)</li><li>connectedHost - <code>string</code></li><li>connectedPort - <code>number</code></li><li>connectedURL - <code>string</code></li><li>connections - <code>number</code></li><li>isConnected - <code>boolean</code></li><li>isDisconnected - <code>boolean</code></li><li>isIPv4 - <code>boolean</code></li><li>isIPv4Enabled - <code>boolean</code></li><li>isIPv4PreferredOverIPv6 - <code>boolean</code></li><li>isIPv6 - <code>boolean</code></li><li>isIPv6Enabled - <code>boolean</code></li><li>isSecure - <code>boolean</code></li><li>localAddress - <code>string</code> (<code>sockaddr</code> struct)</li><li>localHost - <code>string</code></li><li>localPort - <code>number</code></li><li>timeout - <code>number</code></li><li>unixSocketPath - <code>string</code></li><li>userData - <code>string</code></li></ul> |

#### [listen](#listen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:listen(port|path) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Binds an unconnected [`hs.socket`](#new) instance to a port or path (Unix domain socket) for listening |
| **Parameters**                                       | <ul><li>port - A port number [0-65535]. Ports [1-1023] are privileged. Port 0 allows the OS to select any available port</li><li>path - A string containing the path to the Unix domain socket</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket</code></a> object or <code>nil</code> if an error occurred</li></ul> |

#### [read](#read)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:read(delimiter[, tag]) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Read data from the socket. Results are passed to the [callback function](#setCallback), which must be set to use this method |
| **Parameters**                                       | <ul><li>delimiter - Either a number of bytes to read, or a string delimiter such as "&#92;n" or "&#92;r&#92;n". Data is read up to and including the delimiter</li><li>tag - An optional integer to assist with labeling reads. It is passed to the callback to assist with implementing <a href="https://github.com/robbiehanson/CocoaAsyncSocket/wiki/Intro_GCDAsyncSocket#reading--writing">state machines</a> for processing complex protocols</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket</code></a> object or <code>nil</code> if an error occured</li></ul> |
| **Notes**                                            | <ul><li>If called on a listening socket with multiple connections, data is read from each of them</li></ul> |

#### [receive](#receive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:receive(delimiter[, tag]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Alias for [`hs.socket:read`](#read) |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:send(message[, tag]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Alias for [`hs.socket:write`](#write) |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:setCallback([fn]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the read callback for the [`hs.socket`](#new) instance. Must be set to read data from the socket |
| **Parameters**                                       | <ul><li>fn - An optional callback function to process data read from the socket. <code>nil</code> or no argument clears the callback</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket</code></a> object</li></ul> |

#### [setTimeout](#settimeout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:setTimeout(timeout) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the timeout for the socket operations. If the timeout value is negative, the operations will not use a timeout, which is the default |
| **Parameters**                                       | <ul><li>timeout - A number containing the timeout duration, in seconds</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket</code></a> object</li></ul> |

#### [startTLS](#starttls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:startTLS([verify][, peerName]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Secures the socket with TLS. The socket will disconnect immediately if TLS negotiation fails |
| **Parameters**                                       | <ul><li>verify - An optional boolean that, if <code>false</code>, allows TLS handshaking with servers with self-signed certificates and does not evaluate the chain of trust. Defaults to <code>true</code> and omitted if <code>peerName</code> is supplied</li><li>peerName - An optional string containing the fully qualified domain name of the peer to validate against — for example, <code>store.apple.com</code>. It should match the name in the X.509 certificate given by the remote party. See notes below</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket</code></a> object</li></ul> |
| **Notes**                                            | <ul><li>IMPORTANT SECURITY NOTE:The default settings will check to make sure the remote party's certificate is signed by atrusted 3rd party certificate agency (e.g. verisign) and that the certificate is not expired.However it will not verify the name on the certificate unless yougive it a name to verify against via <code>peerName</code>.The security implications of this are important to understand.Imagine you are attempting to create a secure connection to MySecureServer.com,but your socket gets directed to MaliciousServer.com because of a hacked DNS server.If you simply use the default settings, and MaliciousServer.com has a valid certificate,the default settings will not detect any problems since the certificate is valid.To properly secure your connection in this particular scenario youshould set <code>peerName</code> to "MySecureServer.com".</li></ul> |

#### [write](#write)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket:write(message[, tag][, fn]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Write data to the socket |
| **Parameters**                                       | <ul><li>message - A string containing data to be sent on the socket</li><li>tag - An optional integer to assist with labeling writes</li><li>fn - An optional single-use callback function to execute after writing data to the socket. Receives the tag parameter</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket</code></a> object</li></ul> |
| **Notes**                                            | <ul><li>If called on a listening socket with multiple connections, data is broadcasted to all connected sockets</li></ul> |

