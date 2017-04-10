# Hammerspoon docs: hs.itunes

Controls for iTunes music player

## API Overview
* Constants - Useful values which cannot be changed</li>
  * state_paused
  * state_playing
  * state_stopped
* Functions - API calls offered directly by the extension</li>
  * displayCurrentTrack
  * ff
  * getCurrentAlbum
  * getCurrentArtist
  * getCurrentTrack
  * getDuration
  * getPlaybackState
  * getPosition
  * getVolume
  * isPlaying
  * isRunning
  * next
  * pause
  * play
  * playpause
  * previous
  * rw
  * setPosition
  * setVolume
  * volumeDown
  * volumeUp

## API Documentation

### Constants

#### state_paused
  * Signature: hs.itunes.state_paused
  * Type: Constant
  * Description: Returned by `hs.itunes.getPlaybackState()` to indicates iTunes is paused

#### state_playing
  * Signature: hs.itunes.state_playing
  * Type: Constant
  * Description: Returned by `hs.itunes.getPlaybackState()` to indicates iTunes is playing

#### state_stopped
  * Signature: hs.itunes.state_stopped
  * Type: Constant
  * Description: Returned by `hs.itunes.getPlaybackState()` to indicates iTunes is stopped

### Functions

#### displayCurrentTrack
  * Signature: hs.itunes.displayCurrentTrack()
  * Type: Function
  * Description: Displays information for current track on screen
  * Parameters:
     * None
  * Returns:
     * None

#### ff
  * Signature: hs.itunes.ff()
  * Type: Function
  * Description: Skips the current playback forwards by 5 seconds
  * Parameters:
     * None
  * Returns:
     * None

#### getCurrentAlbum
  * Signature: hs.itunes.getCurrentAlbum() -> string or nil
  * Type: Function
  * Description: Gets the name of the current Album
  * Parameters:
     * None
  * Returns:
     * A string containing the Album of the current track, or nil if an error occurred

#### getCurrentArtist
  * Signature: hs.itunes.getCurrentArtist() -> string or nil
  * Type: Function
  * Description: Gets the name of the current Artist
  * Parameters:
     * None
  * Returns:
     * A string containing the Artist of the current track, or nil if an error occurred

#### getCurrentTrack
  * Signature: hs.itunes.getCurrentTrack() -> string or nil
  * Type: Function
  * Description: Gets the name of the current track
  * Parameters:
     * None
  * Returns:
     * A string containing the name of the current track, or nil if an error occurred

#### getDuration
  * Signature: hs.itunes.getDuration()
  * Type: Function
  * Description: Gets the duration (in seconds) of the current song
  * Parameters:
     * None
  * Returns:
     * The number of seconds long the current song is, 0 if no song is playing

#### getPlaybackState
  * Signature: hs.itunes.getPlaybackState()
  * Type: Function
  * Description: Gets the current playback state of iTunes
  * Parameters:
     * None
  * Returns:
     * A string containing one of the following constants:
       - `hs.itunes.state_stopped`
       - `hs.itunes.state_paused`
       - `hs.itunes.state_playing`

#### getPosition
  * Signature: hs.itunes.getPosition()
  * Type: Function
  * Description: Gets the playback position (in seconds) of the current song
  * Parameters:
     * None
  * Returns:
     * A number indicating the current position in the song

#### getVolume
  * Signature: hs.itunes.getVolume()
  * Type: Function
  * Description: Gets the current iTunes volume setting
  * Parameters:
     * None
  * Returns:
     * A number, between 1 and 100, containing the current iTunes playback volume

#### isPlaying
  * Signature: hs.itunes.isPlaying()
  * Type: Function
  * Description: Returns whether iTunes is currently playing
  * Parameters:
     * None
  * Returns:
     * A boolean value indicating whether iTunes is currently playing a track, or nil if an error occurred (unknown player state). Also returns false if the application is not running

#### isRunning
  * Signature: hs.itunes.isRunning()
  * Type: Function
  * Description: Returns whether iTunes is currently open. Most other functions in hs.itunes will automatically start the application, so this function can be used to guard against that.
  * Parameters:
     * None
  * Returns:
     * A boolean value indicating whether the iTunes application is running.

#### next
  * Signature: hs.itunes.next()
  * Type: Function
  * Description: Skips to the next itunes track
  * Parameters:
     * None
  * Returns:
     * None

#### pause
  * Signature: hs.itunes.pause()
  * Type: Function
  * Description: Pauses the current iTunes track
  * Parameters:
     * None
  * Returns:
     * None

#### play
  * Signature: hs.itunes.play()
  * Type: Function
  * Description: Plays the current iTunes track
  * Parameters:
     * None
  * Returns:
     * None

#### playpause
  * Signature: hs.itunes.playpause()
  * Type: Function
  * Description: Toggles play/pause of current iTunes track
  * Parameters:
     * None
  * Returns:
     * None

#### previous
  * Signature: hs.itunes.previous()
  * Type: Function
  * Description: Skips to previous itunes track
  * Parameters:
     * None
  * Returns:
     * None

#### rw
  * Signature: hs.itunes.rw()
  * Type: Function
  * Description: Skips the current playback backwards by 5 seconds
  Paramters:
     * None
  * Returns:
     * None

#### setPosition
  * Signature: hs.itunes.setPosition(pos)
  * Type: Function
  * Description: Sets the playback position of the current song
  * Parameters:
     * pos - A number indicating the playback position (in seconds) to skip to
  * Returns:
     * None

#### setVolume
  * Signature: hs.itunes.setVolume(vol)
  * Type: Function
  * Description: Sets the iTunes playback volume
  * Parameters:
     * vol - A number, between 1 and 100
  * Returns:
     * None

#### volumeDown
  * Signature: hs.itunes.volumeDown()
  * Type: Function
  * Description: Decreases the iTunes playback volume by 5
  * Parameters:
     * None
  * Returns:
     * None

#### volumeUp
  * Signature: hs.itunes.volumeUp()
  * Type: Function
  * Description: Increases the iTunes playback volume by 5
  * Parameters:
     * None
  * Returns:
     * None
