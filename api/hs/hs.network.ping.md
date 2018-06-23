# [docs](index.md) » hs.network.ping
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
 * [isPaused](#ispaused)
 * [isRunning](#isrunning)
 * [packets](#packets)
 * [pause](#pause)
 * [resume](#resume)
 * [sent](#sent)
 * [server](#server)
 * [setCallback](#setcallback)
 * [summary](#summary)

## API Documentation

### Constructors

#### [ping](#ping)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping.ping(server, [count], [interval], [timeout], [class], [fn]) -> pingObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Test server availability by pinging it with ICMP Echo Requests.                                                                                         |
| **Parameters**                                       | <ul><li><code>server</code>   - a string containing the hostname or ip address of the server to test. Both IPv4 and IPv6 addresses are supported.</li></ul><ul><li><code>count</code>    - an optional integer, default 5, specifying the number of ICMP Echo Requests to send to the server.</li></ul><ul><li><code>interval</code> - an optional number, default 1.0, in seconds specifying the delay between the sending of each echo request. To set this parameter, you must supply <code>count</code> as well.</li></ul><ul><li><code>timeout</code>  - an optional number, default 2.0, in seconds specifying how long before an echo reply is considered to have timed-out. To set this parameter, you must supply <code>count</code> and <code>interval</code> as well.</li></ul><ul><li><code>class</code>    - an optional string, default "any", specifying whether IPv4 or IPv6 should be used to send the ICMP packets. The string must be one of the following:</li></ul><ul><li><code>any</code>  - uses the IP version which corresponds to the first address the <code>server</code> resolves to</li></ul><ul><li><code>IPv4</code> - use IPv4; if <code>server</code> cannot resolve to an IPv4 address, or if IPv4 traffic is not supported on the network, the ping will fail with an error.</li></ul><ul><li><code>IPv6</code> - use IPv6; if <code>server</code> cannot resolve to an IPv6 address, or if IPv6 traffic is not supported on the network, the ping will fail with an error.</li></ul><ul><li><code>fn</code>       - the callback function which receives update messages for the ping process. See the Notes for details regarding the callback function.</li></ul>   |
| **Returns**                                          | <ul><li>a pingObject</li></ul>            |
| **Notes**                                            | <ul><li>For convenience, you can call this constructor as <code>hs.network.ping(server, ...)</code></li></ul><ul><li>the full ping process will take at most <code>count</code> * <code>interval</code> + <code>timeout</code> seconds from <code>didStart</code> to <code>didFinish</code>.</li></ul>                 |

### Methods

#### [address](#address)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:address() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a string containing the resolved IPv4 or IPv6 address this pingObject is sending echo requests to.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the IPv4 or IPv6 address this pingObject is sending echo requests to or "<unresolved address>" if the address cannot be resolved.</li></ul>            |

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:cancel() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Cancels an in progress ping process, terminating it immediately                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>the <code>didFinish</code> message will be sent to the callback function as its final message.</li></ul>                 |

#### [count](#count)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:count([count]) -> integer | pingObject | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the number of ICMP Echo Requests that will be sent by the ping process                                                                                         |
| **Parameters**                                       | <ul><li><code>count</code> - an optional integer specifying the total number of echo requests that the ping process should send. If specified, this number must be greater than the number of requests already sent.</li></ul>   |
| **Returns**                                          | <ul><li>if no argument is specified, returns the current number of echo requests the ping process will send; if an argument is specified and the ping process has not completed, returns the pingObject; if the ping process has already completed, then this method returns nil.</li></ul>            |

#### [isPaused](#ispaused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:isPaused() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the ping process is currently paused.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A boolean indicating if the ping process is paused (true) or not (false)</li></ul>            |

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:isRunning() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the ping process is currently active.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A boolean indicating if the ping process is active (true) or not (false)</li></ul>            |
| **Notes**                                            | <ul><li>This method will return false only if the ping process has finished sending all echo requests or if it has been cancelled with <a href="#cancel">hs.network.ping:cancel</a>.  To determine if the process is currently sending out echo requests, see <a href="#isPaused">hs.network.ping:isPaused</a>.</li></ul>                 |

#### [packets](#packets)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:packets([sequenceNumber]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table containing information about the ICMP Echo packets sent by this pingObject.                                                                                         |
| **Parameters**                                       | <ul><li><code>sequenceNumber</code> - an optional integer specifying the sequence number of the ICMP Echo packet to return information about.</li></ul>   |
| **Returns**                                          | <ul><li>If <code>sequenceNumber</code> is specified, returns a table with key-value pairs containing information about the specific ICMP Echo packet with that sequence number, or an empty table if no packet with that sequence number has been sent yet. If no sequence number is specified, returns an array table of all ICMP Echo packets this object has sent.</li></ul>            |
| **Notes**                                            | <ul><li>Sequence numbers start at 0 while Lua array tables are indexed starting at 1. If you do not specify a <code>sequenceNumber</code> to this method, index 1 of the array table returned will contain a table describing the ICMP Echo packet with sequence number 0, index 2 will describe the ICMP Echo packet with sequence number 1, etc.</li></ul>                 |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:pause() -> pingObject | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Pause an in progress ping process.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>if the ping process is currently active, returns the pingObject; if the process has already completed, returns nil.</li></ul>            |

#### [resume](#resume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:resume() -> pingObject | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resume an in progress ping process, if it has been paused.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>if the ping process is currently active, returns the pingObject; if the process has already completed, returns nil.</li></ul>            |

#### [sent](#sent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:sent() -> integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the number of ICMP Echo Requests which have been sent.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The number of echo requests which have been sent so far.</li></ul>            |

#### [server](#server)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:server() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the hostname or ip address string given to the [hs.network.ping.ping](#ping) constructor.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string matching the hostname or ip address given to the <a href="#ping">hs.network.ping.ping</a> constructor for this object.</li></ul>            |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:setCallback(fn | nil) -> pingObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set or remoce the callback function for the pingObject.                                                                                         |
| **Parameters**                                       | <ul><li><code>fn</code> - the function to set as the callback, or nil if you wish use the default callback.</li></ul>   |
| **Returns**                                          | <ul><li>the pingObject</li></ul>            |
| **Notes**                                            | <ul><li>Because the ping process begins immediately upon creation with the <a href="#ping">hs.network.ping.ping</a> constructor, it is preferable to assign the callback with the constructor itself.</li></ul><ul><li>This method is provided as a means of changing the callback based on other events (a change in the current network or location, perhaps.)</li></ul><ul><li>If you truly wish to create a pingObject with no callback, you will need to do something like <code>hs.network.ping.ping(...):setCallback(function() end)</code>.</li></ul>                 |

#### [summary](#summary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.ping:summary() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a string containing summary information about the ping process.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>a summary string for the current state of the ping process</li></ul>            |
| **Notes**                                            | <ul><li>The summary string will look similar to the following:</li></ul><p>~~~</p><p>5 packets transmitted, 5 packets received, 0.0 packet loss</p><p>round-trip min/avg/max = 2.282/4.133/4.926 ms</p><p>~~~</p><ul><li>The numer of packets received will match the number that has currently been sent, not necessarily the value returned by <a href="#count">hs.network.ping:count</a>.</li></ul>                 |

