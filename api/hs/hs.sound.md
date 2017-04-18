# [docs](index.md) » hs.sound
---

Load/play/manipulate sound files

## API Overview
* Functions - API calls offered directly by the extension
 * [soundFileTypes](#soundfiletypes)
 * [soundTypes](#soundtypes)
 * [systemSounds](#systemsounds)
* Constructors - API calls which return an object, typically one that offers API methods
 * [getByFile](#getbyfile)
 * [getByName](#getbyname)
* Methods - API calls which can only be made on an object returned by a constructor
 * [currentTime](#currenttime)
 * [device](#device)
 * [duration](#duration)
 * [isPlaying](#isplaying)
 * [loopSound](#loopsound)
 * [name](#name)
 * [pause](#pause)
 * [play](#play)
 * [resume](#resume)
 * [setCallback](#setcallback)
 * [stop](#stop)
 * [stopOnReload](#stoponreload)
 * [volume](#volume)

## API Documentation

### Functions

#### [soundFileTypes](#soundfiletypes)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound.soundFileTypes() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the supported sound file types                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the sound file filename extensions that are supported by the system</li></ul>          |
| **Notes**                                            | <ul><li>This function is unlikely to be tremendously useful, as filename extensions are essentially meaningless. The data returned by `hs.sound.soundTypes()` is far more valuable</li></ul>                |

#### [soundTypes](#soundtypes)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound.soundTypes() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the supported UTI sound file formats                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the UTI sound formats that are supported by the system</li></ul>          |

#### [systemSounds](#systemsounds)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound.systemSounds() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a table of available system sounds                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing all of the available sound files (i.e. those found in ~/Library/Sounds, /Library/Sounds, /Network/Library/Sounds and /System/Library/Sounds)</li></ul>          |
| **Notes**                                            | <ul><li>The sounds listed by this function can be loaded using `hs.sound.getByName()`</li></ul>                |

### Constructors

#### [getByFile](#getbyfile)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound.getByFile(path) -> sound or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates an `hs.sound` object from a file                                                                                         |
| **Parameters**                                       | <ul><li>path - A string containing the path to a sound file</li></ul> |
| **Returns**                                          | <ul><li>An `hs.sound` object or nil if the file could not be loaded</li></ul>          |

#### [getByName](#getbyname)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound.getByName(name) -> sound or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates an `hs.sound` object from a named sound                                                                                         |
| **Parameters**                                       | <ul><li>name - A string containing the name of a sound</li></ul> |
| **Returns**                                          | <ul><li>An `hs.sound` object or nil if no matching sound could be found</li></ul>          |
| **Notes**                                            | <ul><li>Sounds can only be loaded by name if they are System Sounds (i.e. those found in ~/Library/Sounds, /Library/Sounds, /Network/Library/Sounds and /System/Library/Sounds) or are sound files that have previously been loaded and named</li></ul>                |

### Methods

#### [currentTime](#currenttime)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:currentTime([seekTime]) -> soundObject | seconds` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the current seek offset within an `hs.sound` object.                                                                                         |
| **Parameters**                                       | <ul><li>seekTime - An optional number of seconds to seek to within the sound object</li></ul> |
| **Returns**                                          | <ul><li>If a parameter is provided, returns the sound object; otherwise returns the current position.</li></ul>          |

#### [device](#device)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:device([deviceUID]) -> soundObject | UID string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the playback device to use for an `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>deviceUID - An optional string containing the UID of an `hs.audiodevice` object to use for playback of this sound. Use an explicit nil to use the system's default device</li></ul> |
| **Returns**                                          | <ul><li>If a parameter is provided, returns the sound object; otherwise returns the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>To obtain the UID of a sound device, see `hs.audiodevice:uid()`</li></ul>                |

#### [duration](#duration)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:duration() -> seconds` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the length of an `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number containing the length of the sound, in seconds</li></ul>          |

#### [isPlaying](#isplaying)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:isPlaying() -> bool` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the current playback state of an `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the sound is currently playing, otherwise false</li></ul>          |

#### [loopSound](#loopsound)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:loopSound([loop]) -> soundObject | bool` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the looping behaviour of an `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>loop - An optional boolean, true to loop playback, false to not loop</li></ul> |
| **Returns**                                          | <ul><li>If a parameter is provided, returns the sound object; otherwise returns the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>If you have registered a callback function for completion of a sound's playback, it will not be called when the sound loops</li></ul>                |

#### [name](#name)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:name([soundName]) -> soundObject | name string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the name of an `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>soundName - An optional string to use as the name of the object; use an explicit nil to remove the name</li></ul> |
| **Returns**                                          | <ul><li>If a parameter is provided, returns the sound object; otherwise returns the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>If remove the sound name by specifying `nil`, the sound will automatically be set to stop when Hammerspoon is reloaded.</li></ul>                |

#### [pause](#pause)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:pause() -> soundObject | bool` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Pauses an `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `hs.sound` object if the command was successful, otherwise false.</li></ul>          |

#### [play](#play)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:play() -> soundObject | bool` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Plays an `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `hs.sound` object if the command was successful, otherwise false.</li></ul>          |

#### [resume](#resume)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:resume() -> soundObject | bool` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resumes playing a paused `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `hs.sound` object if the command was successful, otherwise false.</li></ul>          |

#### [setCallback](#setcallback)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:setCallback(function) -> soundObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set or remove the callback for receiving completion notification for the sound object.                                                                                         |
| **Parameters**                                       | <ul><li>function - A function which should be called when the sound completes playing.  Specify an explicit nil to remove the callback function.</li></ul> |
| **Returns**                                          | <ul><li>the sound object</li></ul>          |
| **Notes**                                            | <ul><li>the callback function should accept two parameters and return none.  The parameters passed to the callback function are:</li><li>  state - a boolean flag indicating if the sound completed playing.  Returns true if playback completes properly, or false if a decoding error occurs or if the sound is stopped early with `hs.sound:stop`.</li><li>  sound - the soundObject userdata</li></ul>                |

#### [stop](#stop)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:stop() -> soundObject | bool` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops playing an `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `hs.sound` object if the command was successful, otherwise false.</li></ul>          |

#### [stopOnReload](#stoponreload)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:stopOnReload([stopOnReload]) -> soundObject | bool` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set whether a sound should be stopped when Hammerspoon reloads its configuration                                                                                         |
| **Parameters**                                       | <ul><li>stopOnReload - An optional boolean, true to stop playback when Hammerspoon reloads its config, false to continue playback regardless.  Defaults to true.</li></ul> |
| **Returns**                                          | <ul><li>If a parameter is provided, returns the sound object; otherwise returns the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>This method can only be used on a named `hs.sound` object, see `hs.sound:name()`</li></ul>                |

#### [volume](#volume)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.sound:volume([level]) -> soundObject | number` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the playback volume of an `hs.sound` object                                                                                         |
| **Parameters**                                       | <ul><li>level - A number between 0.0 and 1.0, representing the volume of the sound object relative to the current system volume</li></ul> |
| **Returns**                                          | <ul><li>If a parameter is provided, returns the sound object; otherwise returns the current value.</li></ul>          |

