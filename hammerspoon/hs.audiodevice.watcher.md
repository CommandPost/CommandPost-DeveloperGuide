# [docs](index.md) » hs.audiodevice.watcher
---

Watch for system level audio hardware events

## API Overview
* Functions - API calls offered directly by the extension
 * [isRunning](#isRunning)
 * [setCallback](#setCallback)
 * [start](#start)
 * [stop](#stop)

## API Documentation
### Functions

#### [isRunning](#isRunning)
|             |                 |
| ------------|-----------------|
| Signature   | hs.audiodevice.watcher.isRunning() -> boolean  |
| Type        | Function |
| Description | Gets the status of the audio device watcher |
| Parameters |  * None |
| Returns |  * A boolean, true if the watcher is running, false if not |


#### [setCallback](#setCallback)
|             |                 |
| ------------|-----------------|
| Signature   | hs.audiodevice.watcher.setCallback(fn)  |
| Type        | Function |
| Description | Sets the callback function for the audio device watcher |
| Parameters |  * fn - A callback function, or nil to remove a previously set callback. The callback function should accept a single argument (see Notes below) |
| Returns |  * None |
| Notes |  * This watcher will call the callback when various audio device related events occur (e.g. an audio device appears/disappears, a system default audio device setting changes, etc) * To watch for changes within an audio device, see `hs.audiodevice:newWatcher()` * The callback function argument is a string which may be one of the following strings, but might also be a different string entirely:  * dIn  - Default audio input device setting changed (Note that there is a space character after `dIn`, because these values always have to be four characters long)  * dOut - Default audio output device setting changed  * sOut - Default system audio output setting changed (i.e. the device that system sound effects use. This may also be triggered by dOut, depending on the user's settings)  * dev# - An audio device appeared or disappeared * The callback will be called for each individual audio device event received from the OS, so you may receive multiple events for a single physical action (e.g. unplugging the default audio device will cause `dOut` and `dev#` events, and possibly `sOut` too) * Passing nil will cause the watcher to stop if it is already running

#### [start](#start)
|             |                 |
| ------------|-----------------|
| Signature   | hs.audiodevice.watcher.start()  |
| Type        | Function |
| Description | Starts the audio device watcher |
| Parameters |  * None |
| Returns |  * None |


#### [stop](#stop)
|             |                 |
| ------------|-----------------|
| Signature   | hs.audiodevice.watcher.stop() -> hs.audiodevice.watcher  |
| Type        | Function |
| Description | Stops the audio device watcher |
| Parameters |  * None |
| Returns |  * The `hs.audiodevice.watcher` object |
 |
