# [docs](index.md) » hs.spotify
---

Controls for Spotify music player

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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.state_paused` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returned by `hs.spotify.getPlaybackState()` to indicates Spotify is paused                                                                                         |

#### [state_playing](#state_playing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.state_playing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returned by `hs.spotify.getPlaybackState()` to indicates Spotify is playing                                                                                         |

#### [state_stopped](#state_stopped)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.state_stopped` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returned by `hs.spotify.getPlaybackState()` to indicates Spotify is stopped                                                                                         |

### Functions

#### [displayCurrentTrack](#displaycurrenttrack)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.displayCurrentTrack()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays information for current track on screen                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [ff](#ff)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.ff()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips the playback position forwards by 5 seconds                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [getCurrentAlbum](#getcurrentalbum)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.getCurrentAlbum()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the album of the current track                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing the Album of the current track, or nil if an error occurred</li></ul>          |

#### [getCurrentArtist](#getcurrentartist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.getCurrentArtist()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the artist of the current track                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing the Artist of the current track, or nil if an error occurred</li></ul>          |

#### [getCurrentTrack](#getcurrenttrack)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.getCurrentTrack()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the current track                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing the name of the current track, or nil if an error occurred</li></ul>          |

#### [getDuration](#getduration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.getDuration()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the duration (in seconds) of the current song                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The number of seconds long the current song is, 0 if no song is playing</li></ul>          |

#### [getPlaybackState](#getplaybackstate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.getPlaybackState()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the current playback state of Spotify                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing one of the following constants:</li><li markdown="1">   - `hs.spotify.state_stopped`</li><li markdown="1">   - `hs.spotify.state_paused`</li><li markdown="1">   - `hs.spotify.state_playing`</li></ul>          |

#### [getPosition](#getposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.getPosition()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the playback position (in seconds) in the current song                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A number indicating the current position in the song</li></ul>          |

#### [getVolume](#getvolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.getVolume()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the Spotify volume setting                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A number containing the volume Spotify is set to between 1 and 100</li></ul>          |

#### [isPlaying](#isplaying)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.isPlaying()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether Spotify is currently playing                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean value indicating whether Spotify is currently playing a track, or nil if an error occurred (unknown player state). Also returns false if the application is not running</li></ul>          |

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.isRunning()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether Spotify is currently open. Most other functions in hs.spotify will automatically start the application, so this function can be used to guard against that.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean value indicating whether the Spotify application is running.</li></ul>          |

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.next()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips to the next Spotify track                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.pause()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Pauses the current Spotify track                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [play](#play)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.play()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Plays the current Spotify track                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [playpause](#playpause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.playpause()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles play/pause of current Spotify track                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [previous](#previous)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.previous()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips to previous Spotify track                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [rw](#rw)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.rw` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips the playback position backwards by 5 seconds                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [setPosition](#setposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.setPosition(pos)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the playback position in the current song                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">pos - A number containing the position (in seconds) to jump to in the current song</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [setVolume](#setvolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.setVolume(vol)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Spotify volume setting                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">vol - A number between 1 and 100</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [volumeDown](#volumedown)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.volumeDown()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Reduces the volume by 5                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [volumeUp](#volumeup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotify.volumeUp()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Increases the volume by 5                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

