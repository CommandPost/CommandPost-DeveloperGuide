# [docs](index.md) » hs.socket.udp
---

Talk to custom protocols using asynchronous UDP sockets

For TCP sockets see [`hs.socket`](./hs.socket.html)

You can do a lot of neat trivial and non-trivial things with these. A simple ping ponger:
<pre style="font-size:10px">
function ping(data, addr)
  print(data)
  addr = hs.socket.parseAddress(addr)
  hs.timer.doAfter(1, function()
    client:send("ping", addr.host, addr.port)
  end)
end

function pong(data, addr)
  print(data)
  addr = hs.socket.parseAddress(addr)
  hs.timer.doAfter(1, function()
    server:send("pong", addr.host, addr.port)
  end)
end

server = hs.socket.udp.server(9001, pong):receive()
client = hs.socket.udp.new(ping):send("ping", "localhost", 9001):receive()
</pre>
Resulting in the following endless exchange:
<pre style="font-size:10px">
20:26:56    LuaSkin: (secondary thread): Data written to UDP socket
            LuaSkin: (secondary thread): Data read from UDP socket
ping
20:26:57    LuaSkin: (secondary thread): Data written to UDP socket
            LuaSkin: (secondary thread): Data read from UDP socket
pong
20:26:58    LuaSkin: (secondary thread): Data written to UDP socket
            LuaSkin: (secondary thread): Data read from UDP socket
ping
20:26:59    LuaSkin: (secondary thread): Data written to UDP socket
            LuaSkin: (secondary thread): Data read from UDP socket
pong
...
</pre>

You can do some silly things with a callback factory and enabling broadcasting:
<pre style="font-size:10px">
local function callbackMaker(name)
  local fun = function(data, addr)
    addr = hs.socket.parseAddress(addr)
    print(name.." received data:\n"..data.."\nfrom host: "..addr.host.." port: "..addr.port)
  end
  return fun
end

local listeners = {}
local port = 9001

for i=1,3 do
  table.insert(listeners, hs.socket.udp.new(callbackMaker("listener "..i)):reusePort():listen(port):receive())
end

broadcaster = hs.socket.udp.new():broadcast()
broadcaster:send("hello!", "255.255.255.255", port)
</pre>
Since neither IPv4 nor IPv6 have been disabled, the broadcast is received on both protocols ('dual-stack' IPv6 addresses shown):
<pre style="font-size:10px">
listener 2 received data:
hello!
from host: ::ffff:192.168.0.3 port: 53057
listener 1 received data:
hello!
from host: ::ffff:192.168.0.3 port: 53057
listener 3 received data:
hello!
from host: ::ffff:192.168.0.3 port: 53057
listener 1 received data:
hello!
from host: 192.168.0.3 port: 53057
listener 3 received data:
hello!
from host: 192.168.0.3 port: 53057
listener 2 received data:
hello!
from host: 192.168.0.3 port: 53057
</pre>


