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
| **Parameters**                                       | <ul><li>ip - A string containing the IP address of the MiLight WiFi bridge device. For convenience this can be the broadcast address of your network (e.g. 192.168.0.255)</li></ul><ul><li>port - An optional number containing the UDP port to talk to the bridge on. Defaults to 8899</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.milight</code> object</li></ul>            |
| **Notes**                                            | <ul><li>You can not use 255.255.255.255 as the IP address, to do so requires elevated privileges for the Hammerspoon process</li></ul>                 |

### Methods

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:delete()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deletes an `hs.milight` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [disco](#disco)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:disco() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Cycles through the disco modes                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>True if the command was sent correctly, otherwise false</li></ul>            |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:send(cmd[, value]) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends a command to the bridge                                                                                         |
| **Parameters**                                       | <ul><li>cmd - A command from the <code>hs.milight.cmd</code> table</li></ul><ul><li>value - An optional value, if appropriate for the command (defaults to 0x00)</li></ul>   |
| **Returns**                                          | <ul><li>True if the command was sent, otherwise false</li></ul>            |
| **Notes**                                            | <ul><li>This is a low level command, you typically should use a specific method for the operation you want to perform</li></ul>                 |

#### [zoneBrightness](#zonebrightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneBrightness(zone, value) -> integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets brightness for the specified zone                                                                                         |
| **Parameters**                                       | <ul><li>zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four</li></ul><ul><li>value - A number containing the brightness level to set, between <code>hs.milight.minBrightness</code> and <code>hs.milight.maxBrightness</code></li></ul>   |
| **Returns**                                          | <ul><li>A number containing the value that was sent to the WiFi bridge, or -1 if an error occurred</li></ul>            |

#### [zoneColor](#zonecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneColor(zone, value) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets RGB color for the specified zone                                                                                         |
| **Parameters**                                       | <ul><li>zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four</li></ul><ul><li>value - A number between 0 and 255 that represents a color</li></ul>   |
| **Returns**                                          | <ul><li>True if the command was sent correctly, otherwise false</li></ul>            |
| **Notes**                                            | <ul><li>The color value is not a normal RGB colour, but rather a lookup in an internal table in the light hardware. While any number between 0 and 255 is valid, there are some useful values worth knowing:</li></ul><ul><li>00 - Violet</li></ul><ul><li>16 - Royal Blue</li></ul><ul><li>32 - Baby Blue</li></ul><ul><li>48 - Aqua</li></ul><ul><li>64 - Mint Green</li></ul><ul><li>80 - Seafoam Green</li></ul><ul><li>96 - Green</li></ul><ul><li>112 - Lime Green</li></ul><ul><li>128 - Yellow</li></ul><ul><li>144 - Yellowy Orange</li></ul><ul><li>160 - Orange</li></ul><ul><li>176 - Red</li></ul><ul><li>194 - Pink</li></ul><ul><li>210 - Fuscia</li></ul><ul><li>226 - Lilac</li></ul><ul><li>240 - Lavendar</li></ul>                 |

#### [zoneOff](#zoneoff)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneOff(zone) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Turns off the specified zone                                                                                         |
| **Parameters**                                       | <ul><li>zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four</li></ul>   |
| **Returns**                                          | <ul><li>True if the command was sent correctly, otherwise false</li></ul>            |

#### [zoneOn](#zoneon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneOn(zone) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Turns on the specified zone                                                                                         |
| **Parameters**                                       | <ul><li>zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four</li></ul>   |
| **Returns**                                          | <ul><li>True if the command was sent correctly, otherwise false</li></ul>            |

#### [zoneWhite](#zonewhite)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.milight:zoneWhite(zone) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the specified zone to white                                                                                         |
| **Parameters**                                       | <ul><li>zone - A number specifying which zone to operate on. 0 for all zones, 1-4 for zones one through four</li></ul>   |
| **Returns**                                          | <ul><li>True if the command was sent correctly, otherwise false</li></ul>            |

