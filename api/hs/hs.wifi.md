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
| **Parameters**                                       |  * network - A string containing the SSID of the network to associate to * passphrase - A string containing the passphrase of the network * interface - An optional string containing the name of an interface (see [hs.wifi.interfaces](#interfaces)). If not present, the default system WLAN device will be used                                       |
| **Returns**                                          |  * A boolean, true if the network was joined successfully, false if an error occurred                                                |
| **Notes**                                            |  * Enterprise WiFi networks are not currently supported. Please file an issue on GitHub if you need support for enterprise networks * This function blocks Hammerspoon until the operation is completed * If multiple access points are available with the same SSID, one will be chosen at random to connect to                                                      |

#### [availableNetworks](#availablenetworks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.availableNetworks([interface]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a list of available WiFi networks                                                                                         |
| **Parameters**                                       |  * interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.                                       |
| **Returns**                                          |  * A table containing the names of all visible WiFi networks                                                |
| **Notes**                                            |  * WARNING: This function will block all Lua execution until the scan has completed. It's probably not very sensible to use this function very much, if at all.                                                      |

#### [currentNetwork](#currentnetwork)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.currentNetwork([interface]) -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the current WiFi network                                                                                         |
| **Parameters**                                       |  * interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.                                       |
| **Returns**                                          |  * A string containing the SSID of the WiFi network currently joined, or nil if no there is no WiFi connection                                                |

#### [disassociate](#disassociate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.disassociate([interface]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disconnect the interface from its current network.                                                                                         |
| **Parameters**                                       |  * interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.                                       |
| **Returns**                                          |  * None                                                |

#### [interfaceDetails](#interfacedetails)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.interfaceDetails([interface]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table containing details about the wireless interface.                                                                                         |
| **Parameters**                                       |  * interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.                                       |
| **Returns**                                          |  * A table containing details about the interface.  The table will contain the following keys:   * active            - The interface has its corresponding network service enabled.   * activePHYMode     - The current active PHY mode for the interface.   * bssid             - The current basic service set identifier (BSSID) for the interface.   * cachedScanResults - A table containing the networks currently in the scan cache for the WLAN interface.  See [hs.wifi.backgroundScan](#backgroundScan) for details on the table format.   * configuration     - A table containing the current configuration for the given WLAN interface.  This table will contain the following keys:     * networkProfiles                    - A table containing an array of known networks for the interface.  Entries in the array will each contain the following keys:       * ssid     - The service set identifier (SSID) for the network profile.       * ssidData - The service set identifier (SSID) for the network, returned as data (1-32 octets).       * security - The security mode for the network profile.     * rememberJoinedNetworks             - A boolean flag indicating whether or not the AirPort client will remember all joined networks.     * requireAdministratorForAssociation - A boolean flag indicating whether or not changing the wireless network requires an Administrator password.     * requireAdministratorForIBSSMode    - A boolean flag indicating whether or not creating an IBSS (Ad Hoc) network requires an Administrator password.     * requireAdministratorForPower       - A boolean flag indicating whether or not changing the wireless power state requires an Administrator password.   * countryCode       - The current country code (ISO/IEC 3166-1:1997) for the interface.   * hardwareAddress   - The hardware media access control (MAC) address for the interface.   * interface         - The BSD name of the interface.   * interfaceMode     - The current mode for the interface.   * noise             - The current aggregate noise measurement (dBm) for the interface.   * power             - Whether or not the interface is currently powered on.   * rssi              - The current aggregate received signal strength indication (RSSI) measurement (dBm) for the interface.   * security          - The current security mode for the interface.   * ssid              - The current service set identifier (SSID) for the interface.   * ssidData          - The service set identifier (SSID) for the interface, returned as data (1-32 octets).   * supportedChannels - An array of channels supported by the interface for the active country code.  The array will contain entries with the following keys:     * band   - The channel band.     * number - The channel number.     * width  - The channel width.   * transmitPower     - The current transmit power (mW) for the interface. Returns 0 in the case of an error.   * transmitRate      - The current transmit rate (Mbps) for the interface.   * wlanChannel       - A table containing details about the channel the interface is on. The table will contain the following keys:     * band   - The channel band.     * number - The channel number.     * width  - The channel width.                                                |

#### [interfaces](#interfaces)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.interfaces() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of interface names for WLAN devices attached to the system                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * a table containing the names of all WLAN interfaces for this system.                                                |
| **Notes**                                            |  * For most systems, this will be one interface, but the result is still returned as an array.                                                      |

#### [setPower](#setpower)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.setPower(state, [interface]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Turns a wifi interface on or off                                                                                         |
| **Parameters**                                       |  * state - a boolean value indicating if the Wifi device should be powered on (true) or off (false). * interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.                                       |
| **Returns**                                          |  * True if the power change was successful, or false and an error string if an error occurred attempting to set the power state.  Returns nil if there is a problem attaching to the interface.                                                |

### Constructors

#### [backgroundScan](#backgroundscan)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.backgroundScan(fn, [interface]) -> scanObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Perform a scan for available wifi networks in the background (non-blocking)                                                                                         |
| **Parameters**                                       |  * fn        - the function to callback when the scan is completed. * interface - an optional interface name as listed in the results of [hs.wifi.interfaces](#interfaces).  If not present, the interface defaults to the systems default WLAN device.                                       |
| **Returns**                                          |  * returns a scan object                                                |
| **Notes**                                            |  * If you pass in nil as the callback function, the scan occurs but no callback function is called.  This can be useful to update the `cachedScanResults` entry returned by [hs.wifi.interfaceDetails](#interfaceDetails).                                                      |

### Methods

#### [isDone](#isdone)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi:isDone() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not a scan object has completed its scan for wireless networks.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * a boolean value indicating whether or not the scan has been completed.                                                |
| **Notes**                                            |  * This will be set whether or not an actual callback function was invoked.  This method can be checked to see if the cached data for the `cachedScanResults` entry returned by [hs.wifi.interfaceDetails](#interfaceDetails) has been updated.                                                      |

