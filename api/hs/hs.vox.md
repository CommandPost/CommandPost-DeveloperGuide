# [docs](index.md) » hs.vox
---

Controls for VOX music player

## API Overview
* Functions - API calls offered directly by the extension
 * [addurl](#addurl)
 * [backward](#backward)
 * [decreaseVolume](#decreasevolume)
 * [fastBackward](#fastbackward)
 * [fastForward](#fastforward)
 * [forward](#forward)
 * [getAlbumArtist](#getalbumartist)
 * [getCurrentAlbum](#getcurrentalbum)
 * [getCurrentArtist](#getcurrentartist)
 * [getPlayerState](#getplayerstate)
 * [getUniqueID](#getuniqueid)
 * [increaseVolume](#increasevolume)
 * [isRunning](#isrunning)
 * [next](#next)
 * [pause](#pause)
 * [play](#play)
 * [playpause](#playpause)
 * [playurl](#playurl)
 * [previous](#previous)
 * [shuffle](#shuffle)
 * [togglePlaylist](#toggleplaylist)
 * [trackInfo](#trackinfo)

## API Documentation

### Functions

#### [addurl](#addurl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.addurl(url)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Add media URL to current list                                                                                         |
| **Parameters**                                       | <ul><li>url {string}</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [backward](#backward)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.backward()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips the playback position backwards by about 7 seconds                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [decreaseVolume](#decreasevolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.decreaseVolume()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Decreases the player volume                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [fastBackward](#fastbackward)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.fastBackward()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips the playback position backwards by about 14 seconds                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [fastForward](#fastforward)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.fastForward()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips the playback position forwards by about 17 seconds                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [forward](#forward)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.forward()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips the playback position forwards by about 7 seconds                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [getAlbumArtist](#getalbumartist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.getAlbumArtist()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the artist of current Album                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the artist of current Album, or nil if an error occurred</li></ul>            |

#### [getCurrentAlbum](#getcurrentalbum)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.getCurrentAlbum()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the album of the current track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the Album of the current track, or nil if an error occurred</li></ul>            |

#### [getCurrentArtist](#getcurrentartist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.getCurrentArtist()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the name of the artist of the current track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the Artist of the current track, or nil if an error occurred</li></ul>            |

#### [getPlayerState](#getplayerstate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.getPlayerState()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the current playback state of vox                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>0 for paused</li></ul><ul><li>1 for playing</li></ul>            |

#### [getUniqueID](#getuniqueid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.getUniqueID()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the uniqueID of the current track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the name of the current track, or nil if an error occurred</li></ul>            |

#### [increaseVolume](#increasevolume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.increaseVolume()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Increases the palyer volume                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.isRunning()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether VOX is currently open                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A boolean value indicating whether the vox application is running</li></ul>            |

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.next()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips to the next track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.pause()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Pauses the current vox track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [play](#play)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.play()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Plays the current vox track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [playpause](#playpause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.playpause()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles play/pause of current vox track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [playurl](#playurl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.playurl(url)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Play media from the given URL                                                                                         |
| **Parameters**                                       | <ul><li>url {string}</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [previous](#previous)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.previous()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Skips to previous track                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [shuffle](#shuffle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.shuffle()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggle shuffle state of current list                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [togglePlaylist](#toggleplaylist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.togglePlaylist()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggle playlist                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [trackInfo](#trackinfo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.vox.trackInfo()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays information for current track on screen                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

