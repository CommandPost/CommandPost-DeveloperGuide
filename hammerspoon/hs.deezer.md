# [docs](index.md) » hs.deezer
---


Controls for Deezer music player

## API Overview
* Constants - Useful values which cannot be changed
* [state_paused](#state_paused)
* [state_playing](#state_playing)
* [state_stopped](#state_stopped)
* Functions - API calls offered directly by the extension
* [displayCurrentTrack](#displayCurrentTrack)
* [ff](#ff)
* [getCurrentAlbum](#getCurrentAlbum)
* [getCurrentArtist](#getCurrentArtist)
* [getCurrentTrack](#getCurrentTrack)
* [getPlaybackState](#getPlaybackState)
* [getPosition](#getPosition)
* [getVolume](#getVolume)
* [isPlaying](#isPlaying)
* [isRunning](#isRunning)
* [next](#next)
* [pause](#pause)
* [play](#play)
* [playpause](#playpause)
* [previous](#previous)
* [rw](#rw)
* [setPosition](#setPosition)
* [setVolume](#setVolume)
* [volumeDown](#volumeDown)
* [volumeUp](#volumeUp)

## API Documentation

### Constants

#### [state_paused](#state_paused)
| Signature   | hs.deezer.state_paused  |
| Type        | Constant |
| Description | Returned by `hs.deezer.getPlaybackState()` to indicates deezer is paused |

#### [state_playing](#state_playing)
| Signature   | hs.deezer.state_playing  |
| Type        | Constant |
| Description | Returned by `hs.deezer.getPlaybackState()` to indicates deezer is playing |

#### [state_stopped](#state_stopped)
| Signature   | hs.deezer.state_stopped  |
| Type        | Constant |
| Description | Returned by `hs.deezer.getPlaybackState()` to indicates deezer is stopped |

### Functions

#### [displayCurrentTrack](#displayCurrentTrack)
| Signature   | hs.deezer.displayCurrentTrack()  |
| Type        | Function |
| Description | Displays information for current track on screen |
| Parameters |  * None | | Returns |  * None | 
#### [ff](#ff)
| Signature   | hs.deezer.ff()  |
| Type        | Function |
| Description | Skips the playback position forwards by 5 seconds |
| Parameters |  * None | | Returns |  * None | 
#### [getCurrentAlbum](#getCurrentAlbum)
| Signature   | hs.deezer.getCurrentAlbum()  |
| Type        | Function |
| Description | Gets the name of the album of the current track |
| Parameters |  * None | | Returns |  * A string containing the Album of the current track, or nil if an error occurred | 
#### [getCurrentArtist](#getCurrentArtist)
| Signature   | hs.deezer.getCurrentArtist()  |
| Type        | Function |
| Description | Gets the name of the artist of the current track |
| Parameters |  * None | | Returns |  * A string containing the Artist of the current track, or nil if an error occurred | 
#### [getCurrentTrack](#getCurrentTrack)
| Signature   | hs.deezer.getCurrentTrack()  |
| Type        | Function |
| Description | Gets the name of the current track |
| Parameters |  * None | | Returns |  * A string containing the name of the current track, or nil if an error occurred | 
#### [getPlaybackState](#getPlaybackState)
| Signature   | hs.deezer.getPlaybackState()  |
| Type        | Function |
| Description | Gets the current playback state of deezer |
| Parameters |  * None | | Returns |  * A string containing one of the following constants:   - `hs.deezer.state_stopped`   - `hs.deezer.state_paused`   - `hs.deezer.state_playing` | 
#### [getPosition](#getPosition)
| Signature   | hs.deezer.getPosition()  |
| Type        | Function |
| Description | Gets the playback position (in seconds) in the current song |
| Parameters |  * None | | Returns |  * A number indicating the current position in the song | 
#### [getVolume](#getVolume)
| Signature   | hs.deezer.getVolume()  |
| Type        | Function |
| Description | Gets the deezer volume setting |
  Paramters:
     * None
| Returns |  * A number containing the volume deezer is set to between 1 and 100 | 
#### [isPlaying](#isPlaying)
| Signature   | hs.deezer.isPlaying()  |
| Type        | Function |
| Description | Returns whether deezer is currently playing |
| Parameters |  * None | | Returns |  * A boolean value indicating whether deezer is currently playing a track, or nil if an error occurred (unknown player state). Also returns false if the application is not running | 
#### [isRunning](#isRunning)
| Signature   | hs.deezer.isRunning()  |
| Type        | Function |
| Description | Returns whether deezer is currently open. Most other functions in hs.deezer will automatically start the application, so this function can be used to guard against that. |
| Parameters |  * None | | Returns |  * A boolean value indicating whether the deezer application is running. | 
#### [next](#next)
| Signature   | hs.deezer.next()  |
| Type        | Function |
| Description | Skips to the next deezer track |
| Parameters |  * None | | Returns |  * None | 
#### [pause](#pause)
| Signature   | hs.deezer.pause()  |
| Type        | Function |
| Description | Pauses the current deezer track |
| Parameters |  * None | | Returns |  * None | 
#### [play](#play)
| Signature   | hs.deezer.play()  |
| Type        | Function |
| Description | Plays the current deezer track |
| Parameters |  * None | | Returns |  * None | 
#### [playpause](#playpause)
| Signature   | hs.deezer.playpause()  |
| Type        | Function |
| Description | Toggles play/pause of current deezer track |
| Parameters |  * None | | Returns |  * None | 
#### [previous](#previous)
| Signature   | hs.deezer.previous()  |
| Type        | Function |
| Description | Skips to previous deezer track |
| Parameters |  * None | | Returns |  * None | 
#### [rw](#rw)
| Signature   | hs.deezer.rw  |
| Type        | Function |
| Description | Skips the playback position backwards by 5 seconds |
| Parameters |  * None | | Returns |  * None | 
#### [setPosition](#setPosition)
| Signature   | hs.deezer.setPosition(pos)  |
| Type        | Function |
| Description | Sets the playback position in the current song |
| Parameters |  * pos - A number containing the position (in seconds) to jump to in the current song | | Returns |  * None | 
#### [setVolume](#setVolume)
| Signature   | hs.deezer.setVolume(vol)  |
| Type        | Function |
| Description | Sets the deezer volume setting |
| Parameters |  * vol - A number between 1 and 100 | | Returns |  * None | 
#### [volumeDown](#volumeDown)
| Signature   | hs.deezer.volumeDown()  |
| Type        | Function |
| Description | Reduces the volume by 5 |
| Parameters |  * None | | Returns |  * None | 
#### [volumeUp](#volumeUp)
| Signature   | hs.deezer.volumeUp()  |
| Type        | Function |
| Description | Increases the volume by 5 |
| Parameters |  * None | | Returns |  * None | 