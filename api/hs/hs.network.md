# [docs](index.md) » hs.network
---

This module provides functions for inquiring about and monitoring changes to the network.

## Submodules
 * [hs.network.configuration](hs.network.configuration.md)
 * [hs.network.host](hs.network.host.md)
 * [hs.network.ping](hs.network.ping.md)
 * [hs.network.reachability](hs.network.reachability.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [addresses](#addresses)
 * [interfaceDetails](#interfacedetails)
 * [interfaceName](#interfacename)
 * [interfaces](#interfaces)
 * [primaryInterfaces](#primaryinterfaces)

## API Documentation

### Functions

#### [addresses](#addresses)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.addresses([interface, ...]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of the IPv4 and IPv6 addresses for the specified interfaces, or all interfaces if no arguments are given.                                                                                         |
| **Parameters**                                       | <ul><br /><li>interface, ... - The interface names to return the IP addresses for. It should be specified as one of the following:   * one or more interface names, separated by a comma   * if the first argument is a table, it is assumes to be a table containing a list of interfaces and this list is used instead, ignoring any additional arguments that may be provided   * if no arguments are specified, then the results of <a href="#interfaces">hs.network.interfaces</a> is used.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing a list of the IP addresses for the interfaces as determined by the arguments provided.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The order of the IP addresses returned is undefined. * If no arguments are provided, then this function returns the same results as <code>hs.host.addresses</code>, but does not block.</li><br /></ul>                                             |

#### [interfaceDetails](#interfacedetails)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.interfaceDetails([interface | favorIPv6]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns details about the specified interface or the primary interface if no interface is specified.                                                                                         |
| **Parameters**                                       | <ul><br /><li>interface - an optional string specifying the interface to retrieve details about.  Defaults to the primary interface if not specified. * favorIPv6 - an optional boolean specifying whether or not to prefer the primary IPv6 or the primary IPv4 interface if <code>interface</code> is not specified.  Defaults to false.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing key-value pairs describing interface details.  Returns an empty table if no primary interface can be determined. Logs an error and returns nil if there was a problem retrieving this information.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>When determining the primary interface, the <code>favorIPv6</code> flag only determines interface search order.  If you specify true for this flag, but no primary IPv6 interface exists (i.e. your DHCP server only provides an IPv4 address an IPv6 is limited to local only traffic), then the primary IPv4 interface will be used instead.</li><br /></ul>                                             |

#### [interfaceName](#interfacename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.interfaceName([interface | favorIPv6]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the user defined name for the specified interface or the primary interface if no interface is specified.                                                                                         |
| **Returns**                                          | <ul><br /><li>A string containing the user defined name for the interface, if one exists, or false if the interface does not have a user defined name. Logs an error and returns nil if there was a problem retrieving this information.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Only interfaces which show up in the System Preferences Network panel will have a user defined name.</li><br /></ul>                                             |

#### [interfaces](#interfaces)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.interfaces() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of interfaces currently active for the system.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing a list of the interfaces active for the system.  Logs an error and returns nil if there was a problem retrieving this information.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The names of the interfaces returned by this function correspond to the interface's BSD name, not the user defined name that shows up in the System Preferences's Network panel. * This function returns <em>all</em> interfaces, even ones used by the system that are not directly manageable by the user.</li><br /></ul>                                             |

#### [primaryInterfaces](#primaryinterfaces)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.network.primaryInterfaces() -> ipv4Interface, ipv6Interface` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the names of the primary IPv4 and IPv6 interfaces.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The name of the primary IPv4 interface or false if there isn't one, and the name of the IPv6 interface or false if there isn't one. Logs an error and returns a single nil if there was a problem retrieving this information.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The IPv4 and IPv6 interface names are often, but not always, the same.</li><br /></ul>                                             |

