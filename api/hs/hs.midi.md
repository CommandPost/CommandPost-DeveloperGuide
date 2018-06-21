# [docs](index.md) » hs.midi
---

MIDI Extension for Hammerspoon.

This extension supports listening, transmitting and synthesizing MIDI commands.

This extension was thrown together by [Chris Hocking](http://latenitefilms.com) for [CommandPost](http://commandpost.io).

This extension uses [MIKMIDI](https://github.com/mixedinkey-opensource/MIKMIDI), an easy-to-use Objective-C MIDI library created by Andrew Madsen and developed by him and Chris Flesner of [Mixed In Key](http://www.mixedinkey.com/).

MIKMIDI LICENSE:
Copyright (c) 2013 Mixed In Key, LLC.
Original author: [Andrew R. Madsen](https://github.com/armadsen) (andrew@mixedinkey.com)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## API Overview
* Constants - Useful values which cannot be changed
 * [commandTypes](#commandtypes)
* Functions - API calls offered directly by the extension
 * [deviceCallback](#devicecallback)
 * [devices](#devices)
 * [virtualSources](#virtualsources)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [newVirtualSource](#newvirtualsource)
* Methods - API calls which can only be made on an object returned by a constructor
 * [callback](#callback)
 * [displayName](#displayname)
 * [identityRequest](#identityrequest)
 * [isOnline](#isonline)
 * [isVirtual](#isvirtual)
 * [manufacturer](#manufacturer)
 * [model](#model)
 * [name](#name)
 * [sendCommand](#sendcommand)
 * [sendSysex](#sendsysex)
 * [synthesize](#synthesize)

## API Documentation

### Constants

#### [commandTypes](#commandtypes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.commandTypes[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      |                                                                                          |

### Functions

#### [deviceCallback](#devicecallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.deviceCallback(callbackFn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | A callback that's triggered when a physical or virtual MIDI device is added or removed from the system.                                                                                         |
| **Parameters**                                       |  * callbackFn - the callback function to trigger.                                       |
| **Returns**                                          |  * None                                                |
| **Notes**                                            |  * The callback function should expect 2 argument and should not return anything:   * `devices` - A table containing the names of any physically connected MIDI devices as strings.   * `virtualDevices` - A table containing the names of any virtual MIDI devices as strings. * Example Usage:   ```   hs.midi.deviceCallback(function(devices, virtualDevices)        print(hs.inspect(devices))        print(hs.inspect(virtualDevices))   end)   ```                                                      |

#### [devices](#devices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.devices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table of currently connected physical MIDI devices.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the names of any physically connected MIDI devices as strings.                                                |

#### [virtualSources](#virtualsources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.virtualSources() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table of currently available Virtual MIDI sources. This includes devices, such as Native Instruments controllers which present as virtual endpoints rather than physical devices.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the names of any virtual MIDI sources as strings.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.new(deviceName) -> `hs.midi` object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * deviceName - A string containing the device name of the MIDI device. A valid device name can be found by checking `hs.midi.getDevices()` and/or `hs.midi.virtualSources()`.                                       |
| **Returns**                                          |  * An `hs.midi` object or `nil` if an error occured.                                                |
| **Notes**                                            |  * Example Usage:   `hs.midi.new(hs.midi.devices()[1])`                                                      |

#### [newVirtualSource](#newvirtualsource)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.newVirtualSource(virtualSource) -> `hs.midi` object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * virtualSource - A string containing the virtual source name of the MIDI device. A valid virtual source name can be found by checking `hs.midi.virtualSources()`.                                       |
| **Returns**                                          |  * An `hs.midi` object or `nil` if an error occured.                                                |
| **Notes**                                            |  * Example Usage:   `hs.midi.new(hs.midi.virtualSources()[1])`                                                      |

### Methods

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:callback(callbackFn | nil)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or removes a callback function for the `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * `callbackFn` - a function to set as the callback for this `hs.midi` object.  If the value provided is `nil`, any currently existing callback function is removed.                                       |
| **Returns**                                          |  * The `hs.midi` object                                                |
| **Notes**                                            |  * Most MIDI keyboards produce a `noteOn` when you press a key, then `noteOff` when you release. However, some MIDI keyboards will return a `noteOn` with 0 `velocity` instead of `noteOff`, so you will recieve two `noteOn` commands for every key press/release. * The callback function should expect 8 arguments and should not return anything:   * `object`       - The `hs.midi` object.   * `deviceName`   - The device name as a string.   * `commandType`  - Type of MIDI message as defined as a string. See `hs.midi.commandTypes[]` for a list of possibilities.   * `description`  - Description of the event as a string. This is only really useful for debugging.   * `metadata`     - A table of data for the MIDI command (see below).                                                      |

#### [displayName](#displayname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:displayName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the display name of a `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The name as a string.                                                |

#### [identityRequest](#identityrequest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:identityRequest() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends an Identity Request message to the `hs.midi` device. You can use `hs.midi:callback()` to receive the `systemExclusive` response.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |
| **Notes**                                            |  * Example Usage:  ```  midiDevice = hs.midi.new(hs.midi.devices()[3])  midiDevice:callback(function(object, deviceName, commandType, description, metadata)                        print("object: " .. tostring(object))                        print("deviceName: " .. deviceName)                        print("commandType: " .. commandType)                        print("description: " .. description)                        print("metadata: " .. hs.inspect(metadata))                      end)  midiDevice:identityRequest()  ```                                                      |

#### [isOnline](#isonline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:isOnline() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the online status of a `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if online, otherwise `false`                                                |

#### [isVirtual](#isvirtual)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:isVirtual() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if an `hs.midi` object is virtual, otherwise `false`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if virtual, otherwise `false`                                                |

#### [manufacturer](#manufacturer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:manufacturer() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the manufacturer name of a `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The manufacturer name as a string.                                                |

#### [model](#model)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:model() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the model name of a `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The model name as a string.                                                |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:name() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of a `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The name as a string.                                                |

#### [sendCommand](#sendcommand)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:sendCommand(commandType, metadata) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends a command to the `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * `commandType`    - The type of command you want to send as a string. See `hs.midi.commandTypes[]`. * `metadata`       - A table of data for the MIDI command (see notes below).                                       |
| **Returns**                                          |  * `true` if successful, otherwise `false`                                                |
| **Notes**                                            |  * The `metadata` table can accept following, depending on the `commandType` supplied:                                                      |

#### [sendSysex](#sendsysex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:sendSysex(command) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends a System Exclusive Command to the `hs.midi` object.                                                                                         |
| **Parameters**                                       |  * `command` - The system exclusive command you wish to send as a string. White spaces in the string will be ignored.                                       |
| **Returns**                                          |  * None                                                |
| **Notes**                                            |  * Example Usage:   ```midiDevice:sendSysex("f07e7f06 01f7")```                                                      |

#### [synthesize](#synthesize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:synthesize([value]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set or display whether or not the MIDI device should synthesize audio on your computer.                                                                                         |
| **Parameters**                                       |  * [value] - `true` if you want to synthesize audio, otherwise `false`.                                       |
| **Returns**                                          |  * `true` if enabled otherwise `false`                                                |

