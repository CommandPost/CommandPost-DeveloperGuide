# [docs](index.md) » hs.window.filter
---

Filter windows by application, title, location on screen and more, and easily subscribe to events on these windows

Warning: this module is still somewhat experimental.
Should you encounter any issues, please feel free to report them on https://github.com/Hammerspoon/hammerspoon/issues
or #hammerspoon on irc.freenode.net

Windowfilters monitor all windows as they're created, closed, moved etc., and select some (or none) among these windows
according to specific filtering rules. These filtering rules are app-specific, i.e. they start off by selecting all windows
belonging to a certain application (but you can also define *default* and *override* filters - see `:setAppFilter()`,
`:setDefaultFilter()`, `:setOverrideFilter()`) and they can allow or reject windows based on:
  * visibility, focused and/or fullscreen status
  * title length or patterns in the title
  * position on screen (inside or outside a certain region or screen)
  * accessibility role (standard window, dialog, etc.)
  * whether they're in the current Mission Control Space or not

The filtering happens automatically in the background; windowfilters then:
  * generate a dynamic list of the windows that currently satisfy the filtering rules (see `:getWindows()`)
  * sanitize and expose all pertinent events on these windows (see `:subscribe()` and the module constants with all the events)

A *default windowfilter* (not to be confused with the default filter *within* a windowfilter) is provided as convenience;
it excludes some known apps and windows that are transient in nature, therefore unlikely to be "interesting" for e.g. window management.
`hs.window.filter.new()` (with no arguments) returns a copy of the default windowfilter that you can further tailor
to your needs - see `hs.window.filter.default` and `hs.window.filter.new()` for more information.

Usage examples:
```
local wf=hs.window.filter

-- alter the default windowfilter
wf.default:setAppFilter('My IDE',{allowTitles=1}) -- ignore no-title windows (e.g. transient autocomplete suggestions) in My IDE

-- set the exact scope of what you're interested in - see hs.window.filter:setAppFilter()
wf_terminal = wf.new{'Terminal','iTerm2'} -- all visible terminal windows
wf_timewaster = wf.new(false):setAppFilter('Safari',{allowTitles='reddit'}) -- any Safari windows with "reddit" anywhere in the title
wf_leftscreen = wf.new{override={visible=true,fullscreen=false,allowScreens='-1,0',currentSpace=true}}
-- all visible and non-fullscreen windows that are on the screen to the left of the primary screen in the current Space
wf_editors_righthalf = wf.new{'TextEdit','Sublime Text','BBEdit'}:setRegions(hs.screen.primaryScreen():fromUnitRect'0.5,0/1,1')
-- text editor windows that are on the right half of the primary screen
wf_bigwindows = wf.new(function(w)return w:frame().area>3000000 end) -- only very large windows
wf_notif = wf.new{['Notification Center']={allowRoles='AXNotificationCenterAlert'}} -- notification center alerts

-- subscribe to events
wf_terminal:subscribe(wf.windowFocused,some_fn) -- run a function whenever a terminal window is focused
wf_timewaster:subscribe(wf.hasWindow,startAnnoyingMe):subscribe(wf.hasNoWindows,stopAnnoyingMe) -- fight procrastination :)
```

