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
| **Notes**                                            | <ul><li><code>hs.inspect(hs.redshift.COLORRAMP)</code> from the console will show you how the table is built</li></ul><ul><li>the default ramp has entries from 1000K to 10000K every 100K</li></ul>                 |

### Functions

#### [invertSubscribe](#invertsubscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.invertSubscribe([id,]fn)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Subscribes a callback to be notified when the color inversion status changes                                                                                         |
| **Parameters**                                       | <ul><li>id - (optional) a string identifying the requester (usually the module name); if omitted, <code>fn</code></li></ul><p>itself will be the identifier; this identifier must be passed to <code>hs.redshift.invertUnsubscribe()</code></p><ul><li>fn - a function that will be called whenever color inversion status changes; it must accept a</li></ul><p>single parameter, a string or false as per the return value of <code>hs.redshift.isInverted()</code></p>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [invertUnsubscribe](#invertunsubscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.invertUnsubscribe(id)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unsubscribes a previously subscribed color inversion change callback                                                                                         |
| **Parameters**                                       | <ul><li>id - a string identifying the requester or the callback function itself, depending on how you</li></ul><p>called <code>hs.redshift.invertSubscribe()</code></p>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [isInverted](#isinverted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.isInverted() -> string or false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the colors are currently inverted                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>false if the colors are not currently inverted; otherwise, a string indicating the reason, one of:</li></ul><ul><li>"user" for the user override (see <code>hs.redshift.toggleInvert()</code>)</li></ul><ul><li>"redshift-night" if <code>hs.redshift.start()</code> was called with <code>invertAtNight</code> set to true,</li></ul><pre><code> and it's currently night time</code></pre><ul><li>the ID string (usually the module name) provided to <code>hs.redshift.requestInvert()</code>, if another module requested color inversion</li></ul>            |

#### [requestInvert](#requestinvert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.requestInvert(id,v)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets or clears a request for color inversion                                                                                         |
| **Parameters**                                       | <ul><li>id - a string identifying the requester (usually the module name)</li></ul><ul><li>v - a boolean indicating whether to invert the colors (if true) or clear any previous requests (if false or nil)</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>you can use this function e.g. to automatically invert colors if the ambient light sensor reading drops below</li></ul><p>a certain threshold (<code>hs.brightness.DDCauto()</code> can optionally do exactly that)</p><ul><li>if the user's configuration doesn't explicitly start the redshift module, calling this will have no effect</li></ul>                 |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.start(colorTemp,nightStart,nightEnd[,transition[,invertAtNight[,windowfilterDisable[,dayColorTemp]]]])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the schedule and (re)starts the module                                                                                         |
| **Parameters**                                       | <ul><li>colorTemp - a number indicating the desired color temperature (Kelvin) during the night cycle;</li></ul><p>the recommended range is between 3600K and 1400K; lower values (minimum 1000K) result in a more pronounced adjustment</p><ul><li>nightStart - a string in the format "HH:MM" (24-hour clock) or number of seconds after midnight</li></ul><p>(see <code>hs.timer.seconds()</code>) indicating when the night cycle should start</p><ul><li>nightEnd - a string in the format "HH:MM" (24-hour clock) or number of seconds after midnight</li></ul><p>(see <code>hs.timer.seconds()</code>) indicating when the night cycle should end</p><ul><li>transition - (optional) a string or number of seconds (see <code>hs.timer.seconds()</code>) indicating the duration of</li></ul><p>the transition to the night color temperature and back; if omitted, defaults to 1 hour</p><ul><li>invertAtNight - (optional) a boolean indicating whether the colors should be inverted (in addition to</li></ul><p>the color temperature shift) during the night; if omitted, defaults to false</p><ul><li>windowfilterDisable - (optional) an <code>hs.window.filter</code> instance that will disable color adjustment</li></ul><p>(and color inversion) whenever any window is allowed; alternatively, you can just provide a list of application</p><p>names (typically media apps and/or apps for color-sensitive work) and a windowfilter will be created</p><p>for you that disables color adjustment whenever one of these apps is focused</p><ul><li>dayColorTemp - (optional) a number indicating the desired color temperature (in Kelvin) during the day cycle;</li></ul><p>you can use this to maintain some degree of "redshift" during the day as well, or, if desired, you can</p><p>specify a value higher than 6500K (up to 10000K) for more bluish colors, although that's not recommended;</p><p>if omitted, defaults to 6500K, which disables color adjustment and restores your screens' original color profiles</p>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the module and disables color adjustment and color inversion                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.toggle([v])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets or clears the user override for color temperature adjustment.                                                                                         |
| **Parameters**                                       | <ul><li>v - (optional) a boolean; if true, the override will enable color temperature adjustment on</li></ul><p>the given schedule; if false, the override will disable color temperature adjustment;</p><p>if omitted or nil, it will toggle the override, i.e. clear it if it's currently enforced, or</p><p>set it to the opposite of the current color temperature adjustment status otherwise.</p>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [toggleInvert](#toggleinvert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.redshift.toggleInvert([v])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets or clears the user override for color inversion.                                                                                         |
| **Parameters**                                       | <ul><li>v - (optional) a boolean; if true, the override will invert the colors no matter what; if false,</li></ul><p>the override will disable color inversion no matter what; if omitted or nil, it will toggle the</p><p>override, i.e. clear it if it's currently enforced, or set it to the opposite of the current</p><p>color inversion status otherwise.</p>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

