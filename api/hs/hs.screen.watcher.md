# [docs](index.md) » hs.screen.watcher
---

Watch for screen layout changes
This could be the addition or removal of a monitor, a screen resolution change, movement of a monitor in the Display preferences pane, etc.

Note that screen events which happen while your Mac is suspended, may not trigger the watcher in various circumstances (e.g. if you have FileVault enabled and the machine resumes out of hibernation - the screen events will be happening before the drive is unlocked and will not be reported to Hammerspoon)

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [newWithActiveScreen](#newwithactivescreen)
* Methods - API calls which can only be made on an object returned by a constructor
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.watcher.new(fn) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new screen-watcher.                                                                                         |
| **Parameters**                                       | <ul><br /><li>The function to be called when a change in the screen layout occurs.  This function should take no arguments.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen.watcher</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>A screen layout change usually involves a change that is made from the Displays Preferences Panel or when a monitor is attached or removed.</li><br /></ul>                                             |

#### [newWithActiveScreen](#newwithactivescreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.watcher.newWithActiveScreen(fn) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new screen-watcher that is also called when the active screen changes.                                                                                         |
| **Parameters**                                       | <ul><br /><li>The function to be called when a change in the screen layout or active screen occurs.  This function can optionally take one argument, a boolean which will indicate if the change was due to a screen layout change (nil) or because the active screen changed (true).</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen.watcher</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>A screen layout change usually involves a change that is made from the Displays Preferences Panel or when a monitor is attached or removed.   * <code>nil</code> was chosen instead of <code>falase</code> for the argument type when this type of change occurs to more closely match the previous behavior of having no argument passed to the callback function. * An active screen change indicates that the focused or main screen has changed when the user has "Displays have separate spaces" checked in the Mission Control Preferences Panel (the focused display is the display which has the active window and active menubar).   * Detecting a change in the active display relies on watching for the <code>NSWorkspaceActiveDisplayDidChangeNotification</code> message which is not documented by Apple.  While this message has been around at least since OS X 10.9, because it is undocumented, we cannot be positive that Apple won't remove it in a future OS X update.  Because this watcher works by listening for posted messages, should Apple remove this notification, your callback function will no longer receive messages about this change -- it won't crash or change behavior in any other way.  This documentation will be updated if this status changes.</li><br /></ul>                                             |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.watcher:start() -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the screen watcher, making it so fn is called each time the screen arrangement changes                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.screen.watcher</code> object</li><br /></ul>                                           |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.watcher:stop() -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the screen watcher's fn from getting called until started again                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.screen.watcher</code> object</li><br /></ul>                                           |

