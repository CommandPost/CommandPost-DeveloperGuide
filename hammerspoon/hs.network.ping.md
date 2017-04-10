# [docs](hammerspoon/index.md) » hs.network.ping
---

This module provides a basic ping function which can test host availability. Ping is a network diagnostic tool commonly found in most operating systems which can be used to test if a route to a specified host exists and if that host is responding to network traffic.

## Submodules
 * [hs.network.ping.echoRequest](hs.network.ping.echoRequest.md)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [ping](#ping)
* Methods - API calls which can only be made on an object returned by a constructor
 * [address](#address)
 * [cancel](#cancel)
 * [count](#count)
 * [isPaused](#isPaused)
 * [isRunning](#isRunning)
 * [packets](#packets)
 * [pause](#pause)
 * [resume](#resume)
 * [sent](#sent)
 * [server](#server)
 * [setCallback](#setCallback)
 * [summary](#summary)

## API Documentation

### Constructors

| [ping](#ping)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping.ping(server, [count], [interval], [timeout], [class], [fn]) -> pingObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Test server availability by pinging it with ICMP Echo Requests.                                                                     |
| **Parameters**                              | <ul><li>`server`   - a string containing the hostname or ip address of the server to test. Both IPv4 and IPv6 addresses are supported.</li><li>`count`    - an optional integer, default 5, specifying the number of ICMP Echo Requests to send to the server.</li><li>`interval` - an optional number, default 1.0, in seconds specifying the delay between the sending of each echo request. To set this parameter, you must supply `count` as well.</li><li>`timeout`  - an optional number, default 2.0, in seconds specifying how long before an echo reply is considered to have timed-out. To set this parameter, you must supply `count` and `interval` as well.</li><li>`class`    - an optional string, default "any", specifying whether IPv4 or IPv6 should be used to send the ICMP packets. The string must be one of the following:</li><li>  `any`  - uses the IP version which corresponds to the first address the `server` resolves to</li><li>  `IPv4` - use IPv4; if `server` cannot resolve to an IPv4 address, or if IPv4 traffic is not supported on the network, the ping will fail with an error.</li><li>  `IPv6` - use IPv6; if `server` cannot resolve to an IPv6 address, or if IPv6 traffic is not supported on the network, the ping will fail with an error.</li><li>`fn`       - the callback function which receives update messages for the ping process. See the Notes for details regarding the callback function.</li></ul> |
| **Returns**                                 | <ul><li>a pingObject</li></ul>          |
| **Notes**                                   | <ul><li>For convenience, you can call this constructor as `hs.network.ping(server, ...)`</li><li>the full ping process will take at most `count``interval` + `timeout` seconds from `didStart` to `didFinish`.</li></ul>                |

### Methods

| [address](#address)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:address() -> string`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a string containing the resolved IPv4 or IPv6 address this pingObject is sending echo requests to.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing the IPv4 or IPv6 address this pingObject is sending echo requests to or "<unresolved address>" if the address cannot be resolved.</li></ul>          |

| [cancel](#cancel)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:cancel() -> none`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Cancels an in progress ping process, terminating it immediately                                                                     |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>the `didFinish` message will be sent to the callback function as its final message.</li></ul>                |

| [count](#count)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:count([count]) -> integer | pingObject | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the number of ICMP Echo Requests that will be sent by the ping process                                                                     |
| **Parameters**                              | <ul><li>`count` - an optional integer specifying the total number of echo requests that the ping process should send. If specified, this number must be greater than the number of requests already sent.</li></ul> |
| **Returns**                                 | <ul><li>if no argument is specified, returns the current number of echo requests the ping process will send; if an argument is specified and the ping process has not completed, returns the pingObject; if the ping process has already completed, then this method returns nil.</li></ul>          |

| [isPaused](#isPaused)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:isPaused() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns whether or not the ping process is currently paused.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A boolean indicating if the ping process is paused (true) or not (false)</li></ul>          |

| [isRunning](#isRunning)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:isRunning() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns whether or not the ping process is currently active.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A boolean indicating if the ping process is active (true) or not (false)</li></ul>          |
| **Notes**                                   | <ul><li>This method will return false only if the ping process has finished sending all echo requests or if it has been cancelled with [hs.network.ping:cancel](#cancel).  To determine if the process is currently sending out echo requests, see [hs.network.ping:isPaused](#isPaused).</li></ul>                |

| [packets](#packets)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:packets([sequenceNumber]) -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a table containing information about the ICMP Echo packets sent by this pingObject.                                                                     |
| **Parameters**                              | <ul><li>`sequenceNumber` - an optional integer specifying the sequence number of the ICMP Echo packet to return information about.</li></ul> |
| **Returns**                                 | <ul><li>If `sequenceNumber` is specified, returns a table with key-value pairs containing information about the specific ICMP Echo packet with that sequence number, or an empty table if no packet with that sequence number has been sent yet. If no sequence number is specified, returns an array table of all ICMP Echo packets this object has sent.</li></ul>          |
| **Notes**                                   | <ul><li>Sequence numbers start at 0 while Lua array tables are indexed starting at 1. If you do not specify a `sequenceNumber` to this method, index 1 of the array table returned will contain a table describing the ICMP Echo packet with sequence number 0, index 2 will describe the ICMP Echo packet with sequence number 1, etc.</li></ul>                |

| [pause](#pause)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:pause() -> pingObject | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Pause an in progress ping process.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>if the ping process is currently active, returns the pingObject; if the process has already completed, returns nil.</li></ul>          |

| [resume](#resume)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:resume() -> pingObject | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Resume an in progress ping process, if it has been paused.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>if the ping process is currently active, returns the pingObject; if the process has already completed, returns nil.</li></ul>          |

| [sent](#sent)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:sent() -> integer`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the number of ICMP Echo Requests which have been sent.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The number of echo requests which have been sent so far.</li></ul>          |

| [server](#server)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:server() -> string`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the hostname or ip address string given to the [hs.network.ping.ping](#ping) constructor.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string matching the hostname or ip address given to the [hs.network.ping.ping](#ping) constructor for this object.</li></ul>          |

| [setCallback](#setCallback)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:setCallback(fn | nil) -> pingObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Set or remoce the callback function for the pingObject.                                                                     |
| **Returns**                                 | <ul><li>the pingObject</li></ul>          |
| **Notes**                                   | <ul><li>Because the ping process begins immediately upon creation with the [hs.network.ping.ping](#ping) constructor, it is preferable to assign the callback with the constructor itself.</li><li>This method is provided as a means of changing the callback based on other events (a change in the current network or location, perhaps.)</li><li>If you truly wish to create a pingObject with no callback, you will need to do something like `hs.network.ping.ping(...):setCallback(function() end)`.</li></ul>                |

| [summary](#summary)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.network.ping:summary() -> string`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a string containing summary information about the ping process.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a summary string for the current state of the ping process</li></ul>          |
| **Notes**                                   | <ul><li>The summary string will look similar to the following:</li><li>~~~</li><li>--- hostname ping statistics </li><li>5 packets transmitted, 5 packets received, 0.0 packet loss</li><li>round-trip min/avg/max = 2.282/4.133/4.926 ms</li><li>~~~</li><li>The numer of packets received will match the number that has currently been sent, not necessarily the value returned by [hs.network.ping:count](#count).</li></ul>                |

