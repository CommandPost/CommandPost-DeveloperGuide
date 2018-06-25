# [docs](index.md) » hs.network.reachability
---

This sub-module can be used to determine the reachability of a target host. A remote host is considered reachable when a data packet, sent by an application into the network stack, can leave the local device. Reachability does not guarantee that the data packet will actually be received by the host.

It is important to remember that this module works by determining if the computer has a route for network traffic bound to a specific destination.  An active internet connection provides a default route for any network that the host is not a member of, so care must be used when testing for specific VPN or local networks to avoid false positives.  Some examples follow:

This is a simple watcher which will be invoked whenever the computer's active internet connection changes state:
~~~
    hs.network.reachability.internet():setCallback(function(self, flags)
        if (flags & hs.network.reachability.flags.reachable) > 0 then
            -- a default route exists, so an active internet connection is present
        else
            -- no default route exists, so no active internet connection is present
        end
   end):start()
~~~

Note that when an active internet connection is up (reachable), any specific network test that does not include an address pair will be reachable, since internet reachability is defined as having a default route for all non-local networks.

A specific test for determining if an OpenVPN network is available.  This example requires knowing what the local computer's IP address on the VPN network is (OpenVPN does not set the `isDirect` flag) and has been tested with Tunnelblick.
~~~
    hs.network.reachability.forAddress("10.x.y.z"):setCallback(function(self, flags)
        -- note that because having an internet connection at all will show the remote network
        -- as "reachable", we instead look at whether or not our specific address is "local" instead
        if (flags & hs.network.reachability.flags.isLocalAddress) > 0 then
            -- VPN tunnel is up
        else
            -- VPN tunnel is down
        end
   end):start()
~~~

## API Overview
* Constants - Useful values which cannot be changed
 * [flags](#flags)
* Constructors - API calls which return an object, typically one that offers API methods
 * [forAddress](#foraddress)
 * [forAddressPair](#foraddresspair)
 * [forHostName](#forhostname)
 * [internet](#internet)
 * [linkLocal](#linklocal)
* Methods - API calls which can only be made on an object returned by a constructor
 * [setCallback](#setcallback)
 * [start](#start)
 * [status](#status)
 * [statusString](#statusstring)
 * [stop](#stop)

## API Documentation

### Constants

#### [flags](#flags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability.flags[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      |                                                                                          |

### Constructors

#### [forAddress](#foraddress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability.forAddress(address) -> reachabilityObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns a reachability object for the specified network address.                                                                                         |
| **Parameters**                                       | <ul><br /><li>address - a string or number representing an IPv4 or IPv6 network address to get or track reachability status for.  If the argument is a number, it is treated as the 32 bit numerical representation of an IPv4 address.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a reachability object for the specified network address.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>this object will reflect reachability status for any interface available on the computer.  To check for reachability from a specific interface, use <a href="#addressPair">hs.network.reachability.forAddressPair</a>.</li><br /></ul>                                             |

#### [forAddressPair](#foraddresspair)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability.forAddressPair(localAddress, remoteAddress) -> reachabilityObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns a reachability object for the specified network address from the specified localAddress.                                                                                         |
| **Parameters**                                       | <ul><br /><li>localAddress - a string or number representing a local IPv4 or IPv6 network address. If the address specified is not present on the computer, the remote address will be unreachable. * remoteAddress - a string or number representing an IPv4 or IPv6 network address to get or track reachability status for.  If the argument is a number, it is treated as the 32 bit numerical representation of an IPv4 address.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a reachability object for the specified network address.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>this object will reflect reachability status for a specific interface on the computer.  To check for reachability from any interface, use <a href="#address">hs.network.reachability.forAddress</a>. * this constructor can be used to test for a specific local network.</li><br /></ul>                                             |

#### [forHostName](#forhostname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability.forHostName(hostName) -> reachabilityObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns a reachability object for the specified host.                                                                                         |
| **Parameters**                                       | <ul><br /><li>hostName - a string containing the hostname of a machine to check or track the reachability status for.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a reachability object for the specified host.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>this object will reflect reachability status for any interface available on the computer. * this constructor relies on the hostname being resolvable, possibly through DNS, Bonjour, locally defined, etc.</li><br /></ul>                                             |

#### [internet](#internet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability.internet() -> reachabilityObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a reachability object for testing internet access                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a reachability object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This is equivalent to <code>hs.network.reachability.forAddress("0.0.0.0")</code> * This constructor assumes that a default route for IPv4 traffic is sufficient to determine internet access.  If you are on an IPv6 only network which does not also provide IPv4 route mapping, you should probably use something along the lines of <code>hs.network.reachability.forAddress("::")</code> instead.</li><br /></ul>                                             |

#### [linkLocal](#linklocal)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability.linkLocal() -> reachabilityObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a reachability object for testing IPv4 link local networking                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a reachability object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This is equivalent to <code>hs.network.reachability.forAddress("169.254.0.0")</code> * You can use this to determine if any interface has an IPv4 link local address (i.e. zero conf or local only networking) by checking the "isDirect" flag:   * <code>hs.network.reachability.linklocal():status() &amp; hs.network.reachability.flags.isDirect</code> * If the internet is reachable, then this network will also be reachable by default -- use the isDirect flag to ensure that the route is local.</li><br /></ul>                                             |

### Methods

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability:setCallback(function | nil) -> reachabilityObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set or remove the callback function for a reachability object                                                                                         |
| **Parameters**                                       | <ul><br /><li>a function or nil to set or remove the reachability object callback function</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the reachability object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The callback function will be invoked each time the status for the given reachability object changes.  The callback function should expect 2 arguments, the reachability object itself and a numeric representation of the reachability flags, and should not return anything. * This method just sets the callback function.  You can start or stop the watcher with <a href="#start">hs.network.reachability:start</a> or <a href="#stop">hs.network.reachability:stop</a></li><br /></ul>                                             |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability:start() -> reachabilityObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts watching the reachability object for changes and invokes the callback function (if any) when a change occurs.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the reachability object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The callback function should be specified with <a href="#setCallback">hs.network.reachability:setCallback</a>.</li><br /></ul>                                             |

#### [status](#status)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability:status() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the reachability status for the object                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a numeric representation of the reachability status</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The numeric representation is made up from a combination of the flags defined in <a href="#flags">hs.network.reachability.flags</a>.</li><br /></ul>                                             |

#### [statusString](#statusstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability:statusString() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a string representation of the reachability status for the object                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a string representation of the reachability status for the object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This is included primarily for debugging, but may be more useful when you just want a quick look at the reachability status for display or testing. * The string will be made up of the following flags:   * 't'|'-' indicates if the destination is reachable through a transient connection   * 'R'|'-' indicates if the destination is reachable   * 'c'|'-' indicates that a connection of some sort is required for the destination to be reachable   * 'C'|'-' indicates if the destination requires a connection which will be initiated when traffic to the destination is present   * 'i'|'-' indicates if the destination requires a connection which will require user activity to initiate   * 'D'|'-' indicates if the destination requires a connection which will be initiated on demand through the CFSocketStream interface   * 'l'|'-' indicates if the destination is actually a local address   * 'd'|'-' indicates if the destination is directly connected</li><br /></ul>                                             |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.reachability:stop() -> reachabilityObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops watching the reachability object for changes.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the reachability object</li><br /></ul>                                           |

