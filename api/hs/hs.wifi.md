# [docs](index.md) » hs.wifi
---

Inspect WiFi networks

## Submodules
 * [hs.wifi.watcher](hs.wifi.watcher.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [associate](#associate)
 * [availableNetworks](#availablenetworks)
 * [currentNetwork](#currentnetwork)
 * [disassociate](#disassociate)
 * [interfaceDetails](#interfacedetails)
 * [interfaces](#interfaces)
 * [setPower](#setpower)
* Constructors - API calls which return an object, typically one that offers API methods
 * [backgroundScan](#backgroundscan)
* Methods - API calls which can only be made on an object returned by a constructor
 * [isDone](#isdone)

## API Documentation

### Functions

#### [associate](#associate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.associate(network, passphrase[, interface]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Connect the interface to a wireless network                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">network - A string containing the SSID of the network to associate to</li><li markdown="1">passphrase - A string containing the passphrase of the network</li><li markdown="1">interface - An optional string containing the name of an interface (see [hs.wifi.interfaces](#interfaces)). If not present, the default system WLAN device will be used</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean, true if the network was joined successfully, false if an error occurred</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Enterprise WiFi networks are not currently supported. Please file an issue on GitHub if you need support for enterprise networks</li><li markdown="1">This function blocks Hammerspoon until the operation is completed</li><li markdown="1">If multiple access points are available with the same SSID, one will be chosen at random to connect to</li></ul>                |

#### [availableNetworks](#availablenetworks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.availableNetworks([interface]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a list of available WiFi networks                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table containing the names of all visible WiFi networks</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">WARNING: This function will block all Lua execution until the scan has completed. It's probably not very sensible to use this function very much, if at all.</li></ul>                |

#### [currentNetwork](#currentnetwork)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.currentNetwork([interface]) -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the current WiFi network                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing the SSID of the WiFi network currently joined, or nil if no there is no WiFi connection</li></ul>          |

#### [disassociate](#disassociate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.disassociate([interface]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disconnect the interface from its current network.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [interfaceDetails](#interfacedetails)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.interfaceDetails([interface]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table containing details about the wireless interface.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table containing details about the interface.  The table will contain the following keys:</li><li markdown="1">  active            - The interface has its corresponding network service enabled.</li><li markdown="1">  activePHYMode     - The current active PHY mode for the interface.</li><li markdown="1">  bssid             - The current basic service set identifier (BSSID) for the interface.</li><li markdown="1">  cachedScanResults - A table containing the networks currently in the scan cache for the WLAN interface.  See [hs.wifi.backgroundScan](#backgroundScan) for details on the table format.</li><li markdown="1">  configuration     - A table containing the current configuration for the given WLAN interface.  This table will contain the following keys:</li><li markdown="1">    networkProfiles                    - A table containing an array of known networks for the interface.  Entries in the array will each contain the following keys:</li><li markdown="1">      ssid     - The service set identifier (SSID) for the network profile.</li><li markdown="1">      ssidData - The service set identifier (SSID) for the network, returned as data (1-32 octets).</li><li markdown="1">      security - The security mode for the network profile.</li><li markdown="1">    rememberJoinedNetworks             - A boolean flag indicating whether or not the AirPort client will remember all joined networks.</li><li markdown="1">    requireAdministratorForAssociation - A boolean flag indicating whether or not changing the wireless network requires an Administrator password.</li><li markdown="1">    requireAdministratorForIBSSMode    - A boolean flag indicating whether or not creating an IBSS (Ad Hoc) network requires an Administrator password.</li><li markdown="1">    requireAdministratorForPower       - A boolean flag indicating whether or not changing the wireless power state requires an Administrator password.</li><li markdown="1">  countryCode       - The current country code (ISO/IEC 3166-1:1997) for the interface.</li><li markdown="1">  hardwareAddress   - The hardware media access control (MAC) address for the interface.</li><li markdown="1">  interface         - The BSD name of the interface.</li><li markdown="1">  interfaceMode     - The current mode for the interface.</li><li markdown="1">  noise             - The current aggregate noise measurement (dBm) for the interface.</li><li markdown="1">  power             - Whether or not the interface is currently powered on.</li><li markdown="1">  rssi              - The current aggregate received signal strength indication (RSSI) measurement (dBm) for the interface.</li><li markdown="1">  security          - The current security mode for the interface.</li><li markdown="1">  ssid              - The current service set identifier (SSID) for the interface.</li><li markdown="1">  ssidData          - The service set identifier (SSID) for the interface, returned as data (1-32 octets).</li><li markdown="1">  supportedChannels - An array of channels supported by the interface for the active country code.  The array will contain entries with the following keys:</li><li markdown="1">    band   - The channel band.</li><li markdown="1">    number - The channel number.</li><li markdown="1">    width  - The channel width.</li><li markdown="1">  transmitPower     - The current transmit power (mW) for the interface. Returns 0 in the case of an error.</li><li markdown="1">  transmitRate      - The current transmit rate (Mbps) for the interface.</li><li markdown="1">  wlanChannel       - A table containing details about the channel the interface is on. The table will contain the following keys:</li><li markdown="1">    band   - The channel band.</li><li markdown="1">    number - The channel number.</li><li markdown="1">    width  - The channel width.</li></ul>          |

#### [interfaces](#interfaces)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.interfaces() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of interface names for WLAN devices attached to the system                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a table containing the names of all WLAN interfaces for this system.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">For most systems, this will be one interface, but the result is still returned as an array.</li></ul>                |

#### [setPower](#setpower)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.setPower(state, [interface]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Turns a wifi interface on or off                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">state - a boolean value indicating if the Wifi device should be powered on (true) or off (false).</li><li markdown="1">interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">True if the power change was successful, or false and an error string if an error occurred attempting to set the power state.  Returns nil if there is a problem attaching to the interface.</li></ul>          |

### Constructors

#### [backgroundScan](#backgroundscan)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.backgroundScan(fn, [interface]) -> scanObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Perform a scan for available wifi networks in the background (non-blocking)                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">fn        - the function to callback when the scan is completed.</li><li markdown="1">interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">returns a scan object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">If you pass in nil as the callback function, the scan occurs but no callback function is called.  This can be useful to update the `cachedScanResults` entry returned by [hs.wifi.interfaceDetails](#interfaceDetails).</li></ul>                |

### Methods

#### [isDone](#isdone)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi:isDone() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not a scan object has completed its scan for wireless networks.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a boolean value indicating whether or not the scan has been completed.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This will be set whether or not an actual callback function was invoked.  This method can be checked to see if the cached data for the `cachedScanResults` entry returned by [hs.wifi.interfaceDetails](#interfaceDetails) has been updated.</li></ul>                |

