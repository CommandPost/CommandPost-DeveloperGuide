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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound.soundFileTypes() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the supported sound file types                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the sound file filename extensions that are supported by the system                                                |
| **Notes**                                            |  * This function is unlikely to be tremendously useful, as filename extensions are essentially meaningless. The data returned by `hs.sound.soundTypes()` is far more valuable                                                      |

#### [soundTypes](#soundtypes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound.soundTypes() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the supported UTI sound file formats                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the UTI sound formats that are supported by the system                                                |

#### [systemSounds](#systemsounds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound.systemSounds() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a table of available system sounds                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing all of the available sound files (i.e. those found in ~/Library/Sounds, /Library/Sounds, /Network/Library/Sounds and /System/Library/Sounds)                                                |
| **Notes**                                            |  * The sounds listed by this function can be loaded using `hs.sound.getByName()`                                                      |

### Constructors

#### [getByFile](#getbyfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound.getByFile(path) -> sound or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates an `hs.sound` object from a file                                                                                         |
| **Parameters**                                       |  * path - A string containing the path to a sound file                                       |
| **Returns**                                          |  * An `hs.sound` object or nil if the file could not be loaded                                                |

#### [getByName](#getbyname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound.getByName(name) -> sound or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates an `hs.sound` object from a named sound                                                                                         |
| **Parameters**                                       |  * name - A string containing the name of a sound                                       |
| **Returns**                                          |  * An `hs.sound` object or nil if no matching sound could be found                                                |
| **Notes**                                            |  * Sounds can only be loaded by name if they are System Sounds (i.e. those found in ~/Library/Sounds, /Library/Sounds, /Network/Library/Sounds and /System/Library/Sounds) or are sound files that have previously been loaded and named                                                      |

### Methods

#### [currentTime](#currenttime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:currentTime([seekTime]) -> soundObject | seconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the current seek offset within an `hs.sound` object.                                                                                         |
| **Parameters**                                       |  * seekTime - An optional number of seconds to seek to within the sound object                                       |
| **Returns**                                          |  * If a parameter is provided, returns the sound object; otherwise returns the current position.                                                |

#### [device](#device)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:device([deviceUID]) -> soundObject | UID string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the playback device to use for an `hs.sound` object                                                                                         |
| **Parameters**                                       |  * deviceUID - An optional string containing the UID of an `hs.audiodevice` object to use for playback of this sound. Use an explicit nil to use the system's default device                                       |
| **Returns**                                          |  * If a parameter is provided, returns the sound object; otherwise returns the current setting.                                                |
| **Notes**                                            |  * To obtain the UID of a sound device, see `hs.audiodevice:uid()`                                                      |

#### [duration](#duration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:duration() -> seconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the length of an `hs.sound` object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A number containing the length of the sound, in seconds                                                |

#### [isPlaying](#isplaying)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:isPlaying() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the current playback state of an `hs.sound` object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A boolean, true if the sound is currently playing, otherwise false                                                |

#### [loopSound](#loopsound)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:loopSound([loop]) -> soundObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the looping behaviour of an `hs.sound` object                                                                                         |
| **Parameters**                                       |  * loop - An optional boolean, true to loop playback, false to not loop                                       |
| **Returns**                                          |  * If a parameter is provided, returns the sound object; otherwise returns the current setting.                                                |
| **Notes**                                            |  * If you have registered a callback function for completion of a sound's playback, it will not be called when the sound loops                                                      |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:name([soundName]) -> soundObject | name string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the name of an `hs.sound` object                                                                                         |
| **Parameters**                                       |  * soundName - An optional string to use as the name of the object; use an explicit nil to remove the name                                       |
| **Returns**                                          |  * If a parameter is provided, returns the sound object; otherwise returns the current setting.                                                |
| **Notes**                                            |  * If remove the sound name by specifying `nil`, the sound will automatically be set to stop when Hammerspoon is reloaded.                                                      |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:pause() -> soundObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Pauses an `hs.sound` object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `hs.sound` object if the command was successful, otherwise false.                                                |

#### [play](#play)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:play() -> soundObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Plays an `hs.sound` object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `hs.sound` object if the command was successful, otherwise false.                                                |

#### [resume](#resume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:resume() -> soundObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resumes playing a paused `hs.sound` object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `hs.sound` object if the command was successful, otherwise false.                                                |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:setCallback(function) -> soundObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set or remove the callback for receiving completion notification for the sound object.                                                                                         |
| **Parameters**                                       |  * function - A function which should be called when the sound completes playing.  Specify an explicit nil to remove the callback function.                                       |
| **Returns**                                          |  * the sound object                                                |
| **Notes**                                            |  * the callback function should accept two parameters and return none.  The parameters passed to the callback function are:   * state - a boolean flag indicating if the sound completed playing.  Returns true if playback completes properly, or false if a decoding error occurs or if the sound is stopped early with `hs.sound:stop`.   * sound - the soundObject userdata                                                      |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:stop() -> soundObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops playing an `hs.sound` object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `hs.sound` object if the command was successful, otherwise false.                                                |

#### [stopOnReload](#stoponreload)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:stopOnReload([stopOnReload]) -> soundObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set whether a sound should be stopped when Hammerspoon reloads its configuration                                                                                         |
| **Parameters**                                       |  * stopOnReload - An optional boolean, true to stop playback when Hammerspoon reloads its config, false to continue playback regardless.  Defaults to true.                                       |
| **Returns**                                          |  * If a parameter is provided, returns the sound object; otherwise returns the current setting.                                                |
| **Notes**                                            |  * This method can only be used on a named `hs.sound` object, see `hs.sound:name()`                                                      |

#### [volume](#volume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sound:volume([level]) -> soundObject | number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the playback volume of an `hs.sound` object                                                                                         |
| **Parameters**                                       |  * level - A number between 0.0 and 1.0, representing the volume of the sound object relative to the current system volume                                       |
| **Returns**                                          |  * If a parameter is provided, returns the sound object; otherwise returns the current value.                                                |

