# [docs](index.md) » hs.milight
---

Simple controls for the MiLight LED WiFi bridge (also known as LimitlessLED and EasyBulb)

## API Overview
* Constants - Useful values which cannot be changed
 * [maxBrightness](#maxbrightness)
 * [minBrightness](#minbrightness)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [delete](#delete)
 * [disco](#disco)
 * [send](#send)
 * [zoneBrightness](#zonebrightness)
 * [zoneColor](#zonecolor)
 * [zoneOff](#zoneoff)
 * [zoneOn](#zoneon)
 * [zoneWhite](#zonewhite)

## API Documentation

### Constants

#### [maxBrightness](#maxbrightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight.maxBrightness` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Specifies the maximum brightness value that can be used. Defaults to 25                                                                                         |

#### [minBrightness](#minbrightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight.minBrightness` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Specifies the minimum brightness value that can be used. Defaults to 0                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight.new(ip[, port]) -> bridge` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new bridge object, which will be connected to the supplied IP address and port                                                                                         |
| **Parameters**                                       |  * ip - A string containing the IP address of the MiLight WiFi bridge device. For convenience this can be the broadcast address of your network (e.g. 192.168.0.255) * port - An optional number containing the UDP port to talk to the bridge on. Defaults to 8899                                       |
| **Returns**                                          |  * An `hs.milight` object                                                |
| **Notes**                                            |  * You can not use 255.255.255.255 as the IP address, to do so requires elevated privileges for the Hammerspoon process                                                      |

### Methods

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:delete()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deletes an `hs.milight` object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [disco](#disco)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:disco() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Cycles through the disco modes                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * True if the command was sent correctly, otherwise false                                                |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:send(cmd[, value]) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends a command to the bridge                                                                                         |
| **Parameters**                                       |  * cmd - A command from the `hs.milight.cmd` table * value - An optional value, if appropriate for the command (defaults to 0x00)                                       |
| **Returns**                                          |  * True if the command was sent, otherwise false                                                |
| **Notes**                                            |  * This is a low level command, you typically should use a specific method for the operation you want to perform                                                      |

#### [zoneBrightness](#zonebrightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneBrightness(zone, value) -> integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets brightness for the specified zone                                                                                         |
| **Parameters**                                       |  * zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four * value - A number containing the brightness level to set, between `hs.milight.minBrightness` and `hs.milight.maxBrightness`                                       |
| **Returns**                                          |  * A number containing the value that was sent to the WiFi bridge, or -1 if an error occurred                                                |

#### [zoneColor](#zonecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneColor(zone, value) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets RGB color for the specified zone                                                                                         |
| **Parameters**                                       |  * zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four * value - A number between 0 and 255 that represents a color                                       |
| **Returns**                                          |  * True if the command was sent correctly, otherwise false                                                |
| **Notes**                                            |  * The color value is not a normal RGB colour, but rather a lookup in an internal table in the light hardware. While any number between 0 and 255 is valid, there are some useful values worth knowing:  * 00 - Violet  * 16 - Royal Blue  * 32 - Baby Blue  * 48 - Aqua  * 64 - Mint Green  * 80 - Seafoam Green  * 96 - Green  * 112 - Lime Green  * 128 - Yellow  * 144 - Yellowy Orange  * 160 - Orange  * 176 - Red  * 194 - Pink  * 210 - Fuscia  * 226 - Lilac  * 240 - Lavendar                                                      |

#### [zoneOff](#zoneoff)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneOff(zone) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Turns off the specified zone                                                                                         |
| **Parameters**                                       |  * zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four                                       |
| **Returns**                                          |  * True if the command was sent correctly, otherwise false                                                |

#### [zoneOn](#zoneon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneOn(zone) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Turns on the specified zone                                                                                         |
| **Parameters**                                       |  * zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four                                       |
| **Returns**                                          |  * True if the command was sent correctly, otherwise false                                                |

#### [zoneWhite](#zonewhite)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneWhite(zone) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the specified zone to white                                                                                         |
| **Parameters**                                       |  * zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four                                       |
| **Returns**                                          |  * True if the command was sent correctly, otherwise false                                                |

