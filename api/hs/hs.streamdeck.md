# [docs](index.md) » hs.streamdeck
---

Configure/control an Elgato Stream Deck

Please note that in order for this module to work, the official Elgato Stream Deck app should not be running

This module would not have been possible without standing on the shoulders of others:
 * https://github.com/OpenStreamDeck/StreamDeckSharp
 * https://github.com/Lange/node-elgato-stream-deck
 * Hopper

## API Overview
* Functions - API calls offered directly by the extension
 * [discoveryCallback](#discoverycallback)
 * [getDevice](#getdevice)
 * [init](#init)
 * [numDevices](#numdevices)
* Methods - API calls which can only be made on an object returned by a constructor
 * [buttonCallback](#buttoncallback)
 * [firmwareVersion](#firmwareversion)
 * [reset](#reset)
 * [serialNumber](#serialnumber)
 * [setBrightness](#setbrightness)
 * [setButtonColor](#setbuttoncolor)
 * [setButtonImage](#setbuttonimage)

## API Documentation

### Functions

#### [discoveryCallback](#discoverycallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck.discoveryCallback(fn)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets/clears a callback for reacting to device discovery events                                                                                         |
| **Parameters**                                       |  * fn - A function that will be called when a Streaming Deck is connected or disconnected. It should take the following arguments:  * A boolean, true if a device was connected, false if a device was disconnected  * An hs.streamdeck object, being the device that was connected/disconnected                                       |
| **Returns**                                          |  * None                                                |

#### [getDevice](#getdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck.getDevice(num)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets an hs.streamdeck object for the specified device                                                                                         |
| **Parameters**                                       |  * num - A number that should be within the bounds of the number of connected devices                                       |
| **Returns**                                          |  * An hs.streamdeck object                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck.init(fn)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Stream Deck driver and sets a discovery callback                                                                                         |
| **Parameters**                                       |  * fn - A function that will be called when a Streaming Deck is connected or disconnected. It should take the following arguments:  * A boolean, true if a device was connected, false if a device was disconnected  * An hs.streamdeck object, being the device that was connected/disconnected                                       |
| **Returns**                                          |  * None                                                |
| **Notes**                                            |  * This function must be called before any other parts of this module are used                                                      |

#### [numDevices](#numdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck.numDevices()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the number of Stream Deck devices connected                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A number containing the number of Stream Deck devices attached to the system                                                |

### Methods

#### [buttonCallback](#buttoncallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck:buttonCallback(fn)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets/clears the button callback function for a deck                                                                                         |
| **Parameters**                                       |  * fn - A function to be called when a button is pressed/released on the stream deck. It should receive three arguments:  * The hs.streamdeck userdata object  * A number containing the button that was pressed/released  * A boolean indicating whether the button was pressed (true) or released (false)                                       |
| **Returns**                                          |  * The hs.streamdeck device                                                |

#### [firmwareVersion](#firmwareversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck:firmwareVersion()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the firmware version of a deck                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A string containing the firmware version of the deck                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck:reset()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resets a deck                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The hs.streamdec object                                                |

#### [serialNumber](#serialnumber)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck:serialNumber()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the serial number of a deck                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A string containing the serial number of the deck                                                |

#### [setBrightness](#setbrightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck:setBrightness(brightness)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the brightness of a deck                                                                                         |
| **Parameters**                                       |  * brightness - A whole number between 0 and 100 indicating the percentage brightness level to set                                       |
| **Returns**                                          |  * The hs.streamdeck device                                                |

#### [setButtonColor](#setbuttoncolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck:setButtonColor(button, color)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets a button on the deck to the specified color                                                                                         |
| **Parameters**                                       |  * button - A number (from 1 to 15) describing which button to set the color on * color - An hs.drawing.color object                                       |
| **Returns**                                          |  * The hs.streamdeck object                                                |

#### [setButtonImage](#setbuttonimage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.streamdeck:setButtonImage(button, image)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the image of a button on the deck                                                                                         |
| **Parameters**                                       |  * button - A number (from 1 to 15) describing which button to set the image for * image - An hs.image object                                       |
| **Returns**                                          |  * The hs.streamdeck object                                                |

