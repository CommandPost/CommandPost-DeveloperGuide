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
 * [parseAddress](#parseAddress)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [server](#server)
* Methods - API calls which can only be made on an object returned by a constructor
 * [broadcast](#broadcast)
 * [close](#close)
 * [closed](#closed)
 * [connect](#connect)
 * [connected](#connected)
 * [enableIPv](#enableIPv)
 * [info](#info)
 * [listen](#listen)
 * [pause](#pause)
 * [preferIPv](#preferIPv)
 * [read](#read)
 * [readOne](#readOne)
 * [receive](#receive)
 * [receiveOne](#receiveOne)
 * [reusePort](#reusePort)
 * [send](#send)
 * [setBufferSize](#setBufferSize)
 * [setCallback](#setCallback)
 * [setTimeout](#setTimeout)
 * [write](#write)

## API Documentation
### Variables

#### [timeout](#timeout)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp.timeout  |
| Type        | Variable |
| Description | Timeout for the socket operations, in seconds. New [`hs.socket.udp`](#new) objects will be created with this timeout value, but can individually change it with the [`setTimeout`](#setTimeout) method |
 |

### Functions

#### [parseAddress](#parseAddress)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp.parseAddress(sockaddr) -> table or nil  |
| Type        | Function |
| Description | Alias for [`hs.socket.parseAddress`](./hs.socket.html#parseAddress) |
 |

### Constructors

#### [new](#new)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp.new([fn]) -> hs.socket.udp object  |
| Type        | Constructor |
| Description | Creates an unconnected asynchronous UDP socket object |
| Parameters |  * fn - An optional [callback function](#setCallback) for reading data from the socket, settable here for convenience |
| Returns |  * An [`hs.socket.udp`](#new) object |


#### [server](#server)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp.server(port[, fn]) -> hs.socket.udp object  |
| Type        | Constructor |
| Description | Creates and binds an [`hs.socket.udp`](#new) instance to a port for listening |
| Parameters |  * port - A port number [0-65535]. Ports [1-1023] are privileged. Port 0 allows the OS to select any available port * fn - An optional [callback function](#setCallback) for reading data from the socket, settable here for convenience |
| Returns |  * An [`hs.socket.udp`](#new) object |
 |

### Methods

#### [broadcast](#broadcast)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:broadcast([flag]) -> self or nil  |
| Type        | Method |
| Description | Enables broadcasting on the underlying socket |
| Parameters |  * flag - An optional boolean: `true` to enable broadcasting, `false` to disable it. Defaults to `true` |
| Returns |  * The [`hs.socket.udp`](#new) object or `nil` if an error occurred |
| Notes |  * By default, the underlying socket in the OS will not allow you to send broadcast messages * In order to send broadcast messages, you need to enable this functionality in the socket * A broadcast is a UDP message to addresses like "192.168.255.255" or "255.255.255.255" that is delivered to every host on the network. * The reason this is generally disabled by default (by the OS) is to prevent accidental broadcast messages from flooding the network.

#### [close](#close)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:close() -> self  |
| Type        | Method |
| Description | Immediately closes the underlying socket, freeing the [`hs.socket.udp`](#new) instance for reuse. Any pending send operations are discarded |
| Parameters |  * None |
| Returns |  * The [`hs.socket.udp`](#new) object |


#### [closed](#closed)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:closed() -> bool  |
| Type        | Method |
| Description | Returns the closed status of the [`hs.socket.udp`](#new) instance |
| Parameters |  * None |
| Returns |  * `true` if closed, otherwise `false` |
| Notes |  * UDP sockets are typically meant to be connectionless * Sending a packet anywhere, regardless of whether or not the destination receives it, opens the socket until it is explicitly closed * An active listening socket will not be closed, but will not be 'connected' unless the [connect](#connect) method has been called

#### [connect](#connect)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:connect(host, port[, fn]) -> self or nil  |
| Type        | Method |
| Description | Connects an unconnected [`hs.socket.udp`](#new) instance |
| Parameters |  * host - A string containing the hostname or IP address * port - A port number [1-65535] * fn - An optional single-use callback function to execute after establishing the connection. Receives no parameters |
| Returns |  * The [`hs.socket.udp`](#new) object or `nil` if an error occured |
| Notes | * By design, UDP is a connectionless protocol, and connecting is not needed* Choosing to connect to a specific host/port has the following effect: * You will only be able to send data to the connected host/port * You will only be able to receive data from the connected host/port * You will receive ICMP messages that come from the connected host/port, such as "connection refused"* The actual process of connecting a UDP socket does not result in any communication on the socket. It simply changes the internal state of the socket* You cannot bind a socket after it has been connected* You can only connect a socket once

#### [connected](#connected)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:connected() -> bool  |
| Type        | Method |
| Description | Returns the connection status of the [`hs.socket.udp`](#new) instance |
| Parameters |  * None |
| Returns |  * `true` if connected, otherwise `false` |
| Notes |  * UDP sockets are typically meant to be connectionless * This method will only return `true` if the [`connect`](#connect) method has been explicitly called

#### [enableIPv](#enableIPv)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:enableIPv(version[, flag]) -> self or nil  |
| Type        | Method |
| Description | Enables or disables IPv4 or IPv6 on the underlying socket. By default, both are enabled |
| Parameters |  * version - A number containing the IP version (4 or 6) to enable or disable * flag - A boolean: `true` to enable the chosen IP version, `false` to disable it. Defaults to `true` |
| Returns |  * The [`hs.socket.udp`](#new) object or `nil` if an error occurred |
| Notes |  * Must be called before binding the socket. If you want to create an IPv6-only server, do something like:  * `hs.socket.udp.new(callback):enableIPv(4, false):listen(port):receive()` * The convenience constructor [`hs.socket.server`](#server) will automatically bind the socket and requires closing and relistening to use this method

#### [info](#info)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:info() -> table  |
| Type        | Method |
| Description | Returns information on the [`hs.socket.udp`](#new) instance |
| Parameters |  * None |
| Returns |  * A table containing the following keys:  * connectedAddress - `string` (`sockaddr` struct)  * connectedHost - `string`  * connectedPort - `number`  * isClosed - `boolean`  * isConnected - `boolean`  * isIPv4 - `boolean`  * isIPv4Enabled - `boolean`  * isIPv4Preferred - `boolean`  * isIPv6 - `boolean`  * isIPv6Enabled - `boolean`  * isIPv6Preferred - `boolean`  * isIPVersionNeutral - `boolean`  * localAddress - `string` (`sockaddr` struct)  * localAddress_IPv4 - `string` (`sockaddr` struct)  * localAddress_IPv6 - `string` (`sockaddr` struct)  * localHost - `string`  * localHost_IPv4 - `string`  * localHost_IPv6 - `string`  * localPort - `number`  * localPort_IPv4 - `number`  * localPort_IPv6 - `number`  * maxReceiveIPv4BufferSize - `number`  * maxReceiveIPv6BufferSize - `number`  * timeout - `number`  * userData - `string` |


#### [listen](#listen)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:listen(port) -> self or nil  |
| Type        | Method |
| Description | Binds an unconnected [`hs.socket.udp`](#new) instance to a port for listening |
| Parameters |  * port - A port number [0-65535]. Ports [1-1023] are privileged. Port 0 allows the OS to select any available port |
| Returns |  * The [`hs.socket.udp`](#new) object or `nil` if an error occured |


#### [pause](#pause)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:pause() -> self  |
| Type        | Method |
| Description | Suspends reading of packets from the socket. Call one of the receive methods to resume |
| Parameters |  * None |
| Returns |  * The [`hs.socket.udp`](#new) object |


#### [preferIPv](#preferIPv)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:preferIPv([version]) -> self  |
| Type        | Method |
| Description | Sets the preferred IP version: IPv4, IPv6, or neutral (first to resolve) |
| Parameters |  * version - An optional number containing the IP version to prefer. Anything but 4 or 6 else sets the default neutral behavior |
| Returns |  * The [`hs.socket.udp`](#new) object |
| Notes |  * If a DNS lookup returns only IPv4 results, the socket will automatically use IPv4 * If a DNS lookup returns only IPv6 results, the socket will automatically use IPv6 * If a DNS lookup returns both IPv4 and IPv6 results, then the protocol used depends on the configured preference

#### [read](#read)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:read(delimiter[, tag]) -> self  |
| Type        | Method |
| Description | Alias for [`hs.socket.udp:receive`](#receive) |


#### [readOne](#readOne)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:readOne(delimiter[, tag]) -> self  |
| Type        | Method |
| Description | Alias for [`hs.socket.udp:receiveOne`](#receiveOne) |


#### [receive](#receive)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:receive([fn]) -> self or nil  |
| Type        | Method |
| Description | Reads packets from the socket as they arrive. Results are passed to the [callback function](#setCallback), which must be set to use this method |
| Parameters |  * fn - Optionally supply the [read callback](#setCallback) here |
| Returns |  * The [`hs.socket.udp`](#new) object or `nil` if an error occured |
| Notes |  * There are two modes of operation for receiving packets: one-at-a-time & continuous * In one-at-a-time mode, you call receiveOne every time you are ready process an incoming UDP packet * Receiving packets one-at-a-time may be better suited for implementing certain state machine code where your state machine may not always be ready to process incoming packets * In continuous mode, the callback is invoked immediately every time incoming udp packets are received * Receiving packets continuously is better suited to real-time streaming applications * You may switch back and forth between one-at-a-time mode and continuous mode * If the socket is currently in one-at-a-time mode, calling this method will switch it to continuous mode

#### [receiveOne](#receiveOne)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:receiveOne([fn]) -> self or nil  |
| Type        | Method |
| Description | Reads a single packet from the socket. Results are passed to the [callback function](#setCallback), which must be set to use this method |
| Parameters |  * fn - Optionally supply the [read callback](#setCallback) here |
| Returns |  * The [`hs.socket.udp`](#new) object or `nil` if an error occured |
| Notes |  * There are two modes of operation for receiving packets: one-at-a-time & continuous * In one-at-a-time mode, you call receiveOne every time you are ready process an incoming UDP packet * Receiving packets one-at-a-time may be better suited for implementing certain state machine code where your state machine may not always be ready to process incoming packets * In continuous mode, the callback is invoked immediately every time incoming udp packets are received * Receiving packets continuously is better suited to real-time streaming applications * You may switch back and forth between one-at-a-time mode and continuous mode * If the socket is currently in continuous mode, calling this method will switch it to one-at-a-time mode

#### [reusePort](#reusePort)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:reusePort([flag]) -> self or nil  |
| Type        | Method |
| Description | Enables port reuse on the underlying socket |
| Parameters |  * flag - An optional boolean: `true` to enable port reuse, `false` to disable it. Defaults to `true` |
| Returns |  * The [`hs.socket.udp`](#new) object or `nil` if an error occurred |
| Notes |  * By default, only one socket can be bound to a given IP address+port at a time * To enable multiple processes to simultaneously bind to the same address+port, you need to enable this functionality in the socket * All processes that wish to use the address+port simultaneously must all enable reuse port on the socket bound to that port * Must be called before binding the socket

#### [send](#send)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:send(message, host, port[, tag][, fn]) -> self  |
| Type        | Method |
| Description | Sends a packet to the destination address |
| Parameters |  * message - A string containing data to be sent on the socket * host - A string containing the hostname or IP address * port - A port number [1-65535] * tag - An optional integer to assist with labeling writes * fn - An optional single-use callback function to execute after sending the packet. Receives the tag parameter |
| Returns |  * The [`hs.socket.udp`](#new) object |
| Notes |  * For non-connected sockets, the remote destination is specified for each packet * If the socket has been explicitly connected with [`connect`](#connect), only the message parameter and an optional tag and/or write callback can be supplied * Recall that connecting is optional for a UDP socket * For connected sockets, data can only be sent to the connected address

#### [setBufferSize](#setBufferSize)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:setBufferSize(size[, version]) -> self  |
| Type        | Method |
| Description | Sets the maximum size of the buffer that will be allocated for receive operations |
| Parameters |  * size - An number containing the receive buffer size in bytes * version - An optional number containing the IP version for which to set the buffer size. Anything but 4 or 6 else sets the same size for both |
| Returns |  * The [`hs.socket.udp`](#new) object |
| Notes |  * The default maximum size is 9216 bytes * The theoretical maximum size of any IPv4 UDP packet is UINT16_MAX = 65535 * The theoretical maximum size of any IPv6 UDP packet is UINT32_MAX = 4294967295 * Since the OS notifies us of the size of each received UDP packet, the actual allocated buffer size for each packet is exact * In practice the size of UDP packets is generally much smaller than the max. Most protocols will send and receive packets of only a few bytes, or will set a limit on the size of packets to prevent fragmentation in the IP layer. * If you set the buffer size too small, the sockets API in the OS will silently discard any extra data

#### [setCallback](#setCallback)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:setCallback([fn]) -> self  |
| Type        | Method |
| Description | Sets the read callback for the [`hs.socket.udp`](#new) instance. Must be set to read data from the socket |
| Parameters |  * fn - An optional callback function to process data read from the socket. `nil` or no argument clears the callback |
| Returns |  * The [`hs.socket.udp`](#new) object |


#### [setTimeout](#setTimeout)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:setTimeout(timeout) -> self  |
| Type        | Method |
| Description | Sets the timeout for the socket operations. If the timeout value is negative, the operations will not use a timeout, which is the default |
| Parameters |  * timeout - A number containing the timeout duration, in seconds |
| Returns |  * The [`hs.socket.udp`](#new) object |


#### [write](#write)
|             |                 |
| ------------|-----------------|
| Signature   | hs.socket.udp:write(message[, tag]) -> self  |
| Type        | Method |
| Description | Alias for [`hs.socket.udp:send`](#send) |
 |
