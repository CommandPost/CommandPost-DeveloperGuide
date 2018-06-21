# [docs](index.md) » hs.expose
---

Keyboard-driven expose replacement/enhancement

Warning: this module is still somewhat experimental.
Should you encounter any issues, please feel free to report them on https://github.com/Hammerspoon/hammerspoon/issues
or #hammerspoon on irc.freenode.net

With this module you can configure a hotkey to show thumbnails for open windows when invoked; each thumbnail will have
an associated keyboard "hint" (usually one or two characters) that you can type to quickly switch focus to that
window; in conjunction with keyboard modifiers, you can additionally minimize (`alt` by default) or close
(`shift` by default) any window without having to focus it first.

When used in combination with a windowfilter you can include or exclude specific apps, window titles, screens,
window roles, etc. Additionally, each expose instance can be customized to include or exclude minimized or hidden windows,
windows residing in other Mission Control Spaces, or only windows for the current application. You can further customize
hint length, colors, fonts and sizes, whether to show window thumbnails and/or titles, and more.

To improve responsiveness, this module will update its thumbnail layout in the background (so to speak), so that it
can show the expose without delay on invocation. Be aware that on particularly heavy Hammerspoon configurations
this could adversely affect overall performance; you can disable this behaviour with
`hs.expose.ui.fitWindowsInBackground=false`

Usage:
```
-- set up your instance(s)
expose = hs.expose.new(nil,{showThumbnails=false}) -- default windowfilter, no thumbnails
expose_app = hs.expose.new(nil,{onlyActiveApplication=true}) -- show windows for the current application
expose_space = hs.expose.new(nil,{includeOtherSpaces=false}) -- only windows in the current Mission Control Space
expose_browsers = hs.expose.new{'Safari','Google Chrome'} -- specialized expose using a custom windowfilter
-- for your dozens of browser windows :)

-- then bind to a hotkey
hs.hotkey.bind('ctrl-cmd','e','Expose',function()expose:toggleShow()end)
hs.hotkey.bind('ctrl-cmd-shift','e','App Expose',function()expose_app:toggleShow()end)
```

## API Overview
* Variables - Configurable values
 * [ui](#ui)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [hide](#hide)
 * [show](#show)
 * [toggleShow](#toggleshow)

## API Documentation

### Variables

#### [ui](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.expose.ui` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Allows customization of the expose behaviour and user interface                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.expose.new([windowfilter[, uiPrefs][, logname, [loglevel]]]) -> hs.expose object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new hs.expose instance; it can use a windowfilter to determine which windows to show                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">windowfilter - (optional) if omitted or nil, use the default windowfilter; otherwise it must be a windowfilter</li><li markdown="1">   instance or constructor table</li><li markdown="1">uiPrefs - (optional) a table to override UI preferences for this instance; its keys and values</li><li markdown="1">   must follow the conventions described in `hs.expose.ui`; this parameter allows you to have multiple</li><li markdown="1">   expose instances with different behaviour (for example, with and without thumbnails and/or titles)</li><li markdown="1">   using different hotkeys</li><li markdown="1">logname - (optional) name of the `hs.logger` instance for the new expose; if omitted, the class logger will be used</li><li markdown="1">loglevel - (optional) log level for the `hs.logger` instance for the new expose</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the new instance</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1"> by default expose will show invisible windows and (unlike the OSX expose) windows from other spaces; use</li><li markdown="1">    `hs.expose.ui` or the `uiPrefs` parameter to change these behaviours.</li></ul>                |

### Methods

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.expose:hide()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the expose, if visible, and exits the modal mode.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.expose:show([activeApplication])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows an expose-like screen with modal keyboard hints for switching to, closing or minimizing/unminimizing windows.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">activeApplication - (optional) if true, only show windows of the active application (within the</li><li markdown="1">  scope of the instance windowfilter); otherwise show all windows allowed by the instance windowfilter</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">passing `true` for `activeApplication` will simply hide hints/thumbnails for applications other</li><li markdown="1">   than the active one, without recalculating the hints layout; conversely, setting `onlyActiveApplication=true`</li><li markdown="1">   for an expose instance's `ui` will calculate an optimal layout for the current active application's windows</li><li markdown="1">Completing a hint will exit the expose and focus the selected window.</li><li markdown="1">Pressing esc will exit the expose and with no action taken.</li><li markdown="1">If shift is being held when a hint is completed (the background will be red), the selected</li><li markdown="1">   window will be closed. If it's the last window of an application, the application will be closed.</li><li markdown="1">If alt is being held when a hint is completed (the background will be blue), the selected</li><li markdown="1">   window will be minimized (if visible) or unminimized/unhidden (if minimized or hidden).</li></ul>                |

#### [toggleShow](#toggleshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.expose:toggleShow([activeApplication])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggles the expose - see `hs.expose:show()` and `hs.expose:hide()`                                                                                         |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

