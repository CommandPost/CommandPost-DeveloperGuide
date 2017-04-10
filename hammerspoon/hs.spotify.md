# [docs](index.md) » hs.spotify
---

Controls for Spotify music player

## API Overview
* Constants - Useful values which cannot be changed
** [state_paused](#state_paused)
** [state_playing](#state_playing)
** [state_stopped](#state_stopped)
* Functions - API calls offered directly by the extension
** [displayCurrentTrack](#displayCurrentTrack)
** [ff](#ff)
** [getCurrentAlbum](#getCurrentAlbum)
** [getCurrentArtist](#getCurrentArtist)
** [getCurrentTrack](#getCurrentTrack)
** [getDuration](#getDuration)
** [getPlaybackState](#getPlaybackState)
** [getPosition](#getPosition)
** [getVolume](#getVolume)
** [isPlaying](#isPlaying)
** [isRunning](#isRunning)
** [next](#next)
** [pause](#pause)
** [play](#play)
** [playpause](#playpause)
** [previous](#previous)
** [rw](#rw)
** [setPosition](#setPosition)
** [setVolume](#setVolume)
** [volumeDown](#volumeDown)
** [volumeUp](#volumeUp)

## API Documentation

### Constants

#### [state_paused](#state_paused)
| | |
|-|-|
| Signature   | hs.spotify.state_paused  |
| Type        | Constant |
| Description | Returned by `hs.spotify.getPlaybackState()` to indicates Spotify is paused |

#### [state_playing](#state_playing)
| | |
|-|-|
| Signature   | hs.spotify.state_playing  |
| Type        | Constant |
| Description | Returned by `hs.spotify.getPlaybackState()` to indicates Spotify is playing |

#### [state_stopped](#state_stopped)
| | |
|-|-|
| Signature   | hs.spotify.state_stopped  |
| Type        | Constant |
| Description | Returned by `hs.spotify.getPlaybackState()` to indicates Spotify is stopped |

### Functions

#### [displayCurrentTrack](#displayCurrentTrack)
| | |
|-|-|
| Signature   | hs.spotify.displayCurrentTrack()  |
| Type        | Function |
| Description | Displays information for current track on screen |
| Parameters |  * None | | Returns |  * None | 
#### [ff](#ff)
| | |
|-|-|
| Signature   | hs.spotify.ff()  |
| Type        | Function |
| Description | Skips the playback position forwards by 5 seconds |
| Parameters |  * None | | Returns |  * None | 
#### [getCurrentAlbum](#getCurrentAlbum)
| | |
|-|-|
| Signature   | hs.spotify.getCurrentAlbum()  |
| Type        | Function |
| Description | Gets the name of the album of the current track |
| Parameters |  * None | | Returns |  * A string containing the Album of the current track, or nil if an error occurred | 
#### [getCurrentArtist](#getCurrentArtist)
| | |
|-|-|
| Signature   | hs.spotify.getCurrentArtist()  |
| Type        | Function |
| Description | Gets the name of the artist of the current track |
| Parameters |  * None | | Returns |  * A string containing the Artist of the current track, or nil if an error occurred | 
#### [getCurrentTrack](#getCurrentTrack)
| | |
|-|-|
| Signature   | hs.spotify.getCurrentTrack()  |
| Type        | Function |
| Description | Gets the name of the current track |
| Parameters |  * None | | Returns |  * A string containing the name of the current track, or nil if an error occurred | 
#### [getDuration](#getDuration)
| | |
|-|-|
| Signature   | hs.spotify.getDuration()  |
| Type        | Function |
| Description | Gets the duration (in seconds) of the current song |
| Parameters |  * None | | Returns |  * The number of seconds long the current song is, 0 if no song is playing | 
#### [getPlaybackState](#getPlaybackState)
| | |
|-|-|
| Signature   | hs.spotify.getPlaybackState()  |
| Type        | Function |
| Description | Gets the current playback state of Spotify |
| Parameters |  * None | | Returns |  * A string containing one of the following constants:   - `hs.spotify.state_stopped`   - `hs.spotify.state_paused`   - `hs.spotify.state_playing` | 
#### [getPosition](#getPosition)
| | |
|-|-|
| Signature   | hs.spotify.getPosition()  |
| Type        | Function |
| Description | Gets the playback position (in seconds) in the current song |
| Parameters |  * None | | Returns |  * A number indicating the current position in the song | 
#### [getVolume](#getVolume)
| | |
|-|-|
| Signature   | hs.spotify.getVolume()  |
| Type        | Function |
| Description | Gets the Spotify volume setting |
  Paramters:
     * None
| Returns |  * A number containing the volume Spotify is set to between 1 and 100 | 
#### [isPlaying](#isPlaying)
| | |
|-|-|
| Signature   | hs.spotify.isPlaying()  |
| Type        | Function |
| Description | Returns whether Spotify is currently playing |
| Parameters |  * None | | Returns |  * A boolean value indicating whether Spotify is currently playing a track, or nil if an error occurred (unknown player state). Also returns false if the application is not running | 
#### [isRunning](#isRunning)
| | |
|-|-|
| Signature   | hs.spotify.isRunning()  |
| Type        | Function |
| Description | Returns whether Spotify is currently open. Most other functions in hs.spotify will automatically start the application, so this function can be used to guard against that. |
| Parameters |  * None | | Returns |  * A boolean value indicating whether the Spotify application is running. | 
#### [next](#next)
| | |
|-|-|
| Signature   | hs.spotify.next()  |
| Type        | Function |
| Description | Skips to the next Spotify track |
| Parameters |  * None | | Returns |  * None | 
#### [pause](#pause)
| | |
|-|-|
| Signature   | hs.spotify.pause()  |
| Type        | Function |
| Description | Pauses the current Spotify track |
| Parameters |  * None | | Returns |  * None | 
#### [play](#play)
| | |
|-|-|
| Signature   | hs.spotify.play()  |
| Type        | Function |
| Description | Plays the current Spotify track |
| Parameters |  * None | | Returns |  * None | 
#### [playpause](#playpause)
| | |
|-|-|
| Signature   | hs.spotify.playpause()  |
| Type        | Function |
| Description | Toggles play/pause of current Spotify track |
| Parameters |  * None | | Returns |  * None | 
#### [previous](#previous)
| | |
|-|-|
| Signature   | hs.spotify.previous()  |
| Type        | Function |
| Description | Skips to previous Spotify track |
| Parameters |  * None | | Returns |  * None | 
#### [rw](#rw)
| | |
|-|-|
| Signature   | hs.spotify.rw  |
| Type        | Function |
| Description | Skips the playback position backwards by 5 seconds |
| Parameters |  * None | | Returns |  * None | 
#### [setPosition](#setPosition)
| | |
|-|-|
| Signature   | hs.spotify.setPosition(pos)  |
| Type        | Function |
| Description | Sets the playback position in the current song |
| Parameters |  * pos - A number containing the position (in seconds) to jump to in the current song | | Returns |  * None | 
#### [setVolume](#setVolume)
| | |
|-|-|
| Signature   | hs.spotify.setVolume(vol)  |
| Type        | Function |
| Description | Sets the Spotify volume setting |
| Parameters |  * vol - A number between 1 and 100 | | Returns |  * None | 
#### [volumeDown](#volumeDown)
| | |
|-|-|
| Signature   | hs.spotify.volumeDown()  |
| Type        | Function |
| Description | Reduces the volume by 5 |
| Parameters |  * None | | Returns |  * None | 
#### [volumeUp](#volumeUp)
| | |
|-|-|
| Signature   | hs.spotify.volumeUp()  |
| Type        | Function |
| Description | Increases the volume by 5 |
| Parameters |  * None | | Returns |  * None | 