## API Overview
* Variables - Configurable values
 * [timeout](#timeout)
* Functions - API calls offered directly by the extension
 * [parseAddress](#parseaddress)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [server](#server)
* Methods - API calls which can only be made on an object returned by a constructor
 * [broadcast](#broadcast)
 * [close](#close)
 * [closed](#closed)
 * [connect](#connect)
 * [connected](#connected)
 * [enableIPv](#enableipv)
 * [info](#info)
 * [listen](#listen)
 * [pause](#pause)
 * [preferIPv](#preferipv)
 * [read](#read)
 * [readOne](#readone)
 * [receive](#receive)
 * [receiveOne](#receiveone)
 * [reusePort](#reuseport)
 * [send](#send)
 * [setBufferSize](#setbuffersize)
 * [setCallback](#setcallback)
 * [setTimeout](#settimeout)
 * [write](#write)

## API Documentation

### Variables

#### [timeout](#timeout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp.timeout` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Timeout for the socket operations, in seconds. New [`hs.socket.udp`](#new) objects will be created with this timeout value, but can individually change it with the [`setTimeout`](#setTimeout) method |

### Functions

#### [parseAddress](#parseaddress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp.parseAddress(sockaddr) -> table or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Alias for [`hs.socket.parseAddress`](./hs.socket.html#parseAddress) |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp.new([fn]) -> hs.socket.udp object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an unconnected asynchronous UDP socket object |
| **Parameters**                                       | <ul><li>fn - An optional <a href="#setCallback">callback function</a> for reading data from the socket, settable here for convenience</li></ul> |
| **Returns**                                          | <ul><li>An <a href="#new"><code>hs.socket.udp</code></a> object</li></ul> |

#### [server](#server)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp.server(port[, fn]) -> hs.socket.udp object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates and binds an [`hs.socket.udp`](#new) instance to a port for listening |
| **Parameters**                                       | <ul><li>port - A port number [0-65535]. Ports [1-1023] are privileged. Port 0 allows the OS to select any available port</li><li>fn - An optional <a href="#setCallback">callback function</a> for reading data from the socket, settable here for convenience</li></ul> |
| **Returns**                                          | <ul><li>An <a href="#new"><code>hs.socket.udp</code></a> object</li></ul> |

### Methods

#### [broadcast](#broadcast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:broadcast([flag]) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Enables broadcasting on the underlying socket |
| **Parameters**                                       | <ul><li>flag - An optional boolean: <code>true</code> to enable broadcasting, <code>false</code> to disable it. Defaults to <code>true</code></li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object or <code>nil</code> if an error occurred</li></ul> |
| **Notes**                                            | <ul><li>By default, the underlying socket in the OS will not allow you to send broadcast messages</li><li>In order to send broadcast messages, you need to enable this functionality in the socket</li><li>A broadcast is a UDP message to addresses like "192.168.255.255" or "255.255.255.255" that is delivered to every host on the network.</li><li>The reason this is generally disabled by default (by the OS) is to prevent accidental broadcast messages from flooding the network.</li></ul> |

#### [close](#close)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:close() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Immediately closes the underlying socket, freeing the [`hs.socket.udp`](#new) instance for reuse. Any pending send operations are discarded |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object</li></ul> |

#### [closed](#closed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:closed() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the closed status of the [`hs.socket.udp`](#new) instance |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if closed, otherwise <code>false</code></li></ul> |
| **Notes**                                            | <ul><li>UDP sockets are typically meant to be connectionless</li><li>Sending a packet anywhere, regardless of whether or not the destination receives it, opens the socket until it is explicitly closed</li><li>An active listening socket will not be closed, but will not be 'connected' unless the <a href="#connect">connect</a> method has been called</li></ul> |

#### [connect](#connect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:connect(host, port[, fn]) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Connects an unconnected [`hs.socket.udp`](#new) instance |
| **Parameters**                                       | <ul><li>host - A string containing the hostname or IP address</li><li>port - A port number [1-65535]</li><li>fn - An optional single-use callback function to execute after establishing the connection. Receives no parameters</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object or <code>nil</code> if an error occured</li></ul> |
| **Notes**                                            | <ul><li>By design, UDP is a connectionless protocol, and connecting is not needed</li><li>Choosing to connect to a specific host/port has the following effect:</li><li>You will only be able to send data to the connected host/port</li><li>You will only be able to receive data from the connected host/port</li><li>You will receive ICMP messages that come from the connected host/port, such as "connection refused"</li><li>The actual process of connecting a UDP socket does not result in any communication on the socket. It simply changes the internal state of the socket</li><li>You cannot bind a socket after it has been connected</li><li>You can only connect a socket once</li></ul> |

#### [connected](#connected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:connected() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the connection status of the [`hs.socket.udp`](#new) instance |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if connected, otherwise <code>false</code></li></ul> |
| **Notes**                                            | <ul><li>UDP sockets are typically meant to be connectionless</li><li>This method will only return <code>true</code> if the <a href="#connect"><code>connect</code></a> method has been explicitly called</li></ul> |

#### [enableIPv](#enableipv)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:enableIPv(version[, flag]) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Enables or disables IPv4 or IPv6 on the underlying socket. By default, both are enabled |
| **Parameters**                                       | <ul><li>version - A number containing the IP version (4 or 6) to enable or disable</li><li>flag - A boolean: <code>true</code> to enable the chosen IP version, <code>false</code> to disable it. Defaults to <code>true</code></li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object or <code>nil</code> if an error occurred</li></ul> |
| **Notes**                                            | <ul><li>Must be called before binding the socket. If you want to create an IPv6-only server, do something like:</li><li><code>hs.socket.udp.new(callback):enableIPv(4, false):listen(port):receive()</code></li><li>The convenience constructor <a href="#server"><code>hs.socket.server</code></a> will automatically bind the socket and requires closing and relistening to use this method</li></ul> |

#### [info](#info)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:info() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns information on the [`hs.socket.udp`](#new) instance |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the following keys:</li><li>connectedAddress - <code>string</code> (<code>sockaddr</code> struct)</li><li>connectedHost - <code>string</code></li><li>connectedPort - <code>number</code></li><li>isClosed - <code>boolean</code></li><li>isConnected - <code>boolean</code></li><li>isIPv4 - <code>boolean</code></li><li>isIPv4Enabled - <code>boolean</code></li><li>isIPv4Preferred - <code>boolean</code></li><li>isIPv6 - <code>boolean</code></li><li>isIPv6Enabled - <code>boolean</code></li><li>isIPv6Preferred - <code>boolean</code></li><li>isIPVersionNeutral - <code>boolean</code></li><li>localAddress - <code>string</code> (<code>sockaddr</code> struct)</li><li>localAddress_IPv4 - <code>string</code> (<code>sockaddr</code> struct)</li><li>localAddress_IPv6 - <code>string</code> (<code>sockaddr</code> struct)</li><li>localHost - <code>string</code></li><li>localHost_IPv4 - <code>string</code></li><li>localHost_IPv6 - <code>string</code></li><li>localPort - <code>number</code></li><li>localPort_IPv4 - <code>number</code></li><li>localPort_IPv6 - <code>number</code></li><li>maxReceiveIPv4BufferSize - <code>number</code></li><li>maxReceiveIPv6BufferSize - <code>number</code></li><li>timeout - <code>number</code></li><li>userData - <code>string</code></li></ul> |

#### [listen](#listen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:listen(port) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Binds an unconnected [`hs.socket.udp`](#new) instance to a port for listening |
| **Parameters**                                       | <ul><li>port - A port number [0-65535]. Ports [1-1023] are privileged. Port 0 allows the OS to select any available port</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object or <code>nil</code> if an error occured</li></ul> |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:pause() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Suspends reading of packets from the socket. Call one of the receive methods to resume |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object</li></ul> |

#### [preferIPv](#preferipv)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:preferIPv([version]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the preferred IP version: IPv4, IPv6, or neutral (first to resolve) |
| **Parameters**                                       | <ul><li>version - An optional number containing the IP version to prefer. Anything but 4 or 6 else sets the default neutral behavior</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object</li></ul> |
| **Notes**                                            | <ul><li>If a DNS lookup returns only IPv4 results, the socket will automatically use IPv4</li><li>If a DNS lookup returns only IPv6 results, the socket will automatically use IPv6</li><li>If a DNS lookup returns both IPv4 and IPv6 results, then the protocol used depends on the configured preference</li></ul> |

#### [read](#read)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:read(delimiter[, tag]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Alias for [`hs.socket.udp:receive`](#receive) |

#### [readOne](#readone)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:readOne(delimiter[, tag]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Alias for [`hs.socket.udp:receiveOne`](#receiveOne) |

#### [receive](#receive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:receive([fn]) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Reads packets from the socket as they arrive. Results are passed to the [callback function](#setCallback), which must be set to use this method |
| **Parameters**                                       | <ul><li>fn - Optionally supply the <a href="#setCallback">read callback</a> here</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object or <code>nil</code> if an error occured</li></ul> |
| **Notes**                                            | <ul><li>There are two modes of operation for receiving packets: one-at-a-time &amp; continuous</li><li>In one-at-a-time mode, you call receiveOne every time you are ready process an incoming UDP packet</li><li>Receiving packets one-at-a-time may be better suited for implementing certain state machine code where your state machine may not always be ready to process incoming packets</li><li>In continuous mode, the callback is invoked immediately every time incoming udp packets are received</li><li>Receiving packets continuously is better suited to real-time streaming applications</li><li>You may switch back and forth between one-at-a-time mode and continuous mode</li><li>If the socket is currently in one-at-a-time mode, calling this method will switch it to continuous mode</li></ul> |

#### [receiveOne](#receiveone)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:receiveOne([fn]) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Reads a single packet from the socket. Results are passed to the [callback function](#setCallback), which must be set to use this method |
| **Parameters**                                       | <ul><li>fn - Optionally supply the <a href="#setCallback">read callback</a> here</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object or <code>nil</code> if an error occured</li></ul> |
| **Notes**                                            | <ul><li>There are two modes of operation for receiving packets: one-at-a-time &amp; continuous</li><li>In one-at-a-time mode, you call receiveOne every time you are ready process an incoming UDP packet</li><li>Receiving packets one-at-a-time may be better suited for implementing certain state machine code where your state machine may not always be ready to process incoming packets</li><li>In continuous mode, the callback is invoked immediately every time incoming udp packets are received</li><li>Receiving packets continuously is better suited to real-time streaming applications</li><li>You may switch back and forth between one-at-a-time mode and continuous mode</li><li>If the socket is currently in continuous mode, calling this method will switch it to one-at-a-time mode</li></ul> |

#### [reusePort](#reuseport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:reusePort([flag]) -> self or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Enables port reuse on the underlying socket |
| **Parameters**                                       | <ul><li>flag - An optional boolean: <code>true</code> to enable port reuse, <code>false</code> to disable it. Defaults to <code>true</code></li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object or <code>nil</code> if an error occurred</li></ul> |
| **Notes**                                            | <ul><li>By default, only one socket can be bound to a given IP address+port at a time</li><li>To enable multiple processes to simultaneously bind to the same address+port, you need to enable this functionality in the socket</li><li>All processes that wish to use the address+port simultaneously must all enable reuse port on the socket bound to that port</li><li>Must be called before binding the socket</li></ul> |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:send(message, host, port[, tag][, fn]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sends a packet to the destination address |
| **Parameters**                                       | <ul><li>message - A string containing data to be sent on the socket</li><li>host - A string containing the hostname or IP address</li><li>port - A port number [1-65535]</li><li>tag - An optional integer to assist with labeling writes</li><li>fn - An optional single-use callback function to execute after sending the packet. Receives the tag parameter</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object</li></ul> |
| **Notes**                                            | <ul><li>For non-connected sockets, the remote destination is specified for each packet</li><li>If the socket has been explicitly connected with <a href="#connect"><code>connect</code></a>, only the message parameter and an optional tag and/or write callback can be supplied</li><li>Recall that connecting is optional for a UDP socket</li><li>For connected sockets, data can only be sent to the connected address</li></ul> |

#### [setBufferSize](#setbuffersize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:setBufferSize(size[, version]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the maximum size of the buffer that will be allocated for receive operations |
| **Parameters**                                       | <ul><li>size - An number containing the receive buffer size in bytes</li><li>version - An optional number containing the IP version for which to set the buffer size. Anything but 4 or 6 else sets the same size for both</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object</li></ul> |
| **Notes**                                            | <ul><li>The default maximum size is 9216 bytes</li><li>The theoretical maximum size of any IPv4 UDP packet is UINT16_MAX = 65535</li><li>The theoretical maximum size of any IPv6 UDP packet is UINT32_MAX = 4294967295</li><li>Since the OS notifies us of the size of each received UDP packet, the actual allocated buffer size for each packet is exact</li><li>In practice the size of UDP packets is generally much smaller than the max. Most protocols will send and receive packets of only a few bytes, or will set a limit on the size of packets to prevent fragmentation in the IP layer.</li><li>If you set the buffer size too small, the sockets API in the OS will silently discard any extra data</li></ul> |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:setCallback([fn]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the read callback for the [`hs.socket.udp`](#new) instance. Must be set to read data from the socket |
| **Parameters**                                       | <ul><li>fn - An optional callback function to process data read from the socket. <code>nil</code> or no argument clears the callback</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object</li></ul> |

#### [setTimeout](#settimeout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:setTimeout(timeout) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the timeout for the socket operations. If the timeout value is negative, the operations will not use a timeout, which is the default |
| **Parameters**                                       | <ul><li>timeout - A number containing the timeout duration, in seconds</li></ul> |
| **Returns**                                          | <ul><li>The <a href="#new"><code>hs.socket.udp</code></a> object</li></ul> |

#### [write](#write)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.socket.udp:write(message[, tag]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Alias for [`hs.socket.udp:send`](#send) |

