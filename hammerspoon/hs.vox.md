# Hammerspoon docs: hs.vox

Controls for VOX music player

## API Overview
* Functions - API calls offered directly by the extension</li>
  * addurl
  * backward
  * decreaseVolume
  * fastBackward
  * fastForward
  * forward
  * getAlbumArtist
  * getCurrentAlbum
  * getCurrentArtist
  * getPlayerState
  * getUniqueID
  * increaseVolume
  * isRunning
  * next
  * pause
  * play
  * playpause
  * playurl
  * previous
  * shuffle
  * togglePlaylist
  * trackInfo

## API Documentation

### Functions

#### addurl
  * Signature: hs.vox.addurl(url)
  * Type: Function
  * Description: Add media URL to current list
  * Parameters:
     * url {string}
  * Returns:
     * None

#### backward
  * Signature: hs.vox.backward()
  * Type: Function
  * Description: Skips the playback position backwards by about 7 seconds
  * Parameters:
     * None
  * Returns:
     * None

#### decreaseVolume
  * Signature: hs.vox.decreaseVolume()
  * Type: Function
  * Description: Decreases the player volume
  * Parameters:
     * None
  * Returns:
     * None

#### fastBackward
  * Signature: hs.vox.fastBackward()
  * Type: Function
  * Description: Skips the playback position backwards by about 14 seconds
  * Parameters:
     * None
  * Returns:
     * None

#### fastForward
  * Signature: hs.vox.fastForward()
  * Type: Function
  * Description: Skips the playback position forwards by about 17 seconds
  * Parameters:
     * None
  * Returns:
     * None

#### forward
  * Signature: hs.vox.forward()
  * Type: Function
  * Description: Skips the playback position forwards by about 7 seconds
  * Parameters:
     * None
  * Returns:
     * None

#### getAlbumArtist
  * Signature: hs.vox.getAlbumArtist()
  * Type: Function
  * Description: Gets the artist of current Album
  * Parameters:
     * None
  * Returns:
     * A string containing the artist of current Album, or nil if an error occurred

#### getCurrentAlbum
  * Signature: hs.vox.getCurrentAlbum()
  * Type: Function
  * Description: Gets the name of the album of the current track
  * Parameters:
     * None
  * Returns:
     * A string containing the Album of the current track, or nil if an error occurred

#### getCurrentArtist
  * Signature: hs.vox.getCurrentArtist()
  * Type: Function
  * Description: Gets the name of the artist of the current track
  * Parameters:
     * None
  * Returns:
     * A string containing the Artist of the current track, or nil if an error occurred

#### getPlayerState
  * Signature: hs.vox.getPlayerState()
  * Type: Function
  * Description: Gets the current playback state of vox
  * Parameters:
     * None
  * Returns:
     * 0 for paused
     * 1 for playing

#### getUniqueID
  * Signature: hs.vox.getUniqueID()
  * Type: Function
  * Description: Gets the uniqueID of the current track
  * Parameters:
     * None
  * Returns:
     * A string containing the name of the current track, or nil if an error occurred

#### increaseVolume
  * Signature: hs.vox.increaseVolume()
  * Type: Function
  * Description: Increases the palyer volume
  * Parameters:
     * None
  * Returns:
     * None

#### isRunning
  * Signature: hs.vox.isRunning()
  * Type: Function
  * Description: Returns whether VOX is currently open
  * Parameters:
     * None
  * Returns:
     * A boolean value indicating whether the vox application is running

#### next
  * Signature: hs.vox.next()
  * Type: Function
  * Description: Skips to the next track
  * Parameters:
     * None
  * Returns:
     * None

#### pause
  * Signature: hs.vox.pause()
  * Type: Function
  * Description: Pauses the current vox track
  * Parameters:
     * None
  * Returns:
     * None

#### play
  * Signature: hs.vox.play()
  * Type: Function
  * Description: Plays the current vox track
  * Parameters:
     * None
  * Returns:
     * None

#### playpause
  * Signature: hs.vox.playpause()
  * Type: Function
  * Description: Toggles play/pause of current vox track
  * Parameters:
     * None
  * Returns:
     * None

#### playurl
  * Signature: hs.vox.playurl(url)
  * Type: Function
  * Description: Play media from the given URL
  * Parameters:
     * url {string}
  * Returns:
     * None

#### previous
  * Signature: hs.vox.previous()
  * Type: Function
  * Description: Skips to previous track
  * Parameters:
     * None
  * Returns:
     * None

#### shuffle
  * Signature: hs.vox.shuffle()
  * Type: Function
  * Description: Toggle shuffle state of current list
  * Parameters:
     * None
  * Returns:
     * None

#### togglePlaylist
  * Signature: hs.vox.togglePlaylist()
  * Type: Function
  * Description: Toggle playlist
  * Parameters:
     * None
  * Returns:
     * None

#### trackInfo
  * Signature: hs.vox.trackInfo()
  * Type: Function
  * Description: Displays information for current track on screen
  * Parameters:
     * None
  * Returns:
     * None
