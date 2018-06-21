# [docs](index.md) » hs.audiodevice.watcher
---

Watch for system level audio hardware events

## API Overview
* Functions - API calls offered directly by the extension
 * [isRunning](#isrunning)
 * [setCallback](#setcallback)
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Functions

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.watcher.isRunning() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the status of the audio device watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean, true if the watcher is running, false if not</li></ul>          |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.watcher.setCallback(fn)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the callback function for the audio device watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">fn - A callback function, or nil to remove a previously set callback. The callback function should accept a single argument (see Notes below)</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This watcher will call the callback when various audio device related events occur (e.g. an audio device appears/disappears, a system default audio device setting changes, etc)</li><li markdown="1">To watch for changes within an audio device, see `hs.audiodevice:newWatcher()`</li><li markdown="1">The callback function argument is a string which may be one of the following strings, but might also be a different string entirely:</li><li markdown="1"> dIn  - Default audio input device setting changed (Note that there is a space character after `dIn`, because these values always have to be four characters long)</li><li markdown="1"> dOut - Default audio output device setting changed</li><li markdown="1"> sOut - Default system audio output setting changed (i.e. the device that system sound effects use. This may also be triggered by dOut, depending on the user's settings)</li><li markdown="1"> dev# - An audio device appeared or disappeared</li><li markdown="1">The callback will be called for each individual audio device event received from the OS, so you may receive multiple events for a single physical action (e.g. unplugging the default audio device will cause `dOut` and `dev#` events, and possibly `sOut` too)</li><li markdown="1">Passing nil will cause the watcher to stop if it is already running</li></ul>                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.watcher.start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Starts the audio device watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.audiodevice.watcher.stop() -> hs.audiodevice.watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the audio device watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `hs.audiodevice.watcher` object</li></ul>          |

