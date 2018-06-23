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
| **Parameters**                                       | <ul><li>callbackFn - the callback function to trigger.</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>The callback function should expect 2 argument and should not return anything:</li></ul><ul><li><code>devices</code> - A table containing the names of any physically connected MIDI devices as strings.</li></ul><ul><li><code>virtualDevices</code> - A table containing the names of any virtual MIDI devices as strings.</li></ul><ul><li>Example Usage:</li></ul><p>```</p><p>hs.midi.deviceCallback(function(devices, virtualDevices)</p><pre><code>    print(hs.inspect(devices))</code></pre><pre><code>    print(hs.inspect(virtualDevices))</code></pre><p>end)</p><p>```</p>                 |

#### [devices](#devices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.devices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table of currently connected physical MIDI devices.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A table containing the names of any physically connected MIDI devices as strings.</li></ul>            |

#### [virtualSources](#virtualsources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.virtualSources() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table of currently available Virtual MIDI sources. This includes devices, such as Native Instruments controllers which present as virtual endpoints rather than physical devices.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A table containing the names of any virtual MIDI sources as strings.</li></ul>            |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.new(deviceName) -> `hs.midi` object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li>deviceName - A string containing the device name of the MIDI device. A valid device name can be found by checking <code>hs.midi.getDevices()</code> and/or <code>hs.midi.virtualSources()</code>.</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.midi</code> object or <code>nil</code> if an error occured.</li></ul>            |
| **Notes**                                            | <ul><li>Example Usage:</li></ul><p><code>hs.midi.new(hs.midi.devices()[1])</code></p>                 |

#### [newVirtualSource](#newvirtualsource)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi.newVirtualSource(virtualSource) -> `hs.midi` object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li>virtualSource - A string containing the virtual source name of the MIDI device. A valid virtual source name can be found by checking <code>hs.midi.virtualSources()</code>.</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.midi</code> object or <code>nil</code> if an error occured.</li></ul>            |
| **Notes**                                            | <ul><li>Example Usage:</li></ul><p><code>hs.midi.new(hs.midi.virtualSources()[1])</code></p>                 |

### Methods

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:callback(callbackFn | nil)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or removes a callback function for the `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li><code>callbackFn</code> - a function to set as the callback for this <code>hs.midi</code> object.  If the value provided is <code>nil</code>, any currently existing callback function is removed.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.midi</code> object</li></ul>            |
| **Notes**                                            | <ul><li>Most MIDI keyboards produce a <code>noteOn</code> when you press a key, then <code>noteOff</code> when you release. However, some MIDI keyboards will return a <code>noteOn</code> with 0 <code>velocity</code> instead of <code>noteOff</code>, so you will recieve two <code>noteOn</code> commands for every key press/release.</li></ul><ul><li>The callback function should expect 8 arguments and should not return anything:</li></ul><ul><li><code>object</code>       - The <code>hs.midi</code> object.</li></ul><ul><li><code>deviceName</code>   - The device name as a string.</li></ul><ul><li><code>commandType</code>  - Type of MIDI message as defined as a string. See <code>hs.midi.commandTypes[]</code> for a list of possibilities.</li></ul><ul><li><code>description</code>  - Description of the event as a string. This is only really useful for debugging.</li></ul><ul><li><code>metadata</code>     - A table of data for the MIDI command (see below).</li></ul>                 |

#### [displayName](#displayname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:displayName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the display name of a `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The name as a string.</li></ul>            |

#### [identityRequest](#identityrequest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:identityRequest() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends an Identity Request message to the `hs.midi` device. You can use `hs.midi:callback()` to receive the `systemExclusive` response.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>Example Usage:</li></ul><p>```</p><p>midiDevice = hs.midi.new(hs.midi.devices()[3])</p><pre><code>                    print("object: " .. tostring(object))</code></pre><pre><code>                    print("deviceName: " .. deviceName)</code></pre><pre><code>                    print("commandType: " .. commandType)</code></pre><pre><code>                    print("description: " .. description)</code></pre><pre><code>                    print("metadata: " .. hs.inspect(metadata))</code></pre><pre><code>                  end)</code></pre><p>```</p>                 |

#### [isOnline](#isonline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:isOnline() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the online status of a `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if online, otherwise <code>false</code></li></ul>            |

#### [isVirtual](#isvirtual)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:isVirtual() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if an `hs.midi` object is virtual, otherwise `false`.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if virtual, otherwise <code>false</code></li></ul>            |

#### [manufacturer](#manufacturer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:manufacturer() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the manufacturer name of a `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The manufacturer name as a string.</li></ul>            |

#### [model](#model)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:model() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the model name of a `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The model name as a string.</li></ul>            |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:name() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of a `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The name as a string.</li></ul>            |

#### [sendCommand](#sendcommand)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:sendCommand(commandType, metadata) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends a command to the `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li><code>commandType</code>    - The type of command you want to send as a string. See <code>hs.midi.commandTypes[]</code>.</li></ul><ul><li><code>metadata</code>       - A table of data for the MIDI command (see notes below).</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if successful, otherwise <code>false</code></li></ul>            |
| **Notes**                                            | <ul><li>The <code>metadata</code> table can accept following, depending on the <code>commandType</code> supplied:</li></ul>                 |

#### [sendSysex](#sendsysex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:sendSysex(command) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends a System Exclusive Command to the `hs.midi` object.                                                                                         |
| **Parameters**                                       | <ul><li><code>command</code> - The system exclusive command you wish to send as a string. White spaces in the string will be ignored.</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>Example Usage:</li></ul><p><code>midiDevice:sendSysex("f07e7f06 01f7")</code></p>                 |

#### [synthesize](#synthesize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.midi:synthesize([value]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set or display whether or not the MIDI device should synthesize audio on your computer.                                                                                         |
| **Parameters**                                       | <ul><li>[value] - <code>true</code> if you want to synthesize audio, otherwise <code>false</code>.</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if enabled otherwise <code>false</code></li></ul>            |

