# [docs](index.md) » hs.audiodevice
---

Manipulate the system's audio devices

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## Submodules
 * [hs.audiodevice.datasource](hs.audiodevice.datasource.md)
 * [hs.audiodevice.watcher](hs.audiodevice.watcher.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [allDevices](#alldevices)
 * [allInputDevices](#allinputdevices)
 * [allOutputDevices](#alloutputdevices)
 * [current](#current)
 * [defaultInputDevice](#defaultinputdevice)
 * [defaultOutputDevice](#defaultoutputdevice)
 * [findDeviceByName](#finddevicebyname)
 * [findDeviceByUID](#finddevicebyuid)
 * [findInputByName](#findinputbyname)
 * [findInputByUID](#findinputbyuid)
 * [findOutputByName](#findoutputbyname)
 * [findOutputByUID](#findoutputbyuid)
* Methods - API calls which can only be made on an object returned by a constructor
 * [allInputDataSources](#allinputdatasources)
 * [allOutputDataSources](#alloutputdatasources)
 * [currentInputDataSource](#currentinputdatasource)
 * [currentOutputDataSource](#currentoutputdatasource)
 * [inputMuted](#inputmuted)
 * [inputVolume](#inputvolume)
 * [isInputDevice](#isinputdevice)
 * [isOutputDevice](#isoutputdevice)
 * [jackConnected](#jackconnected)
 * [muted](#muted)
 * [name](#name)
 * [outputMuted](#outputmuted)
 * [outputVolume](#outputvolume)
 * [setDefaultInputDevice](#setdefaultinputdevice)
 * [setDefaultOutputDevice](#setdefaultoutputdevice)
 * [setInputMuted](#setinputmuted)
 * [setInputVolume](#setinputvolume)
 * [setMuted](#setmuted)
 * [setOutputMuted](#setoutputmuted)
 * [setOutputtVolume](#setoutputtvolume)
 * [setVolume](#setvolume)
 * [supportsInputDataSources](#supportsinputdatasources)
 * [supportsOutputDataSources](#supportsoutputdatasources)
 * [transportType](#transporttype)
 * [uid](#uid)
 * [volume](#volume)
 * [watcherCallback](#watchercallback)
 * [watcherIsRunning](#watcherisrunning)
 * [watcherStart](#watcherstart)
 * [watcherStop](#watcherstop)

## API Documentation

### Functions

#### [allDevices](#alldevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.allDevices() -> hs.audiodevice[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of all connected devices                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of zero or more audio devices connected to the system</li></ul>          |

#### [allInputDevices](#allinputdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.allInputDevices() -> audio[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of all connected input devices.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of zero or more audio input devices connected to the system</li></ul>          |

#### [allOutputDevices](#alloutputdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.allOutputDevices() -> hs.audiodevice[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of all connected output devices                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of zero or more audio output devices connected to the system</li></ul>          |

#### [current](#current)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.current([input]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Fetch various metadata about the current default audio devices                                                                                         |
| **Parameters**                                       | <ul><li>output - An optional boolean, true to fetch information about the default input device, false for output device. Defaults to false</li></ul> |
| **Returns**                                          | <ul><li>A table with the following contents:</li><li>```lua</li><li>    {</li><li>        name = defaultOutputDevice():name(),</li><li>        uid = module.defaultOutputDevice():uid(),</li><li>        muted = defaultOutputDevice():muted(),</li><li>        volume = defaultOutputDevice():volume(),</li><li>        device = defaultOutputDevice(),</li><li>    }</li><li>```</li></ul>          |

#### [defaultInputDevice](#defaultinputdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.defaultInputDevice() -> audio or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get the currently selected audio input device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An hs.audiodevice object, or nil if no suitable device could be found</li></ul>          |

#### [defaultOutputDevice](#defaultoutputdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.defaultOutputDevice() -> audio or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get the currently selected audio output device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An hs.audiodevice object, or nil if no suitable device could be found</li></ul>          |

#### [findDeviceByName](#finddevicebyname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.findDeviceByName(name) -> device or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Find an audio device by name                                                                                         |
| **Parameters**                                       | <ul><li>name - A string containing the name of an audio device to search for</li></ul> |
| **Returns**                                          | <ul><li>An `hs.audiodevice` object or nil if the device could not be found</li></ul>          |

#### [findDeviceByUID](#finddevicebyuid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.findDeviceByUID(uid) -> device or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Find an audio device by UID                                                                                         |
| **Parameters**                                       | <ul><li>uid - A string containing the UID of an audio device to search for</li></ul> |
| **Returns**                                          | <ul><li>An `hs.audiodevice` object or nil if the device could not be found</li></ul>          |

#### [findInputByName](#findinputbyname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.findInputByName(name) -> device or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Find an audio input device by name                                                                                         |
| **Parameters**                                       | <ul><li>name - A string containing the name of an audio input device to search for</li></ul> |
| **Returns**                                          | <ul><li>An hs.audiodevice object or nil if the device could not be found</li></ul>          |

#### [findInputByUID](#findinputbyuid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.findInputByUID(uid) -> device or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Find an audio input device by UID                                                                                         |
| **Parameters**                                       | <ul><li>name - A string containing the UID of an audio input device to search for</li></ul> |
| **Returns**                                          | <ul><li>An hs.audiodevice object or nil if the device could not be found</li></ul>          |

#### [findOutputByName](#findoutputbyname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.findOutputByName(name) -> device or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Find an audio output device by name                                                                                         |
| **Parameters**                                       | <ul><li>name - A string containing the name of an audio output device to search for</li></ul> |
| **Returns**                                          | <ul><li>An hs.audiodevice object or nil if the device could not be found</li></ul>          |

#### [findOutputByUID](#findoutputbyuid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.findOutputByUID(uid) -> device or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Find an audio output device by UID                                                                                         |
| **Parameters**                                       | <ul><li>name - A string containing the UID of an audio output device to search for</li></ul> |
| **Returns**                                          | <ul><li>An hs.audiodevice object or nil if the device could not be found</li></ul>          |

### Methods

#### [allInputDataSources](#allinputdatasources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:allInputDataSources() -> hs.audiodevice.dataSource[] or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets all of the input data sources of an audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A list of hs.audiodevice.dataSource objects, or nil if an error occurred</li></ul>          |

#### [allOutputDataSources](#alloutputdatasources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:allOutputDataSources() -> hs.audiodevice.dataSource[] or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets all of the output data sources of an audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A list of hs.audiodevice.dataSource objects, or nil if an error occurred</li></ul>          |

#### [currentInputDataSource](#currentinputdatasource)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:currentInputDataSource() -> hs.audiodevice.dataSource object or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the current input data source of an audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An hs.audiodevice.dataSource object, or nil if an error occurred</li></ul>          |
| **Notes**                                            | <ul><li>Before calling this method, you should check the result of hs.audiodevice:supportsInputDataSources()</li></ul>                |

#### [currentOutputDataSource](#currentoutputdatasource)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:currentOutputDataSource() -> hs.audiodevice.dataSource object or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the current output data source of an audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An hs.audiodevice.dataSource object, or nil if an error occurred</li></ul>          |
| **Notes**                                            | <ul><li>Before calling this method, you should check the result of hs.audiodevice:supportsOutputDataSources()</li></ul>                |

#### [inputMuted](#inputmuted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:inputMuted() -> bool or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the Input mutedness state of the audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if the audio device's Input is muted. False if it's not muted, nil if it does not support muting</li></ul>          |

#### [inputVolume](#inputvolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:inputVolume() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the current input volume of this audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number between 0 and 100, representing the input volume percentage, or nil if the audio device does not support input volume levels</li></ul>          |
| **Notes**                                            | <ul><li>The return value will be a floating point number</li></ul>                |

#### [isInputDevice](#isinputdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:isInputDevice() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determins if an audio device is an input device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the device is an input device, false if not</li></ul>          |

#### [isOutputDevice](#isoutputdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:isOutputDevice() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determins if an audio device is an output device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the device is an output device, false if not</li></ul>          |

#### [jackConnected](#jackconnected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:jackConnected() -> boolean or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determines whether an audio jack (e.g. headphones) is connected to an audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if a jack is connected, false if not, or nil if the device does not support jack sense</li></ul>          |

#### [muted](#muted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:muted() -> bool or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the mutedness state of the audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if the audio device is muted, False if it is not muted, nil if it does not support muting</li></ul>          |
| **Notes**                                            | <ul><li>If a device is capable of both input and output, this method will prefer the output. See `:inputMuted()` and `:outputMuted()` for specific variants.</li></ul>                |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:name() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the name of the audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the name of the audio device, or nil if it has no name</li></ul>          |

#### [outputMuted](#outputmuted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:outputMuted() -> bool or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the Output mutedness state of the audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if the audio device's Output is muted. False if it's not muted, nil if it does not support muting</li></ul>          |

#### [outputVolume](#outputvolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:outputVolume() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the current output volume of this audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number between 0 and 100, representing the output volume percentage, or nil if the audio device does not support output volume levels</li></ul>          |
| **Notes**                                            | <ul><li>The return value will be a floating point number</li></ul>                |

#### [setDefaultInputDevice](#setdefaultinputdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:setDefaultInputDevice() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects this device as the system's audio input device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if the audio device was successfully selected, otherwise false.</li></ul>          |

#### [setDefaultOutputDevice](#setdefaultoutputdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:setDefaultOutputDevice() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects this device as the system's audio output device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if the audio device was successfully selected, otherwise false.</li></ul>          |

#### [setInputMuted](#setinputmuted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:setInputMuted(state) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set the mutedness state of the Input of the audio device                                                                                         |
| **Parameters**                                       | <ul><li>state - A boolean value. True to mute the device, False to unmute it</li></ul> |
| **Returns**                                          | <ul><li>True if the device's Input mutedness state was set, or False if it does not support muting</li></ul>          |

#### [setInputVolume](#setinputvolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:setInputVolume(level) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set the input volume of this audio device                                                                                         |
| **Parameters**                                       | <ul><li>level - A number between 0 and 100, representing the input volume as a percentage</li></ul> |
| **Returns**                                          | <ul><li>True if the volume was set, false if the audio device does not support setting an input volume level</li></ul>          |
| **Notes**                                            | <ul><li>The volume level is a floating point number. Depending on your audio hardware, it may not be possible to increase volume in single digit increments</li></ul>                |

#### [setMuted](#setmuted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:setMuted(state) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set the mutedness state of the audio device                                                                                         |
| **Parameters**                                       | <ul><li>state - A boolean value. True to mute the device, False to unmute it</li></ul> |
| **Returns**                                          | <ul><li>True if the device's mutedness state was set, or False if it does not support muting</li></ul>          |
| **Notes**                                            | <ul><li>If a device is capable of both input and output, this method will prefer the output. See `:inputSetMuted()` and `:outputSetMuted()` for specific variants.</li></ul>                |

#### [setOutputMuted](#setoutputmuted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:setOutputMuted(state) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set the mutedness state of the Output of the audio device                                                                                         |
| **Parameters**                                       | <ul><li>state - A boolean value. True to mute the device, False to unmute it</li></ul> |
| **Returns**                                          | <ul><li>True if the device's Output mutedness state was set, or False if it does not support muting</li></ul>          |

#### [setOutputtVolume](#setoutputtvolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:setOutputtVolume(level) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set the output volume of this audio device                                                                                         |
| **Parameters**                                       | <ul><li>level - A number between 0 and 100, representing the output volume as a percentage</li></ul> |
| **Returns**                                          | <ul><li>True if the volume was set, false if the audio device does not support setting an output volume level</li></ul>          |
| **Notes**                                            | <ul><li>The volume level is a floating point number. Depending on your audio hardware, it may not be possible to increase volume in single digit increments</li></ul>                |

#### [setVolume](#setvolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:setVolume(level) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set the volume of this audio device                                                                                         |
| **Parameters**                                       | <ul><li>level - A number between 0 and 100, representing the volume as a percentage</li></ul> |
| **Returns**                                          | <ul><li>True if the volume was set, false if the audio device does not support setting a volume level.</li></ul>          |
| **Notes**                                            | <ul><li>The volume level is a floating point number. Depending on your audio hardware, it may not be possible to increase volume in single digit increments.</li><li>This method will inspect the device to determine if it is an input or output device, and set the appropriate volume. For devices that are both input and output devices, see `:setInputVolume()` and `:setOutputVolume()`</li></ul>                |

#### [supportsInputDataSources](#supportsinputdatasources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:supportsInputDataSources() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determines whether an audio device supports input data sources                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the device supports input data sources, false if not</li></ul>          |

#### [supportsOutputDataSources](#supportsoutputdatasources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:supportsOutputDataSources() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determines whether an audio device supports output data sources                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the device supports output data sources, false if not</li></ul>          |

#### [transportType](#transporttype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:transportType() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the hardware transport type of an audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the transport type, or nil if an error occurred</li></ul>          |

#### [uid](#uid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:uid() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the unique identifier of the audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the UID of the audio device, or nil if it has no UID.</li></ul>          |

#### [volume](#volume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:volume() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get the current volume of this audio device                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number between 0 and 100, representing the volume percentage, or nil if the audio device does not support volume levels</li></ul>          |
| **Notes**                                            | <ul><li>The return value will be a floating point number</li><li>This method will inspect the device to determine if it is an input or output device, and return the appropriate volume. For devices that are both input and output devices, see `:inputVolume()` and `:outputVolume()`</li></ul>                |

#### [watcherCallback](#watchercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:watcherCallback(fn) -> hs.audiodevice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or removes a callback function for an audio device watcher                                                                                         |
| **Parameters**                                       | <ul><li>fn - A callback function that will be called when properties of this audio device change, or nil to remove an existing callback. The function should accept four arguments:</li><li> A string containing the UID of the audio device (see `hs.audiodevice.findDeviceByUID()`)</li><li> A string containing the name of the event. Possible values are:</li><li>  vmvc - Volume changed</li><li>  mute - Mute state changed</li><li>  jack - Jack sense state changed (usually this means headphones were plugged/unplugged)</li><li>  span - Stereo pan changed</li><li>  diff - Device configuration changed (if you are caching audio device properties, this event indicates you should flush your cache)</li><li> A string containing the scope of the event. Possible values are:</li><li>  glob - This is a global event pertaining to the whole device</li><li>  inpt - This is an event pertaining only to the input functions of the device</li><li>  outp - This is an event pertaining only to the output functions of the device</li><li> A number containing the element of the event. Typical values are:</li><li>  0 - Typically this means the Master channel</li><li>  1 - Typically this means the Left channel</li><li>  2 - Typically this means the Right channel</li></ul> |
| **Returns**                                          | <ul><li>The `hs.audiodevice` object</li></ul>          |
| **Notes**                                            | <ul><li>You will receive many events to your callback, so filtering on the name/scope/element arguments is vital. For example, on a stereo device, it is not uncommon to receive a `volm` event for each audio channel when the volume changes, or multiple `mute` events for channels. Dragging a volume slider in the system Sound preferences will produce a large number of `volm` events. Plugging/unplugging headphones may trigger `volm` events in addition to `jack` ones, etc.</li><li>If you need to use the `hs.audiodevice` object in your callback, use `hs.audiodevice.findDeviceByUID()` to obtain it fro the first callback argument</li></ul>                |

#### [watcherIsRunning](#watcherisrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:watcherIsRunning() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the status of the `hs.audiodevice` object watcher                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the watcher is running, false if not</li></ul>          |

#### [watcherStart](#watcherstart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:watcherStart() -> hs.audiodevice or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the watcher on an `hs.audiodevice` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `hs.audiodevice` object, or nil if an error occurred</li></ul>          |

#### [watcherStop](#watcherstop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice:watcherStop() -> hs.audiodevice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the watcher on an `hs.audiodevice` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `hs.audiodevice` object</li></ul>          |

