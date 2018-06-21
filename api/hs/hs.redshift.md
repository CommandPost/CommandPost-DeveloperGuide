# [docs](index.md) » hs.redshift
---

Inverts and/or lowers the color temperature of the screen(s) on a schedule, for a more pleasant experience at night

Usage:
```
-- make a windowfilterDisable for redshift: VLC, Photos and screensaver/login window will disable color adjustment and inversion
local wfRedshift=hs.window.filter.new({VLC={focused=true},Photos={focused=true},loginwindow={visible=true,allowRoles='*'}},'wf-redshift')
-- start redshift: 2800K + inverted from 21 to 7, very long transition duration (19->23 and 5->9)
hs.redshift.start(2800,'21:00','7:00','4h',true,wfRedshift)
-- allow manual control of inverted colors
hs.hotkey.bind(HYPER,'f1','Invert',hs.redshift.toggleInvert)
```

Note:
 * As of macOS 10.12.4, Apple provides "Night Shift", which implements a simple red-shift effect, as part of the OS. It seems unlikely that `hs.redshift` will see significant future development.

## API Overview
* Variables - Configurable values
 * [COLORRAMP](#colorramp)
* Functions - API calls offered directly by the extension
 * [invertSubscribe](#invertsubscribe)
 * [invertUnsubscribe](#invertunsubscribe)
 * [isInverted](#isinverted)
 * [requestInvert](#requestinvert)
 * [start](#start)
 * [stop](#stop)
 * [toggle](#toggle)
 * [toggleInvert](#toggleinvert)

## API Documentation

### Variables

#### [COLORRAMP](#colorramp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.COLORRAMP` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | A table holding the gamma values for given color temperatures; each key must be a color temperature number in K (useful values are between                                                                                         |
| **Notes**                                            | <ul markdown="1"><li markdown="1">`hs.inspect(hs.redshift.COLORRAMP)` from the console will show you how the table is built</li><li markdown="1">the default ramp has entries from 1000K to 10000K every 100K</li></ul>                |

### Functions

#### [invertSubscribe](#invertsubscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.invertSubscribe([id,]fn)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Subscribes a callback to be notified when the color inversion status changes                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">id - (optional) a string identifying the requester (usually the module name); if omitted, `fn`</li><li markdown="1">   itself will be the identifier; this identifier must be passed to `hs.redshift.invertUnsubscribe()`</li><li markdown="1">fn - a function that will be called whenever color inversion status changes; it must accept a</li><li markdown="1">   single parameter, a string or false as per the return value of `hs.redshift.isInverted()`</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [invertUnsubscribe](#invertunsubscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.invertUnsubscribe(id)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unsubscribes a previously subscribed color inversion change callback                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">id - a string identifying the requester or the callback function itself, depending on how you</li><li markdown="1">   called `hs.redshift.invertSubscribe()`</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [isInverted](#isinverted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.isInverted() -> string or false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the colors are currently inverted                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">false if the colors are not currently inverted; otherwise, a string indicating the reason, one of:</li><li markdown="1">  "user" for the user override (see `hs.redshift.toggleInvert()`)</li><li markdown="1">  "redshift-night" if `hs.redshift.start()` was called with `invertAtNight` set to true,</li><li markdown="1">     and it's currently night time</li><li markdown="1">  the ID string (usually the module name) provided to `hs.redshift.requestInvert()`, if another module requested color inversion</li></ul>          |

#### [requestInvert](#requestinvert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.requestInvert(id,v)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets or clears a request for color inversion                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">id - a string identifying the requester (usually the module name)</li><li markdown="1">v - a boolean indicating whether to invert the colors (if true) or clear any previous requests (if false or nil)</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">you can use this function e.g. to automatically invert colors if the ambient light sensor reading drops below</li><li markdown="1">   a certain threshold (`hs.brightness.DDCauto()` can optionally do exactly that)</li><li markdown="1">if the user's configuration doesn't explicitly start the redshift module, calling this will have no effect</li></ul>                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.start(colorTemp,nightStart,nightEnd[,transition[,invertAtNight[,windowfilterDisable[,dayColorTemp]]]])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the schedule and (re)starts the module                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">colorTemp - a number indicating the desired color temperature (Kelvin) during the night cycle;</li><li markdown="1">   the recommended range is between 3600K and 1400K; lower values (minimum 1000K) result in a more pronounced adjustment</li><li markdown="1">nightStart - a string in the format "HH:MM" (24-hour clock) or number of seconds after midnight</li><li markdown="1">   (see `hs.timer.seconds()`) indicating when the night cycle should start</li><li markdown="1">nightEnd - a string in the format "HH:MM" (24-hour clock) or number of seconds after midnight</li><li markdown="1">   (see `hs.timer.seconds()`) indicating when the night cycle should end</li><li markdown="1">transition - (optional) a string or number of seconds (see `hs.timer.seconds()`) indicating the duration of</li><li markdown="1">   the transition to the night color temperature and back; if omitted, defaults to 1 hour</li><li markdown="1">invertAtNight - (optional) a boolean indicating whether the colors should be inverted (in addition to</li><li markdown="1">   the color temperature shift) during the night; if omitted, defaults to false</li><li markdown="1">windowfilterDisable - (optional) an `hs.window.filter` instance that will disable color adjustment</li><li markdown="1">   (and color inversion) whenever any window is allowed; alternatively, you can just provide a list of application</li><li markdown="1">   names (typically media apps and/or apps for color-sensitive work) and a windowfilter will be created</li><li markdown="1">   for you that disables color adjustment whenever one of these apps is focused</li><li markdown="1">dayColorTemp - (optional) a number indicating the desired color temperature (in Kelvin) during the day cycle;</li><li markdown="1">   you can use this to maintain some degree of "redshift" during the day as well, or, if desired, you can</li><li markdown="1">   specify a value higher than 6500K (up to 10000K) for more bluish colors, although that's not recommended;</li><li markdown="1">   if omitted, defaults to 6500K, which disables color adjustment and restores your screens' original color profiles</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the module and disables color adjustment and color inversion                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.toggle([v])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets or clears the user override for color temperature adjustment.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">v - (optional) a boolean; if true, the override will enable color temperature adjustment on</li><li markdown="1">   the given schedule; if false, the override will disable color temperature adjustment;</li><li markdown="1">   if omitted or nil, it will toggle the override, i.e. clear it if it's currently enforced, or</li><li markdown="1">   set it to the opposite of the current color temperature adjustment status otherwise.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [toggleInvert](#toggleinvert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.toggleInvert([v])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets or clears the user override for color inversion.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">v - (optional) a boolean; if true, the override will invert the colors no matter what; if false,</li><li markdown="1">   the override will disable color inversion no matter what; if omitted or nil, it will toggle the</li><li markdown="1">   override, i.e. clear it if it's currently enforced, or set it to the opposite of the current</li><li markdown="1">   color inversion status otherwise.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

