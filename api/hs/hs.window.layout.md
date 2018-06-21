# [docs](index.md) » hs.window.layout
---

**WARNING**: EXPERIMENTAL MODULE. DO **NOT** USE IN PRODUCTION.
This module is *for testing purposes only*. It can undergo breaking API changes or *go away entirely* **at any point and without notice**.
(Should you encounter any issues, please feel free to report them on https://github.com/Hammerspoon/hammerspoon/issues
or #hammerspoon on irc.freenode.net)

Window management

Windowlayouts work by selecting certain windows via windowfilters and arranging them onscreen according to specific rules.

A **layout** is composed of a list of rules and, optionally, a screen arrangement definition.
Rules within a layout are evaluated in order; once a window is acted upon by a rule, subsequent rules will not affect it further.
A **rule** needs a **windowfilter**, producing a dynamic list of windows (the "window pool") to which the rule is applied,
and a list of commands, evaluated in order.
A **command** acts on one or more of the windows, and is composed of:
* an **action**, it can be
  - `move`: moves the window(s) to a specified onscreen rect (if the action is omitted, `move` is assumed)
  - `minimize`, `maximize`, `fullscreen`
  - `tile`, `fit`: tiles the windows onto a specified rect, using `hs.window.tiling.tileWindows()`; for `fit`, the
    `preserveRelativeArea` parameter will be set to true
  - `hide`, `unhide`: hides or unhides the window's application (like when using cmd-h)
  - `noaction`: skip action on the window(s)
* a **maxn** number, indicating how many windows from this rule's window pool will be affected (at most) by this command;
  if omitted (or if explicitly the string `all`) all the remaining windows will be processed by this command; processed
  windows are "consumed" and are excluded from the window pool for subsequent commands in this rule, and from subsequent rules
* a **selector**, describing the sort order used to pick the first *maxn* windows from the window pool for this command;
  it can be one of `focused` (pick *maxn* most recently focused windows), `frontmost` (pick the recent focused window if its  
  application is frontmost applicaion, otherwise the command will be skipped), `newest` (most recently created), `oldest`
  (least recently created), or `closest` (pick the *maxn* windows that are closest to the destination rect); if omitted,
  defaults to `closest` for move, tile and fit, and `newest` for everything else
* an `hs.geometry` *size* (only valid for tile and fit) indicating the desired optimal aspect ratio for the tiled windows;
  if omitted, defaults to 1x1 (i.e. square windows)
* for move, tile and fit, an `hs.geometry` *rect*, or a *unit rect* plus a *screen hint* (for `hs.screen.find()`),
  indicating the destination rect for the command
* for fullscreen and maximize, a *screen hint* indicating the desired screen; if omitted, uses the window's current screen

You should place higher-priority rules (with highly specialized windowfilters) first, and "fallback" rules
(with more generic windowfilters) last; similarly, *within* a rule, you should have commands for the more "important"
(i.e. relevant to your current workflow) windows first (move, maximize...) and after that deal with less prominent
windows, if any remain, e.g. by placing them out of the way (minimize).
`unhide` and `hide`, if used, should usually go into their own rules (with a windowfilter that allows invisible windows
for `unhide`) that come *before* other rules that deal with actual window placement - unlike the other actions,
they don't "consume" windows making them unavailable for subsequent rules, as they act on applications.

In order to avoid dealing with deeply nested maps, you can define a layout in your scripts via a list, where each element
(or row) denotes a rule; in turn every rule can be a simplified list of two elements:
  - a windowfilter or a constructor argument table for one (see `hs.window.filter.new()` and `hs.window.filter:setFilters()`)
  - a single string containing all the commands (action and parameters) in order; actions and selectors can be shortened to
    3 characters; all tokens must be separated by spaces (do not use spaces inside `hs.geometry` constructor strings);
    for greater clarity you can separate commands with `|` (pipe character)

Some command string examples:
- `"move 1 [0,0,50,50] -1,0"` moves the closest window to the topleft quadrant of the left screen
- `"max 0,0"` maximizes all the windows onto the primary screen, one on top of another
- `"move 1 foc [0,0,30,100] 0,0 | tile all foc [30,0,100,100] 0,0"` moves the most recently focused window to the left third,
and tiles the remaining windows onto the right side, keeping the most recently focused on top and to the left
- `"1 new [0,0,50,100] 0,0 | 1 new [50,0,100,100] 0,0 | min"` divides the primary screen between the two newest windows
and minimizes any other windows

Each layout can work in "passive" or "active" modes; passive layouts must be triggered manually (via `hs.hotkey.bind()`,
`hs.menubar`, etc.) while active layouts continuously keep their rules enforced (see `hs.window.layout:start()`
for more information); in general you should avoid having multiple active layouts targeting the same windows, as the
results will be unpredictable (if such a situation is detected, you'll see an error in the Hammerspoon console); you
*can* have multiple active layouts, but be careful to maintain a clear "separation of concerns" between their respective windowfilters.

Each layout can have an associated screen configuration; if so, the layout will only be valid while the current screen
arrangement satisfies it; see `hs.window.layout:setScreenConfiguration()` for more information.

## API Overview
* Variables - Configurable values
 * [applyDelay](#applydelay)
 * [screensChangedDelay](#screenschangeddelay)
* Functions - API calls offered directly by the extension
 * [applyLayout](#applylayout)
 * [pauseAllInstances](#pauseallinstances)
 * [resumeAllInstances](#resumeallinstances)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [apply](#apply)
 * [getRules](#getrules)
 * [pause](#pause)
 * [resume](#resume)
 * [setScreenConfiguration](#setscreenconfiguration)
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Variables

#### [applyDelay](#applydelay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout.applyDelay` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | When "active mode" windowlayouts apply a rule, they will pause briefly for this amount of time in seconds, to allow windows                                                                                         |

#### [screensChangedDelay](#screenschangeddelay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout.screensChangedDelay` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The number of seconds to wait, after a screen configuration change has been detected, before                                                                                         |

### Functions

#### [applyLayout](#applylayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout.applyLayout(rules)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Applies a layout                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">rules - see `hs.window.layout.new()`</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">this is a convenience wrapper for "passive mode" use that creates, applies, and deletes a windowlayout object;</li><li markdown="1">   do *not* use shared windowfilters in `rules`, as they'll be deleted; you can just use constructor argument maps instead</li></ul>                |

#### [pauseAllInstances](#pauseallinstances)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout.pauseAllInstances()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Pauses all active windowlayout instances                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [resumeAllInstances](#resumeallinstances)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout.resumeAllInstances()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resumes all active windowlayout instances                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout.new(rules[,logname[,loglevel]]) -> hs.window.layout object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new hs.window.layout instance                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">rules - a table containing the rules for this windowlayout (see the module description); additionally, if a special key `screens`</li><li markdown="1">   is present, its value must be a valid screen configuration as per `hs.window.layout:setScreenConfiguration()`</li><li markdown="1">logname - (optional) name of the `hs.logger` instance for the new windowlayout; if omitted, the class logger will be used</li><li markdown="1">loglevel - (optional) log level for the `hs.logger` instance for the new windowlayout</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a new windowlayout instance</li></ul>          |

### Methods

#### [apply](#apply)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout:apply()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies the layout                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the `hs.window.layout` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">if a screen configuration is defined for this windowfilter, and currently not satisfied, this method will do nothing</li></ul>                |

#### [getRules](#getrules)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout:getRules() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a table with all the rules (and the screen configuration, if present) defined for this windowlayout                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a table containing the rules of this windowlayout; you can pass this table (optionally</li><li markdown="1">   after performing valid manipulations) to `hs.window.layout.new()`</li></ul>          |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout:pause() -> hs.window.layout object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Pauses an active windowlayout instance; while paused no automatic window management will occur                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the `hs.window.layout` object</li></ul>          |

#### [resume](#resume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout:resume() -> hs.window.layout object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resumes an active windowlayout instance after it was paused                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the `hs.window.layout` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">if a screen configuration is defined for this windowfilter, and currently not satisfied, this method will do nothing</li></ul>                |

#### [setScreenConfiguration](#setscreenconfiguration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout:setScreenConfiguration(screens) -> hs.window.layout object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determines the screen configuration that permits applying this windowlayout                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">screens - a map, where each *key* must be a valid "hint" for `hs.screen.find()`, and the corresponding</li><li markdown="1">   value can be:</li><li markdown="1">  `true` - the screen must be currently present (attached and enabled)</li><li markdown="1">  `false` - the screen must be currently absent</li><li markdown="1">  an `hs.geometry` point (or constructor argument) - the screen must be present and in this specific</li><li markdown="1">     position in the current arragement (as per `hs.screen:position()`)</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the `hs.window.layout` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">if `screens` is `nil`, any previous screen configuration is removed, and this windowlayout will be always allowed</li><li markdown="1">for "active" windowlayouts, call this method *before* calling `hs.window.layout:start()`</li><li markdown="1">by using `hs.geometry` size objects as hints you can define separate layouts for the same physical</li><li markdown="1">   screen at different resolutions</li></ul>                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout:start() -> hs.window.layout object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Puts a windowlayout instance in "active mode"                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the `hs.window.layout` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">if a screen configuration is defined for this windowfilter, and currently not satisfied, this</li><li markdown="1">   windowfilter will be put in "active mode" but will remain paused until the screen configuration</li><li markdown="1">   requirements are met</li></ul>                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.layout:stop() -> hs.window.layout object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops a windowlayout instance (i.e. not in "active mode" anymore)                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the `hs.window.layout` object</li></ul>          |

