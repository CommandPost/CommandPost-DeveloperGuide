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
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the storeObject</li><br /></ul>                                           |

### Methods

#### [computerName](#computername)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:computerName() -> name, encoding` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of the computeras specified in the Sharing Preferences, and its string encoding                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>name     - the computer name * encoding - the encoding type</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>You can also retrieve this information as key-value pairs with <code>hs.network.configuration:contents("Setup:/System")</code></li><br /></ul>                                             |

#### [consoleUser](#consoleuser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:consoleUser() -> name, uid, gid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of the user currently logged into the system, including the users id and primary group id                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>name - the user name * uid  - the user ID for the user * gid  - the user's primary group ID</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>You can also retrieve this information as key-value pairs with <code>hs.network.configuration:contents("State:/Users/ConsoleUser")</code></li><br /></ul>                                             |

#### [contents](#contents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:contents([keys], [pattern]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return the contents of the store for the specified keys or keys matching the specified pattern(s)                                                                                         |
| **Parameters**                                       | <ul><br /><li>keys    - a string or table of strings containing the keys or patterns of keys, if <code>pattern</code> is true.  Defaults to all keys. * pattern - a boolean indicating wether or not the string(s) provided are to be considered regular expression patterns (true) or literal strings to match (false).  Defaults to false.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table of key-value pairs from the dynamic store which match the specified keys or key patterns.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>if no parameters are provided, then all key-value pairs in the dynamic store are returned.</li><br /></ul>                                             |

#### [dhcpInfo](#dhcpinfo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:dhcpInfo([serviceID]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return the DHCP information for the specified service or the primary service if no parameter is specified.                                                                                         |
| **Parameters**                                       | <ul><br /><li>serviceID - an optional string contining the service ID of the interface for which to return DHCP info.  If this parameter is not provided, then the default (primary) service is queried.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table containing DHCP information including lease time and DHCP options</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>a list of possible Service ID's can be retrieved with <code>hs.network.configuration:contents("Setup:/Network/Global/IPv4")</code> * generates an error if the service ID is invalid or was not assigned an IP address via DHCP.</li><br /></ul>                                             |

#### [hostname](#hostname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:hostname() -> name` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current local host name for the computer                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>name - the local host name</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>You can also retrieve this information as key-value pairs with <code>hs.network.configuration:contents("Setup:/System")</code></li><br /></ul>                                             |

#### [keys](#keys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:keys([keypattern]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return the keys in the dynamic store which match the specified pattern                                                                                         |
| **Parameters**                                       | <ul><br /><li>keypattern - a regular expression specifying which keys to return (defaults to ".*", or all keys)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table of keys from the dynamic store.</li><br /></ul>                                           |

#### [location](#location)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:location() -> location` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current location identifier                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>location - the UUID for the currently active network location</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>You can also retrieve this information as key-value pairs with <code>hs.network.configuration:contents("Setup:")</code> * If you have different locations defined in the Network preferences panel, this can be used to determine the currently active location.</li><br /></ul>                                             |

#### [locations](#locations)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:locations() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns all configured locations                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table of key-value pairs mapping location UUIDs to their names</li><br /></ul>                                           |

#### [monitorKeys](#monitorkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:monitorKeys([keys], [pattern]) -> storeObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specify the key(s) or key pattern(s) to monitor for changes.                                                                                         |
| **Parameters**                                       | <ul><br /><li>keys    - a string or table of strings containing the keys or patterns of keys, if <code>pattern</code> is true.  Defaults to all keys. * pattern - a boolean indicating wether or not the string(s) provided are to be considered regular expression patterns (true) or literal strings to match (false).  Defaults to false.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the store Object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>if no parameters are provided, then all key-value pairs in the dynamic store are monitored for changes.</li><br /></ul>                                             |

#### [proxies](#proxies)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:proxies() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns information about the currently active proxies, if any                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table of key-value pairs describing the current proxies in effect, both globally, and scoped to specific interfaces.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>You can also retrieve this information as key-value pairs with <code>hs.network.configuration:contents("State:/Network/Global/Proxies")</code></li><br /></ul>                                             |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:setCallback(function | nil) -> storeObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set or remove the callback function for a store object                                                                                         |
| **Parameters**                                       | <ul><br /><li>a function or nil to set or remove the store object callback function</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the store object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The callback function will be invoked each time a monitored key changes value and the callback function should accept two parameters: the storeObject itself, and an array of the keys which contain values that have changed. * This method just sets the callback function.  You specify which keys to watch with <a href="#monitorKeys">hs.network.configuration:monitorKeys</a> and start or stop the watcher with <a href="#start">hs.network.configuration:start</a> or <a href="#stop">hs.network.configuartion:stop</a></li><br /></ul>                                             |

#### [setLocation](#setlocation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:setLocation(location) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Switches to a new location                                                                                         |
| **Parameters**                                       | <ul><br /><li>location - string containing name or UUID of new location</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>bool - true if the location was successfully changed, false if there was an error</li><br /></ul>                                           |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:start() -> storeObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts watching the store object for changes to the monitored keys and invokes the callback function (if any) when a change occurs.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the store object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The callback function should be specified with <a href="#setCallback">hs.network.configuration:setCallback</a> and the keys to monitor should be specified with <a href="#monitorKeys">hs.network.configuration:monitorKeys</a>.</li><br /></ul>                                             |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.configuration:stop() -> storeObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops watching the store object for changes.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the store object</li><br /></ul>                                           |

