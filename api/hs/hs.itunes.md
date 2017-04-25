# [docs](index.md) » hs.itunes
---

Controls for iTunes music player

## API Overview
* Constants - Useful values which cannot be changed
 * [state_paused](#state_paused)
 * [state_playing](#state_playing)
 * [state_stopped](#state_stopped)
* Functions - API calls offered directly by the extension
 * [displayCurrentTrack](#displaycurrenttrack)
 * [ff](#ff)
 * [getCurrentAlbum](#getcurrentalbum)
 * [getCurrentArtist](#getcurrentartist)
 * [getCurrentTrack](#getcurrenttrack)
 * [getDuration](#getduration)
 * [getPlaybackState](#getplaybackstate)
 * [getPosition](#getposition)
 * [getVolume](#getvolume)
 * [isPlaying](#isplaying)
 * [isRunning](#isrunning)
 * [next](#next)
 * [pause](#pause)
 * [play](#play)
 * [playpause](#playpause)
 * [previous](#previous)
 * [rw](#rw)
 * [setPosition](#setposition)
 * [setVolume](#setvolume)
 * [volumeDown](#volumedown)
 * [volumeUp](#volumeup)

## API Documentation

### Constants

#### [state_paused](#state_paused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.state_paused` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returned by `hs.itunes.getPlaybackState()` to indicates iTunes is paused                                                                                         |

#### [state_playing](#state_playing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.state_playing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returned by `hs.itunes.getPlaybackState()` to indicates iTunes is playing                                                                                         |

#### [state_stopped](#state_stopped)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.state_stopped` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returned by `hs.itunes.getPlaybackState()` to indicates iTunes is stopped                                                                                         |

### Functions

#### [displayCurrentTrack](#displaycurrenttrack)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.displayCurrentTrack()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays information for current track on screen                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [ff](#ff)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.ff()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips the current playback forwards by 5 seconds                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [getCurrentAlbum](#getcurrentalbum)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.getCurrentAlbum() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the current Album                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the Album of the current track, or nil if an error occurred</li></ul>          |

#### [getCurrentArtist](#getcurrentartist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.getCurrentArtist() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the current Artist                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the Artist of the current track, or nil if an error occurred</li></ul>          |

#### [getCurrentTrack](#getcurrenttrack)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.getCurrentTrack() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the current track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the name of the current track, or nil if an error occurred</li></ul>          |

#### [getDuration](#getduration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.getDuration()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the duration (in seconds) of the current song                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The number of seconds long the current song is, 0 if no song is playing</li></ul>          |

#### [getPlaybackState](#getplaybackstate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.getPlaybackState()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the current playback state of iTunes                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing one of the following constants:</li><li>   - `hs.itunes.state_stopped`</li><li>   - `hs.itunes.state_paused`</li><li>   - `hs.itunes.state_playing`</li></ul>          |

#### [getPosition](#getposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.getPosition()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the playback position (in seconds) of the current song                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number indicating the current position in the song</li></ul>          |

#### [getVolume](#getvolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.getVolume()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the current iTunes volume setting                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number, between 1 and 100, containing the current iTunes playback volume</li></ul>          |

#### [isPlaying](#isplaying)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.isPlaying()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether iTunes is currently playing                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean value indicating whether iTunes is currently playing a track, or nil if an error occurred (unknown player state). Also returns false if the application is not running</li></ul>          |

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.isRunning()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether iTunes is currently open. Most other functions in hs.itunes will automatically start the application, so this function can be used to guard against that.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean value indicating whether the iTunes application is running.</li></ul>          |

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.next()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips to the next itunes track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.pause()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Pauses the current iTunes track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [play](#play)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.play()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Plays the current iTunes track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [playpause](#playpause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.playpause()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles play/pause of current iTunes track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [previous](#previous)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.previous()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips to previous itunes track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [rw](#rw)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.rw()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips the current playback backwards by 5 seconds                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setPosition](#setposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.setPosition(pos)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the playback position of the current song                                                                                         |
| **Parameters**                                       | <ul><li>pos - A number indicating the playback position (in seconds) to skip to</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setVolume](#setvolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.setVolume(vol)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the iTunes playback volume                                                                                         |
| **Parameters**                                       | <ul><li>vol - A number, between 1 and 100</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [volumeDown](#volumedown)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.volumeDown()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Decreases the iTunes playback volume by 5                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [volumeUp](#volumeup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.itunes.volumeUp()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Increases the iTunes playback volume by 5                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

