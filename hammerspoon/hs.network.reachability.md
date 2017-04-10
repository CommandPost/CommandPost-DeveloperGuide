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
** [flags[]](#flags[])
* Constructors - API calls which return an object, typically one that offers API methods
** [forAddress](#forAddress)
** [forAddressPair](#forAddressPair)
** [forHostName](#forHostName)
** [internet](#internet)
** [linkLocal](#linkLocal)
* Methods - API calls which can only be made on an object returned by a constructor
** [setCallback](#setCallback)
** [start](#start)
** [status](#status)
** [statusString](#statusString)
** [stop](#stop)

## API Documentation

### Constants

#### [flags[]](#flags[])
| | |
|-|-|
| Signature   | hs.network.reachability.flags[]  |
| Type        | Constant |
| Description |  |
  A table containing the numeric value for the possible flags returned by the [hs.network.reachability:status](#status) method or in the `flags` parameter of the callback function.
    * transientConnection  - indicates if the destination is reachable through a transient connection
    * reachable            - indicates if the destination is reachable
    * connectionRequired   - indicates that a connection of some sort is required for the destination to be reachable
    * connectionOnTraffic  - indicates if the destination requires a connection which will be initiated when traffic to the destination is present
    * interventionRequired - indicates if the destination requires a connection which will require user activity to initiate
    * connectionOnDemand   - indicates if the destination requires a connection which will be initiated on demand through the CFSocketStream interface
    * isLocalAddress       - indicates if the destination is actually a local address
    * isDirect             - indicates if the destination is directly connected

### Constructors

#### [forAddress](#forAddress)
| | |
|-|-|
| Signature   | hs.network.reachability.forAddress(address) -> reachabilityObject  |
| Type        | Constructor |
| Description | Returns a reachability object for the specified network address. |
| Parameters |  * address - a string or number representing an IPv4 or IPv6 network address to get or track reachability status for.  If the argument is a number, it is treated as the 32 bit numerical representation of an IPv4 address. | | Returns |  * a reachability object for the specified network address. | | Notes |  * this object will reflect reachability status for any interface available on the computer.  To check for reachability from a specific interface, use [hs.network.reachability.forAddressPair](#addressPair). | 
#### [forAddressPair](#forAddressPair)
| | |
|-|-|
| Signature   | hs.network.reachability.forAddressPair(localAddress, remoteAddress) -> reachabilityObject  |
| Type        | Constructor |
| Description | Returns a reachability object for the specified network address from the specified localAddress. |
| Parameters |  * localAddress - a string or number representing a local IPv4 or IPv6 network address. If the address specified is not present on the computer, the remote address will be unreachable. * remoteAddress - a string or number representing an IPv4 or IPv6 network address to get or track reachability status for.  If the argument is a number, it is treated as the 32 bit numerical representation of an IPv4 address. | | Returns |  * a reachability object for the specified network address. | | Notes |  * this object will reflect reachability status for a specific interface on the computer.  To check for reachability from any interface, use [hs.network.reachability.forAddress](#address). * this constructor can be used to test for a specific local network. | 
#### [forHostName](#forHostName)
| | |
|-|-|
| Signature   | hs.network.reachability.forHostName(hostName) -> reachabilityObject  |
| Type        | Constructor |
| Description | Returns a reachability object for the specified host. |
| Parameters |  * hostName - a string containing the hostname of a machine to check or track the reachability status for. | | Returns |  * a reachability object for the specified host. | | Notes |  * this object will reflect reachability status for any interface available on the computer. * this constructor relies on the hostname being resolvable, possibly through DNS, Bonjour, locally defined, etc. | 
#### [internet](#internet)
| | |
|-|-|
| Signature   | hs.network.reachability.internet() -> reachabilityObject  |
| Type        | Constructor |
| Description | Creates a reachability object for testing internet access |
| Parameters |  * None | | Returns |  * a reachability object | | Notes |  * This is equivalent to `hs.network.reachability.forAddress("0.0.0.0")` * This constructor assumes that a default route for IPv4 traffic is sufficient to determine internet access.  If you are on an IPv6 only network which does not also provide IPv4 route mapping, you should probably use something along the lines of `hs.network.reachability.forAddress("::")` instead. | 
#### [linkLocal](#linkLocal)
| | |
|-|-|
| Signature   | hs.network.reachability.linkLocal() -> reachabilityObject  |
| Type        | Constructor |
| Description | Creates a reachability object for testing IPv4 link local networking |
| Parameters |  * None | | Returns |  * a reachability object | | Notes |  * This is equivalent to `hs.network.reachability.forAddress("169.254.0.0")` * You can use this to determine if any interface has an IPv4 link local address (i.e. zero conf or local only networking) by checking the "isDirect" flag:   * `hs.network.reachability.linklocal():status() & hs.network.reachability.flags.isDirect` * If the internet is reachable, then this network will also be reachable by default -- use the isDirect flag to ensure that the route is local. | 
### Methods

#### [setCallback](#setCallback)
| | |
|-|-|
| Signature   | hs.network.reachability:setCallback(function | nil) -> reachabilityObject  |
| Type        | Method |
| Description | Set or remove the callback function for a reachability object |
| Parameters |  * a function or nil to set or remove the reachability object callback function | | Returns |  * the reachability object | | Notes |  * The callback function will be invoked each time the status for the given reachability object changes.  The callback function should expect 2 arguments, the reachability object itself and a numeric representation of the reachability flags, and should not return anything. * This method just sets the callback function.  You can start or stop the watcher with [hs.network.reachability:start](#start) or [hs.network.reachability:stop](#stop) | 
#### [start](#start)
| | |
|-|-|
| Signature   | hs.network.reachability:start() -> reachabilityObject  |
| Type        | Method |
| Description | Starts watching the reachability object for changes and invokes the callback function (if any) when a change occurs. |
| Parameters |  * None | | Returns |  * the reachability object | | Notes |  * The callback function should be specified with [hs.network.reachability:setCallback](#setCallback). | 
#### [status](#status)
| | |
|-|-|
| Signature   | hs.network.reachability:status() -> number  |
| Type        | Method |
| Description | Returns the reachability status for the object |
| Parameters |  * None | | Returns |  * a numeric representation of the reachability status | | Notes |  * The numeric representation is made up from a combination of the flags defined in [hs.network.reachability.flags](#flags). | 
#### [statusString](#statusString)
| | |
|-|-|
| Signature   | hs.network.reachability:statusString() -> string  |
| Type        | Method |
| Description | Returns a string representation of the reachability status for the object |
| Parameters |  * None | | Returns |  * a string representation of the reachability status for the object | | Notes |  * This is included primarily for debugging, but may be more useful when you just want a quick look at the reachability status for display or testing. * The string will be made up of the following flags:   * 't'|'-' indicates if the destination is reachable through a transient connection   * 'R'|'-' indicates if the destination is reachable   * 'c'|'-' indicates that a connection of some sort is required for the destination to be reachable   * 'C'|'-' indicates if the destination requires a connection which will be initiated when traffic to the destination is present   * 'i'|'-' indicates if the destination requires a connection which will require user activity to initiate   * 'D'|'-' indicates if the destination requires a connection which will be initiated on demand through the CFSocketStream interface   * 'l'|'-' indicates if the destination is actually a local address   * 'd'|'-' indicates if the destination is directly connected | 
#### [stop](#stop)
| | |
|-|-|
| Signature   | hs.network.reachability:stop() -> reachabilityObject  |
| Type        | Method |
| Description | Stops watching the reachability object for changes. |
| Parameters |  * None | | Returns |  * the reachability object | 