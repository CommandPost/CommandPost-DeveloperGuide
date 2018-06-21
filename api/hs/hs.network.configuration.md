# [docs](index.md) » hs.network.configuration
---

This sub-module provides access to the current location set configuration settings in the system's dynamic store.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [open](#open)
* Methods - API calls which can only be made on an object returned by a constructor
 * [computerName](#computername)
 * [consoleUser](#consoleuser)
 * [contents](#contents)
 * [dhcpInfo](#dhcpinfo)
 * [hostname](#hostname)
 * [keys](#keys)
 * [location](#location)
 * [locations](#locations)
 * [monitorKeys](#monitorkeys)
 * [proxies](#proxies)
 * [setCallback](#setcallback)
 * [setLocation](#setlocation)
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constructors

#### [open](#open)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration.open() -> storeObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Opens a session to the dynamic store maintained by the System Configuration server.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the storeObject                                                |

### Methods

#### [computerName](#computername)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:computerName() -> name, encoding` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of the computeras specified in the Sharing Preferences, and its string encoding                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * name     - the computer name * encoding - the encoding type                                                |
| **Notes**                                            |  * You can also retrieve this information as key-value pairs with `hs.network.configuration:contents("Setup:/System")`                                                      |

#### [consoleUser](#consoleuser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:consoleUser() -> name, uid, gid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of the user currently logged into the system, including the users id and primary group id                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * name - the user name * uid  - the user ID for the user * gid  - the user's primary group ID                                                |
| **Notes**                                            |  * You can also retrieve this information as key-value pairs with `hs.network.configuration:contents("State:/Users/ConsoleUser")`                                                      |

#### [contents](#contents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:contents([keys], [pattern]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return the contents of the store for the specified keys or keys matching the specified pattern(s)                                                                                         |
| **Parameters**                                       |  * keys    - a string or table of strings containing the keys or patterns of keys, if `pattern` is true.  Defaults to all keys. * pattern - a boolean indicating wether or not the string(s) provided are to be considered regular expression patterns (true) or literal strings to match (false).  Defaults to false.                                       |
| **Returns**                                          |  * a table of key-value pairs from the dynamic store which match the specified keys or key patterns.                                                |
| **Notes**                                            |  * if no parameters are provided, then all key-value pairs in the dynamic store are returned.                                                      |

#### [dhcpInfo](#dhcpinfo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:dhcpInfo([serviceID]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return the DHCP information for the specified service or the primary service if no parameter is specified.                                                                                         |
| **Parameters**                                       |  * serviceID - an optional string contining the service ID of the interface for which to return DHCP info.  If this parameter is not provided, then the default (primary) service is queried.                                       |
| **Returns**                                          |  * a table containing DHCP information including lease time and DHCP options                                                |
| **Notes**                                            |  * a list of possible Service ID's can be retrieved with `hs.network.configuration:contents("Setup:/Network/Global/IPv4")` * generates an error if the service ID is invalid or was not assigned an IP address via DHCP.                                                      |

#### [hostname](#hostname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:hostname() -> name` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current local host name for the computer                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * name - the local host name                                                |
| **Notes**                                            |  * You can also retrieve this information as key-value pairs with `hs.network.configuration:contents("Setup:/System")`                                                      |

#### [keys](#keys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:keys([keypattern]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return the keys in the dynamic store which match the specified pattern                                                                                         |
| **Parameters**                                       |  * keypattern - a regular expression specifying which keys to return (defaults to ".*", or all keys)                                       |
| **Returns**                                          |  * a table of keys from the dynamic store.                                                |

#### [location](#location)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:location() -> location` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current location identifier                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * location - the UUID for the currently active network location                                                |
| **Notes**                                            |  * You can also retrieve this information as key-value pairs with `hs.network.configuration:contents("Setup:")` * If you have different locations defined in the Network preferences panel, this can be used to determine the currently active location.                                                      |

#### [locations](#locations)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:locations() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns all configured locations                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * a table of key-value pairs mapping location UUIDs to their names                                                |

#### [monitorKeys](#monitorkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:monitorKeys([keys], [pattern]) -> storeObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specify the key(s) or key pattern(s) to monitor for changes.                                                                                         |
| **Parameters**                                       |  * keys    - a string or table of strings containing the keys or patterns of keys, if `pattern` is true.  Defaults to all keys. * pattern - a boolean indicating wether or not the string(s) provided are to be considered regular expression patterns (true) or literal strings to match (false).  Defaults to false.                                       |
| **Returns**                                          |  * the store Object                                                |
| **Notes**                                            |  * if no parameters are provided, then all key-value pairs in the dynamic store are monitored for changes.                                                      |

#### [proxies](#proxies)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:proxies() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns information about the currently active proxies, if any                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * a table of key-value pairs describing the current proxies in effect, both globally, and scoped to specific interfaces.                                                |
| **Notes**                                            |  * You can also retrieve this information as key-value pairs with `hs.network.configuration:contents("State:/Network/Global/Proxies")`                                                      |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:setCallback(function | nil) -> storeObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set or remove the callback function for a store object                                                                                         |
| **Parameters**                                       |  * a function or nil to set or remove the store object callback function                                       |
| **Returns**                                          |  * the store object                                                |
| **Notes**                                            |  * The callback function will be invoked each time a monitored key changes value and the callback function should accept two parameters: the storeObject itself, and an array of the keys which contain values that have changed. * This method just sets the callback function.  You specify which keys to watch with [hs.network.configuration:monitorKeys](#monitorKeys) and start or stop the watcher with [hs.network.configuration:start](#start) or [hs.network.configuartion:stop](#stop)                                                      |

#### [setLocation](#setlocation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:setLocation(location) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Switches to a new location                                                                                         |
| **Parameters**                                       |  * location - string containing name or UUID of new location                                       |
| **Returns**                                          |  * bool - true if the location was successfully changed, false if there was an error                                                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:start() -> storeObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts watching the store object for changes to the monitored keys and invokes the callback function (if any) when a change occurs.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the store object                                                |
| **Notes**                                            |  * The callback function should be specified with [hs.network.configuration:setCallback](#setCallback) and the keys to monitor should be specified with [hs.network.configuration:monitorKeys](#monitorKeys).                                                      |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:stop() -> storeObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops watching the store object for changes.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the store object                                                |