## API Overview
* Constants - Useful values which cannot be changed
 * [default](#default)
 * [defaultCurrentSpace](#defaultcurrentspace)
 * [hasNoWindows](#hasnowindows)
 * [hasWindow](#haswindow)
 * [sortByCreated](#sortbycreated)
 * [sortByCreatedLast](#sortbycreatedlast)
 * [sortByFocused](#sortbyfocused)
 * [sortByFocusedLast](#sortbyfocusedlast)
 * [windowAllowed](#windowallowed)
 * [windowCreated](#windowcreated)
 * [windowDestroyed](#windowdestroyed)
 * [windowFocused](#windowfocused)
 * [windowFullscreened](#windowfullscreened)
 * [windowHidden](#windowhidden)
 * [windowInCurrentSpace](#windowincurrentspace)
 * [windowMinimized](#windowminimized)
 * [windowMoved](#windowmoved)
 * [windowNotInCurrentSpace](#windownotincurrentspace)
 * [windowNotOnScreen](#windownotonscreen)
 * [windowNotVisible](#windownotvisible)
 * [windowOnScreen](#windowonscreen)
 * [windowRejected](#windowrejected)
 * [windowsChanged](#windowschanged)
 * [windowTitleChanged](#windowtitlechanged)
 * [windowUnfocused](#windowunfocused)
 * [windowUnfullscreened](#windowunfullscreened)
 * [windowUnhidden](#windowunhidden)
 * [windowUnminimized](#windowunminimized)
 * [windowVisible](#windowvisible)
* Variables - Configurable values
 * [allowedWindowRoles](#allowedwindowroles)
 * [forceRefreshOnSpaceChange](#forcerefreshonspacechange)
 * [ignoreAlways](#ignorealways)
* Functions - API calls offered directly by the extension
 * [focusEast](#focuseast)
 * [focusNorth](#focusnorth)
 * [focusSouth](#focussouth)
 * [focusWest](#focuswest)
 * [isGuiApp](#isguiapp)
 * [switchedToSpace](#switchedtospace)
* Constructors - API calls which return an object, typically one that offers API methods
 * [copy](#copy)
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [allowApp](#allowapp)
 * [focusWindowEast](#focuswindoweast)
 * [focusWindowNorth](#focuswindownorth)
 * [focusWindowSouth](#focuswindowsouth)
 * [focusWindowWest](#focuswindowwest)
 * [getFilters](#getfilters)
 * [getWindows](#getwindows)
 * [isAppAllowed](#isappallowed)
 * [isWindowAllowed](#iswindowallowed)
 * [pause](#pause)
 * [rejectApp](#rejectapp)
 * [resume](#resume)
 * [setAppFilter](#setappfilter)
 * [setCurrentSpace](#setcurrentspace)
 * [setDefaultFilter](#setdefaultfilter)
 * [setFilters](#setfilters)
 * [setOverrideFilter](#setoverridefilter)
 * [setRegions](#setregions)
 * [setScreens](#setscreens)
 * [setSortOrder](#setsortorder)
 * [subscribe](#subscribe)
 * [unsubscribe](#unsubscribe)
 * [unsubscribeAll](#unsubscribeall)
 * [windowsToEast](#windowstoeast)
 * [windowsToNorth](#windowstonorth)
 * [windowsToSouth](#windowstosouth)
 * [windowsToWest](#windowstowest)

## API Documentation

### Constants

#### [default](#default)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.default` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The default windowfilter; it filters apps whose windows are transient in nature so that you're unlikely (and often |
| **Notes**                                            | <ul><li>While you can customize the default windowfilter, it's usually advisable to make your customizations on a local copy via <code>mywf=hs.window.filter.new()</code>;   the default windowfilter can potentially be used in several Hammerspoon modules and changing it might have unintended consequences.   Common customizations:</li><li>to exclude fullscreen windows: <code>nofs_wf=hs.window.filter.new():setOverrideFilter{fullscreen=false}</code></li><li>to include invisible windows: <code>inv_wf=windowfilter.new():setDefaultFilter{}</code></li><li>If you still want to alter the default windowfilter:</li><li>you should probably apply your customizations at the top of your <code>init.lua</code>, or at any rate before instantiating any other windowfilter; this     way copies created via <code>hs.window.filter.new(nil,...)</code> will inherit your modifications</li><li>to list the known exclusions: <code>hs.inspect(hs.window.filter.default:getFilters())</code> from the console</li><li>to add an exclusion: <code>hs.window.filter.default:rejectApp'Cool New Launcher'</code></li><li>to add an app-specific rule: <code>hs.window.filter.default:setAppFilter('My IDE',1)</code>; ignore tooltips/code completion (empty title) in My IDE</li><li>to remove an exclusion (e.g. if you want to have access to Spotlight windows): <code>hs.window.filter.default:allowApp'Spotlight'</code>;     for specialized uses you can make a specific windowfilter with <code>myfilter=hs.window.filter.new'Spotlight'</code></li></ul> |

#### [defaultCurrentSpace](#defaultcurrentspace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.defaultCurrentSpace` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A copy of the default windowfilter (see `hs.window.filter.default`) that only allows windows in the current |
| **Notes**                                            | <ul><li>This windowfilter will inherit customizations to the default windowfilter if they're performed <em>before</em> referencing this</li></ul> |

#### [hasNoWindows](#hasnowindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.hasNoWindows` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Pseudo-event for `hs.window.filter:subscribe()`: the windowfilter now rejects all windows |
| **Notes**                                            | <ul><li>callbacks for this event will receive (as the first argument) the last window that was allowed (and is now rejected)</li><li>this pseudo-event won't trigger again until after the windowfilter allows at least one window</li><li>this pseudo-event will be emitted <em>after</em> the <em>actual</em> event(s) (e.g. <code>windowDestroyed</code>) that caused the window to be rejected</li></ul> |

#### [hasWindow](#haswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.hasWindow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Pseudo-event for `hs.window.filter:subscribe()`: the windowfilter now allows one window |
| **Notes**                                            | <ul><li>callbacks for this event will receive (as the first argument) the window that is now allowed</li><li>this pseudo-event won't trigger again until after the windowfilter reverts to rejecting all windows</li><li>this pseudo-event will be emitted <em>after</em> the <em>actual</em> event(s) (e.g. <code>windowCreated</code>) that caused a window to be allowed</li></ul> |

#### [sortByCreated](#sortbycreated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.sortByCreated` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Sort order for `hs.window.filter:getWindows()`: windows are sorted in order of creation, oldest first (see also `hs.window.filter:setSortOrder()`) |

#### [sortByCreatedLast](#sortbycreatedlast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.sortByCreatedLast` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Sort order for `hs.window.filter:getWindows()`: windows are sorted in order of creation, newest first (see also `hs.window.filter:setSortOrder()`) |

#### [sortByFocused](#sortbyfocused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.sortByFocused` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Sort order for `hs.window.filter:getWindows()`: windows are sorted in order of focus received, least recently first (see also `hs.window.filter:setSortOrder()`) |

#### [sortByFocusedLast](#sortbyfocusedlast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.sortByFocusedLast` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Sort order for `hs.window.filter:getWindows()`: windows are sorted in order of focus received, most recently first (see also `hs.window.filter:setSortOrder()`) |
| **Notes**                                            | <ul><li>This is the default sort order for all windowfilters</li></ul> |

#### [windowAllowed](#windowallowed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowAllowed` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Pseudo-event for `hs.window.filter:subscribe()`: a previously rejected window (or a newly created one) is now allowed |
| **Notes**                                            | <ul><li>this pseudo-event will be emitted <em>before</em> the <em>actual</em> event(s) (e.g. <code>windowCreated</code>) that caused the window to be allowed</li></ul> |

#### [windowCreated](#windowcreated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowCreated` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a new window was created |

#### [windowDestroyed](#windowdestroyed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowDestroyed` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window was destroyed |

#### [windowFocused](#windowfocused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowFocused` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window received focus |

#### [windowFullscreened](#windowfullscreened)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowFullscreened` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window was expanded to fullscreen |

#### [windowHidden](#windowhidden)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowHidden` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window was hidden (its app was hidden, e.g. via `cmd-h`) |

#### [windowInCurrentSpace](#windowincurrentspace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowInCurrentSpace` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window is now in the current Mission Control Space, due to |

#### [windowMinimized](#windowminimized)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowMinimized` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window was minimized |

#### [windowMoved](#windowmoved)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowMoved` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window was moved or resized, including toggling fullscreen/maximize |

#### [windowNotInCurrentSpace](#windownotincurrentspace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowNotInCurrentSpace` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window that used to be in the current Mission Control Space isn't anymore, |

#### [windowNotOnScreen](#windownotonscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowNotOnScreen` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window is no longer *actually* visible on any screen because it was minimized, closed, |

#### [windowNotVisible](#windownotvisible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowNotVisible` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window is no longer "visible" (in *any* Mission Control Space, as per `hs.window:isVisible()`) |

#### [windowOnScreen](#windowonscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowOnScreen` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window became *actually* visible on screen (i.e. it's "visible" as per `hs.window:isVisible()` |

#### [windowRejected](#windowrejected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowRejected` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Pseudo-event for `hs.window.filter:subscribe()`: a previously allowed window (or a window that's been destroyed) is now rejected |
| **Notes**                                            | <ul><li>this pseudo-event will be emitted <em>after</em> the <em>actual</em> event(s) (e.g. <code>windowDestroyed</code>) that caused the window to be rejected</li></ul> |

#### [windowsChanged](#windowschanged)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowsChanged` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Pseudo-event for `hs.window.filter:subscribe()`: the list of allowed windows (as per `windowfilter:getWindows()`) has changed |
| **Notes**                                            | <ul><li>callbacks for this event will receive (as the first argument) either a random window among the currently allowed ones,   or nil if the windowfilter is rejecting all windows</li><li>similarly, the second argument passed to callbacks (window's app name) will be nil if the windowfilter is rejecting all windows</li><li>this pseudo-event will be emitted <em>after</em> the <em>actual</em> event(s) that caused the list of allowed windows to change</li></ul> |

#### [windowTitleChanged](#windowtitlechanged)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowTitleChanged` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window's title changed |

#### [windowUnfocused](#windowunfocused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowUnfocused` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window lost focus |

#### [windowUnfullscreened](#windowunfullscreened)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowUnfullscreened` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window was reverted back from fullscreen |

#### [windowUnhidden](#windowunhidden)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowUnhidden` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window was unhidden (its app was unhidden, e.g. via `cmd-h`) |

#### [windowUnminimized](#windowunminimized)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowUnminimized` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window was unminimized |

#### [windowVisible](#windowvisible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.windowVisible` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Event for `hs.window.filter:subscribe()`: a window became "visible" (in *any* Mission Control Space, as per `hs.window:isVisible()`) |

### Variables

#### [allowedWindowRoles](#allowedwindowroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.allowedWindowRoles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A table for window roles (as per `hs.window:subrole()`) that are allowed by default. |
| **Notes**                                            | <ul><li>You can have fine grained control of allowed window roles via the <code>setAppFilter</code>, <code>setDefaultFilter</code>, <code>setOverrideFilter</code> methods.</li><li>If you know what you're doing you can override the allowed window roles globally by changing this variable, but this is discouraged.</li></ul> |

#### [forceRefreshOnSpaceChange](#forcerefreshonspacechange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.forceRefreshOnSpaceChange` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Tells all windowfilters whether to refresh all windows when the user switches to a different Mission Control Space. |
| **Notes**                                            | <ul><li>If you defined one or more Spaces-aware windowfilters (i.e. when the <code>currentSpace</code> field of a filter is present), windows need refreshing at every space change anyway, so this variable is ignored</li></ul> |

#### [ignoreAlways](#ignorealways)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.ignoreAlways` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A table of application names (as per `hs.application:name()`) that are always ignored by this module. |
| **Notes**                                            | <ul><li>As the name implies, even the empty, "allow all" windowfilter will ignore these apps.</li><li>You don't <em>need</em> to keep this table up to date, since non GUI apps will simply never show up anywhere; this table is just used as a "root" filter to gain a (very small) performance improvement.</li></ul> |

### Functions

#### [focusEast](#focuseast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.focusEast()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Convenience function to focus the nearest window to the east |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that performs <code>hs.window.filter.defaultCurrentSpace:focusWindowEast(nil,nil,true)</code></li></ul> |

#### [focusNorth](#focusnorth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.focusNorth()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Convenience function to focus the nearest window to the north |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that performs <code>hs.window.filter.defaultCurrentSpace:focusWindowNorth(nil,nil,true)</code></li></ul> |

#### [focusSouth](#focussouth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.focusSouth()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Convenience function to focus the nearest window to the south |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that performs <code>hs.window.filter.defaultCurrentSpace:focusWindowSouth(nil,nil,true)</code></li></ul> |

#### [focusWest](#focuswest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.focusWest()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Convenience function to focus the nearest window to the west |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that performs <code>hs.window.filter.defaultCurrentSpace:focusWindowWest(nil,nil,true)</code></li></ul> |

#### [isGuiApp](#isguiapp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.isGuiApp(appname) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks whether an app is a known non-GUI app, as per `hs.window.filter.ignoreAlways` |
| **Parameters**                                       | <ul><li>appname - name of the app to check as per <code>hs.application:name()</code></li></ul> |
| **Returns**                                          | <ul><li><code>false</code> if the app is a known non-GUI (or not accessible) app; <code>true</code> otherwise</li></ul> |

#### [switchedToSpace](#switchedtospace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.switchedToSpace(space)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Callback to inform all windowfilters that the user initiated a switch to a (numbered) Mission Control Space. |
| **Parameters**                                       | <ul><li>space - the Space number the user is switching to</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>Only use this function if "Displays have separate Spaces" and "Automatically rearrange Spaces" are OFF in System Preferences&gt;Mission Control</li><li>Calling this function will set <code>hs.window.filter.forceRefreshOnSpaceChange</code> to <code>false</code></li><li>If you defined one or more Spaces-aware windowfilters (i.e. when the <code>currentSpace</code> field of a filter is present), windows need refreshing at every space change anyway, so using this callback will not result in improved performance</li></ul> |

### Constructors

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.copy(windowfilter[,logname[,loglevel]]) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns a copy of an hs.window.filter object that you can further restrict or expand |
| **Parameters**                                       | <ul><li>windowfilter - an <code>hs.window.filter</code> object to copy</li><li>logname - (optional) name of the <code>hs.logger</code> instance for the new windowfilter; if omitted, the class logger will be used</li><li>loglevel - (optional) log level for the <code>hs.logger</code> instance for the new windowfilter</li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter.new(fn[,logname[,loglevel]]) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new hs.window.filter instance |
| **Parameters**                                       | <ul><li>fn</li><li>if <code>nil</code>, returns a copy of the default windowfilter, including any customizations you might have applied to it     so far; you can then further restrict or expand it</li><li>if <code>true</code>, returns an empty windowfilter that allows every window</li><li>if <code>false</code>, returns a windowfilter with a default rule to reject every window</li><li>if a string or table of strings, returns a windowfilter that only allows visible windows of the specified apps     as per <code>hs.application:name()</code></li><li>if a table, you can fully define a windowfilter without having to call any methods after construction; the     table must be structured as per <code>hs.window.filter:setFilters()</code>; if not specified in the table, the     default filter in the new windowfilter will reject all windows</li><li>otherwise it must be a function that accepts an <code>hs.window</code> object and returns <code>true</code> if the window is allowed     or <code>false</code> otherwise; this way you can define a fully custom windowfilter</li><li>logname - (optional) name of the <code>hs.logger</code> instance for the new windowfilter; if omitted, the class logger will be used</li><li>loglevel - (optional) log level for the <code>hs.logger</code> instance for the new windowfilter</li></ul> |
| **Returns**                                          | <ul><li>a new windowfilter instance</li></ul> |

### Methods

#### [allowApp](#allowapp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:allowApp(appname) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the windowfilter to allow all visible windows belonging to a specific app |
| **Parameters**                                       | <ul><li>appname - app name as per <code>hs.application:name()</code></li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>this is just a convenience wrapper for <code>windowfilter:setAppFilter(appname,{visible=true})</code></li></ul> |

#### [focusWindowEast](#focuswindoweast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:focusWindowEast(window, frontmost, strict)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Focuses the nearest window to the east of a given window |
| **Parameters**                                       | <ul><li>window - (optional) an <code>hs.window</code> object; if nil, <code>hs.window.frontmostWindow()</code> will be used</li><li>frontmost - (optional) boolean, if true focuses the nearest window that isn't occluded by any other window in this windowfilter</li><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   eastward axis</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that performs <code>hs.window.focusWindowEast(window,self:getWindows(),...)</code></li><li>You'll likely want to add <code>:setCurrentSpace(true)</code> to the windowfilter used for this method call</li></ul> |

#### [focusWindowNorth](#focuswindownorth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:focusWindowNorth(window, frontmost, strict)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Focuses the nearest window to the south of a given window |
| **Parameters**                                       | <ul><li>window - (optional) an <code>hs.window</code> object; if nil, <code>hs.window.frontmostWindow()</code> will be used</li><li>frontmost - (optional) boolean, if true focuses the nearest window that isn't occluded by any other window in this windowfilter</li><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   southward axis</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that performs <code>hs.window.focusWindowNorth(window,self:getWindows(),...)</code></li><li>You'll likely want to add <code>:setCurrentSpace(true)</code> to the windowfilter used for this method call</li></ul> |

#### [focusWindowSouth](#focuswindowsouth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:focusWindowSouth(window, frontmost, strict)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Focuses the nearest window to the north of a given window |
| **Parameters**                                       | <ul><li>window - (optional) an <code>hs.window</code> object; if nil, <code>hs.window.frontmostWindow()</code> will be used</li><li>frontmost - (optional) boolean, if true focuses the nearest window that isn't occluded by any other window in this windowfilter</li><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   northward axis</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that performs <code>hs.window.focusWindowSouth(window,self:getWindows(),...)</code></li><li>You'll likely want to add <code>:setCurrentSpace(true)</code> to the windowfilter used for this method call</li></ul> |

#### [focusWindowWest](#focuswindowwest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:focusWindowWest(window, frontmost, strict)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Focuses the nearest window to the west of a given window |
| **Parameters**                                       | <ul><li>window - (optional) an <code>hs.window</code> object; if nil, <code>hs.window.frontmostWindow()</code> will be used</li><li>frontmost - (optional) boolean, if true focuses the nearest window that isn't occluded by any other window in this windowfilter</li><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the westward axis</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that performs <code>hs.window.focusWindowWest(window,self:getWindows(),...)</code></li><li>You'll likely want to add <code>:setCurrentSpace(true)</code> to the windowfilter used for this method call</li></ul> |

#### [getFilters](#getfilters)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:getFilters() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Return a table with all the filtering rules defined for this windowfilter |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table containing the filtering rules of this windowfilter; you can pass this table (optionally after performing valid manipulations) to <code>hs.window.filter:setFilters()</code> and <code>hs.window.filter.new()</code></li></ul> |

#### [getWindows](#getwindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:getWindows([sortOrder]) -> list of hs.window objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the current windows allowed by this windowfilter |
| **Parameters**                                       | <ul><li>sortOrder - (optional) one of the <code>hs.window.filter.sortBy...</code> constants to determine the sort order   of the returned list; if omitted, uses the windowfilter's sort order as per <code>hs.window.filter:setSortOrder()</code>  (defaults to <code>sortByFocusedLast</code>)</li></ul> |
| **Returns**                                          | <ul><li>a list of <code>hs.window</code> objects</li></ul> |

#### [isAppAllowed](#isappallowed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:isAppAllowed(appname) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if an app is allowed by the windowfilter |
| **Parameters**                                       | <ul><li>appname - app name as per <code>hs.application:name()</code></li></ul> |
| **Returns**                                          | <ul><li><code>false</code> if the app is rejected by the windowfilter; <code>true</code> otherwise</li></ul> |

#### [isWindowAllowed](#iswindowallowed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:isWindowAllowed(window) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if a window is allowed by the windowfilter |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the window is allowed by the windowfilter, <code>false</code> otherwise; <code>nil</code> if an invalid object was passed</li></ul> |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:pause() -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops the windowfilter event subscriptions; no more event callbacks will be triggered, but the subscriptions remain intact for a subsequent call to `hs.window.filter:resume()` |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |

#### [rejectApp](#rejectapp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:rejectApp(appname) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the windowfilter to outright reject any windows belonging to a specific app |
| **Parameters**                                       | <ul><li>appname - app name as per <code>hs.application:name()</code></li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>this is just a convenience wrapper for <code>windowfilter:setAppFilter(appname,false)</code></li></ul> |

#### [resume](#resume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:resume() -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resumes the windowfilter event subscriptions |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |

#### [setAppFilter](#setappfilter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:setAppFilter(appname, filter) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the detailed filtering rules for the windows of a specific app |
| **Parameters**                                       | <ul><li>appname - app name as per <code>hs.application:name()</code></li><li>filter - if <code>false</code>, reject the app; if <code>true</code>, <code>nil</code>, or omitted, allow all visible windows (in any Space) for the app; otherwise it must be a table describing the filtering rules for the app, via the following fields:</li><li>visible - if <code>true</code>, only allow visible windows (in any Space); if <code>false</code>, reject visible windows; if omitted, this rule is ignored</li><li>currentSpace - if <code>true</code>, only allow windows in the current Mission Control Space (minimized and hidden windows are included, as they're considered to belong to all Spaces); if <code>false</code>, reject windows in the current Space (including all minimized and hidden windows); if omitted, this rule is ignored</li><li>fullscreen - if <code>true</code>, only allow fullscreen windows; if <code>false</code>, reject fullscreen windows; if omitted, this rule is ignored</li><li>hasTitlebar - if <code>true</code>, only allow windows with titlebar; if <code>false</code>, reject window with titlebar; if omitted, this rule is ignored</li><li>focused - if <code>true</code>, only allow a window while focused; if <code>false</code>, reject the focused window; if omitted, this rule is ignored</li><li>activeApplication - only allow any of this app's windows while it is (if <code>true</code>) or it's not (if <code>false</code>) the active application; if omitted, this rule is ignored</li><li>allowTitles<ul><li>if a number, only allow windows whose title is at least as many characters long; e.g. pass <code>1</code> to filter windows with an empty title</li><li>if a string or table of strings, only allow windows whose title matches (one of) the pattern(s) as per <code>string.match</code></li><li>if omitted, this rule is ignored</li></ul></li><li>rejectTitles - if a string or table of strings, reject windows whose titles matches (one of) the pattern(s) as per <code>string.match</code>; if omitted, this rule is ignored</li><li>allowRegions - an <code>hs.geometry</code> rect or constructor argument, or a list of them, designating (a) screen "region(s)" in absolute coordinates: only allow windows that "cover" at least 50% of (one of) the region(s), and/or windows that have at least 50% of their surface inside (one of) the region(s); if omitted, this rule is ignored</li><li>rejectRegions - an <code>hs.geometry</code> rect or constructor argument, or a list of them, designating (a) screen "region(s)" in absolute coordinates: reject windows that "cover" at least 50% of (one of) the region(s), and/or windows that have at least 50% of their surface inside (one of) the region(s); if omitted, this rule is ignored</li><li>allowScreens - a valid argument for <code>hs.screen.find()</code>, or a list of them, indicating one (or more) screen(s): only allow windows that (mostly) lie on (one of) the screen(s); if omitted, this rule is ignored</li><li>rejectScreens - a valid argument for <code>hs.screen.find()</code>, or a list of them, indicating one (or more) screen(s): reject windows that (mostly) lie on (one of) the screen(s); if omitted, this rule is ignored</li><li>allowRoles<ul><li>if a string or table of strings, only allow these window roles as per <code>hs.window:subrole()</code></li><li>if the special string <code>'*'</code>, this rule is ignored (i.e. all window roles, including empty ones, are allowed)</li><li>if omitted, use the default allowed roles (defined in <code>hs.window.filter.allowedWindowRoles</code>)</li></ul></li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>Passing <code>focused=true</code> in <code>filter</code> will (naturally) result in the windowfilter ever allowing 1 window at most</li><li>If you want to allow <em>all</em> windows for an app, including invisible ones, pass an empty table for <code>filter</code></li><li>Spaces-aware windowfilters might experience a (sometimes significant) delay after every Space switch, since (due to OS X limitations) they must re-query for the list of all windows in the current Space every time.</li><li>If System Preferences&gt;Mission Control&gt;Displays have separate Spaces is <em>on</em>, the <em>current Space</em> is defined as the union of all the Spaces that are currently visible</li><li>This table explains the effects of different combinations of <code>visible</code> and <code>currentSpace</code>, showing which windows will be allowed:<code>|visible=         nil                      |             true             |     false    ||currentSpace|------------------------------------------|------------------------------|--------------||     nil    |all                                       |visible in ANY space          |min and hidden||    true    |visible in CURRENT space+min and hidden   |visible in CURRENT space      |min and hidden||    false   |visible in OTHER space only+min and hidden|visible in OTHER space only   |none          |</code></li></ul> |

#### [setCurrentSpace](#setcurrentspace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:setCurrentSpace(val) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets whether the windowfilter should only allow (or reject) windows in the current Mission Control Space |
| **Parameters**                                       | <ul><li>val - boolean; if <code>true</code>, only allow windows in the current Mission Control Space, plus minimized and hidden windows;   if <code>false</code>, reject them; if <code>nil</code>, ignore Mission Control Spaces</li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>This is just a convenience wrapper for setting the <code>currentSpace</code> field in the <code>override</code> filter (other   fields will be left untouched); per-app filters will maintain their <code>currentSpace</code> field, if present, as is</li><li>Spaces-aware windowfilters might experience a (sometimes significant) delay after every Space switch, since   (due to OS X limitations) they must re-query for the list of all windows in the current Space every time.</li></ul> |

#### [setDefaultFilter](#setdefaultfilter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:setDefaultFilter(filter) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Set the default filtering rules to be used for apps without app-specific rules |
| **Parameters**                                       | <ul><li>filter - see <code>hs.window.filter:setAppFilter</code></li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |

#### [setFilters](#setfilters)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:setFilters(filters) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets multiple filtering rules |
| **Parameters**                                       | <ul><li>filters - table, every element will set an application filter; these elements must:</li><li>have a <em>key</em> of type string, denoting an application name as per <code>hs.application:name()</code></li><li>if the <em>value</em> is a boolean, the app will be allowed or rejected accordingly - see <code>hs.window.filter:allowApp()</code>     and <code>hs.window.filter:rejectApp()</code></li><li>if the <em>value</em> is a table, it must contain the accept/reject rules for the app <em>as key/value pairs</em>; valid keys     and values are described in <code>hs.window.filter:setAppFilter()</code></li><li>the key can be one of the special strings <code>"default"</code> and <code>"override"</code>, which will will set the default and override     filter respectively</li><li>the key can be the special string <code>"sortOrder"</code>; the value must be one of the <code>sortBy...</code> constants as per     <code>hs.window.filter:setSortOrder()</code></li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>every filter definition in <code>filters</code> will overwrite the pre-existing one for the relevant application, if present;   this also applies to the special default and override filters, if included</li></ul> |

#### [setOverrideFilter](#setoverridefilter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:setOverrideFilter(filter) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Set overriding filtering rules that will be applied for all apps before any app-specific rules |
| **Parameters**                                       | <ul><li>filter - see <code>hs.window.filter:setAppFilter</code></li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |

#### [setRegions](#setregions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:setRegions(regions) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the allowed screen regions for this windowfilter |
| **Parameters**                                       | <ul><li>regions - an <code>hs.geometry</code> rect or constructor argument, or a list of them, indicating the allowed region(s) for this windowfilter</li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>This is just a convenience wrapper for setting the <code>allowRegions</code> field in the <code>override</code> filter (other fields will be left untouched); per-app filters will maintain their <code>allowRegions</code> and <code>rejectRegions</code> fields, if present</li></ul> |

#### [setScreens](#setscreens)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:setScreens(screens) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the allowed screens for this windowfilter |
| **Parameters**                                       | <ul><li>regions - a valid argument for <code>hs.screen.find()</code>, or a list of them, indicating the allowed screen(s) for this windowfilter</li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>This is just a convenience wrapper for setting the <code>allowScreens</code> field in the <code>override</code> filter (other   fields will be left untouched); per-app filters will maintain their <code>allowScreens</code> and <code>rejectScreens</code> fields, if present</li></ul> |

#### [setSortOrder](#setsortorder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:setSortOrder(sortOrder) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the sort order for this windowfilter's `:getWindows()` method |
| **Parameters**                                       | <ul><li>sortOrder - one of the <code>hs.window.filter.sortBy...</code> constants</li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>The default sort order for all windowfilters (that is, until changed by this method) is <code>hs.window.filter.sortByFocusedLast</code></li></ul> |

#### [subscribe](#subscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:subscribe(event, fn[, immediate]) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Subscribe to one or more events on the allowed windows |
| **Parameters**                                       | <ul><li>event - string or list of strings, the event(s) to subscribe to (see the <code>hs.window.filter</code> constants); alternatively, this can be a map <code>{event1=fn1,event2=fn2,...}</code>: fnN will be subscribed to eventN, and the parameter <code>fn</code> will be ignored</li><li>fn - function or list of functions, the callback(s) to add for the event(s); each will be passed 3 parameters</li><li>a <code>hs.window</code> object referring to the event's window</li><li>a string containing the application name (<code>window:application():name()</code>) for convenience</li><li>a string containing the event that caused the callback, i.e. (one of) the event(s) you subscribed to</li><li>immediate - (optional) if <code>true</code>, also call all the callbacks immediately for windows that satisfy the event(s) criteria</li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>Passing lists means that <em>all</em> the <code>fn</code>s will be called when <em>any</em> of the <code>event</code>s fires, so it's <em>not</em> a shortcut for subscribing distinct callbacks to distinct events; use a map or chained <code>:subscribe</code> calls for that.</li><li>Use caution with <code>immediate</code>: if for example you're subscribing to <code>hs.window.filter.windowUnfocused</code>, <code>fn</code>(s) will be called for <em>all</em> the windows except the currently focused one.</li><li>If the windowfilter was paused with <code>hs.window.filter:pause()</code>, calling this will resume it.</li></ul> |

#### [unsubscribe](#unsubscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:unsubscribe([event][, fn]) -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes one or more event subscriptions |
| **Parameters**                                       | <ul><li>event - string or list of strings, the event(s) to unsubscribe; if omitted, <code>fn</code>(s) will be unsubscribed from all events;   alternatively, this can be a map <code>{event1=fn1,event2=fn2,...}</code>: fnN will be unsubscribed from eventN, and the parameter <code>fn</code> will be ignored</li><li>fn - function or list of functions, the callback(s) to remove; if omitted, all callbacks will be unsubscribed from <code>event</code>(s)</li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>You must pass at least one of <code>event</code> or <code>fn</code></li><li>If calling this on the default (or any other shared use) windowfilter, do not pass events, as that would remove   <em>all</em> the callbacks for the events including ones subscribed elsewhere that you might not be aware of. You should   instead keep references to your functions and pass in those.</li></ul> |

#### [unsubscribeAll](#unsubscribeall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:unsubscribeAll() -> hs.window.filter object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes all event subscriptions |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.window.filter</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>You should not use this on the default windowfilter or other shared-use windowfilters</li></ul> |

#### [windowsToEast](#windowstoeast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:windowsToEast(window, frontmost, strict) -> list of `hs.window` objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets all visible windows allowed by this windowfilter that lie to the east a given window |
| **Parameters**                                       | <ul><li>window - (optional) an <code>hs.window</code> object; if nil, <code>hs.window.frontmostWindow()</code> will be used</li><li>frontmost - (optional) boolean, if true unoccluded windows will be placed before occluded ones in the result list</li><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   eastward axis</li></ul> |
| **Returns**                                          | <ul><li>A list of <code>hs.window</code> objects representing all windows positioned east (i.e. right) of the window, in ascending order of distance</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that returns <code>hs.window.windowsToEast(window,self:getWindows(),...)</code></li><li>You'll likely want to add <code>:setCurrentSpace(true)</code> to the windowfilter used for this method call (or just use   <code>hs.window.filter.defaultCurrentSpace</code>)</li></ul> |

#### [windowsToNorth](#windowstonorth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:windowsToNorth(window, frontmost, strict) -> list of `hs.window` objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets all visible windows allowed by this windowfilter that lie to the north a given window |
| **Parameters**                                       | <ul><li>window - (optional) an <code>hs.window</code> object; if nil, <code>hs.window.frontmostWindow()</code> will be used</li><li>frontmost - (optional) boolean, if true unoccluded windows will be placed before occluded ones in the result list</li><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   northward axis</li></ul> |
| **Returns**                                          | <ul><li>A list of <code>hs.window</code> objects representing all windows positioned north (i.e. up) of the window, in ascending order of distance</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that returns <code>hs.window.windowsToNorth(window,self:getWindows(),...)</code></li><li>You'll likely want to add <code>:setCurrentSpace(true)</code> to the windowfilter used for this method call (or just use   <code>hs.window.filter.defaultCurrentSpace</code>)</li></ul> |

#### [windowsToSouth](#windowstosouth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:windowsToSouth(window, frontmost, strict) -> list of `hs.window` objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets all visible windows allowed by this windowfilter that lie to the south a given window |
| **Parameters**                                       | <ul><li>window - (optional) an <code>hs.window</code> object; if nil, <code>hs.window.frontmostWindow()</code> will be used</li><li>frontmost - (optional) boolean, if true unoccluded windows will be placed before occluded ones in the result list</li><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the   southward axis</li></ul> |
| **Returns**                                          | <ul><li>A list of <code>hs.window</code> objects representing all windows positioned south (i.e. down) of the window, in ascending order of distance</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that returns <code>hs.window.windowsToSouth(window,self:getWindows(),...)</code></li><li>You'll likely want to add <code>:setCurrentSpace(true)</code> to the windowfilter used for this method call (or just use   <code>hs.window.filter.defaultCurrentSpace</code>)</li></ul> |

#### [windowsToWest](#windowstowest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.window.filter:windowsToWest(window, frontmost, strict) -> list of `hs.window` objects` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets all visible windows allowed by this windowfilter that lie to the west a given window |
| **Parameters**                                       | <ul><li>window - (optional) an <code>hs.window</code> object; if nil, <code>hs.window.frontmostWindow()</code> will be used</li><li>frontmost - (optional) boolean, if true unoccluded windows will be placed before occluded ones in the result list</li><li>strict - (optional) boolean, if true only consider windows at an angle between 45° and -45° on the westward axis</li></ul> |
| **Returns**                                          | <ul><li>A list of <code>hs.window</code> objects representing all windows positioned west (i.e. left) of the window, in ascending order of distance</li></ul> |
| **Notes**                                            | <ul><li>This is a convenience wrapper that returns <code>hs.window.windowsToWest(window,self:getWindows(),...)</code></li><li>You'll likely want to add <code>:setCurrentSpace(true)</code> to the windowfilter used for this method call (or just use <code>hs.window.filter.defaultCurrentSpace</code>)</li></ul> |

