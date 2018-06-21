# [docs](index.md) » hs.window.switcher
---

Window-based cmd-tab replacement

Usage:
```
-- set up your windowfilter
switcher = hs.window.switcher.new() -- default windowfilter: only visible windows, all Spaces
switcher_space = hs.window.switcher.new(hs.window.filter.new():setCurrentSpace(true):setDefaultFilter{}) -- include minimized/hidden windows, current Space only
switcher_browsers = hs.window.switcher.new{'Safari','Google Chrome'} -- specialized switcher for your dozens of browser windows :)

-- bind to hotkeys; WARNING: at least one modifier key is required!
hs.hotkey.bind('alt','tab','Next window',function()switcher:next()end)
hs.hotkey.bind('alt-shift','tab','Prev window',function()switcher:previous()end)

-- alternatively, call .nextWindow() or .previousWindow() directly (same as hs.window.switcher.new():next())
hs.hotkey.bind('alt','tab','Next window',hs.window.switcher.nextWindow)
-- you can also bind to `repeatFn` for faster traversing
hs.hotkey.bind('alt-shift','tab','Prev window',hs.window.switcher.previousWindow,nil,hs.window.switcher.previousWindow)
```

## API Overview
* Variables - Configurable values
 * [ui](#ui)
* Functions - API calls offered directly by the extension
 * [nextWindow](#nextwindow)
 * [previousWindow](#previouswindow)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [next](#next)
 * [previous](#previous)

## API Documentation

### Variables

#### [ui](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.switcher.ui` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Allows customization of the switcher behaviour and user interface                                                                                         |

### Functions

#### [nextWindow](#nextwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.switcher.nextWindow()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the switcher (if not yet visible) and selects the next window                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">the switcher will be dismissed (and the selected window focused) when all modifier keys are released</li></ul>                |

#### [previousWindow](#previouswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.switcher.previousWindow()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the switcher (if not yet visible) and selects the previous window                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">the switcher will be dismissed (and the selected window focused) when all modifier keys are released</li></ul>                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.switcher.new([windowfilter[, uiPrefs][, logname, [loglevel]]]) -> hs.window.switcher object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new switcher instance; it can use a windowfilter to determine which windows to show                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">windowfilter - (optional) if omitted or nil, use the default windowfilter; otherwise it must be a windowfilter</li><li markdown="1">   instance or constructor table</li><li markdown="1">uiPrefs - (optional) a table to override UI preferences for this instance; its keys and values</li><li markdown="1">   must follow the conventions described in `hs.window.switcher.ui`; this parameter allows you to have multiple</li><li markdown="1">   switcher instances with different behaviour (for example, with and without thumbnails and/or titles)</li><li markdown="1">   using different hotkeys</li><li markdown="1">logname - (optional) name of the `hs.logger` instance for the new switcher; if omitted, the class logger will be used</li><li markdown="1">loglevel - (optional) log level for the `hs.logger` instance for the new switcher</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the new instance</li></ul>          |

### Methods

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.switcher:next()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the switcher instance (if not yet visible) and selects the next window                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">the switcher will be dismissed (and the selected window focused) when all modifier keys are released</li></ul>                |

#### [previous](#previous)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.switcher:previous()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the switcher instance (if not yet visible) and selects the previous window                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">the switcher will be dismissed (and the selected window focused) when all modifier keys are released</li></ul>                |

