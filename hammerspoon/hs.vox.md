# [docs](index.md) » hs.vox
---

Controls for VOX music player

## API Overview
* Functions - API calls offered directly by the extension
 * [addurl](#addurl)
 * [backward](#backward)
 * [decreaseVolume](#decreaseVolume)
 * [fastBackward](#fastBackward)
 * [fastForward](#fastForward)
 * [forward](#forward)
 * [getAlbumArtist](#getAlbumArtist)
 * [getCurrentAlbum](#getCurrentAlbum)
 * [getCurrentArtist](#getCurrentArtist)
 * [getPlayerState](#getPlayerState)
 * [getUniqueID](#getUniqueID)
 * [increaseVolume](#increaseVolume)
 * [isRunning](#isRunning)
 * [next](#next)
 * [pause](#pause)
 * [play](#play)
 * [playpause](#playpause)
 * [playurl](#playurl)
 * [previous](#previous)
 * [shuffle](#shuffle)
 * [togglePlaylist](#togglePlaylist)
 * [trackInfo](#trackInfo)

## API Documentation

### Functions

| #### [addurl](#addurl)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.addurl(url)                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Add media URL to current list                                                           |
| **Parameters**                              |  * url {string}         |
| **Returns**                                 |  * None                  |

| #### [backward](#backward)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.backward()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Skips the playback position backwards by about 7 seconds                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [decreaseVolume](#decreaseVolume)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.decreaseVolume()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Decreases the player volume                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [fastBackward](#fastBackward)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.fastBackward()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Skips the playback position backwards by about 14 seconds                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [fastForward](#fastForward)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.fastForward()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Skips the playback position forwards by about 17 seconds                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [forward](#forward)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.forward()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Skips the playback position forwards by about 7 seconds                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [getAlbumArtist](#getAlbumArtist)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.getAlbumArtist()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the artist of current Album                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * A string containing the artist of current Album, or nil if an error occurred                  |

| #### [getCurrentAlbum](#getCurrentAlbum)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.getCurrentAlbum()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the name of the album of the current track                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * A string containing the Album of the current track, or nil if an error occurred                  |

| #### [getCurrentArtist](#getCurrentArtist)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.getCurrentArtist()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the name of the artist of the current track                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * A string containing the Artist of the current track, or nil if an error occurred                  |

| #### [getPlayerState](#getPlayerState)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.getPlayerState()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the current playback state of vox                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * 0 for paused * 1 for playing                  |

| #### [getUniqueID](#getUniqueID)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.getUniqueID()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the uniqueID of the current track                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * A string containing the name of the current track, or nil if an error occurred                  |

| #### [increaseVolume](#increaseVolume)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.increaseVolume()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Increases the palyer volume                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [isRunning](#isRunning)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.isRunning()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Returns whether VOX is currently open                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * A boolean value indicating whether the vox application is running                  |

| #### [next](#next)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.next()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Skips to the next track                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [pause](#pause)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.pause()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Pauses the current vox track                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [play](#play)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.play()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Plays the current vox track                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [playpause](#playpause)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.playpause()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Toggles play/pause of current vox track                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [playurl](#playurl)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.playurl(url)                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Play media from the given URL                                                           |
| **Parameters**                              |  * url {string}         |
| **Returns**                                 |  * None                  |

| #### [previous](#previous)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.previous()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Skips to previous track                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [shuffle](#shuffle)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.shuffle()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Toggle shuffle state of current list                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [togglePlaylist](#togglePlaylist)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.togglePlaylist()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Toggle playlist                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [trackInfo](#trackInfo)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.vox.trackInfo()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Displays information for current track on screen                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

