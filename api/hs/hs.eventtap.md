# [docs](index.md) » hs.eventtap
---

Tap into input events (mouse, keyboard, trackpad) for observation and possibly overriding them
It also provides convenience wrappers for sending mouse and keyboard events. If you need to construct finely controlled mouse/keyboard events, see hs.eventtap.event

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## Submodules
 * [hs.eventtap.event](hs.eventtap.event.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [checkKeyboardModifiers](#checkkeyboardmodifiers)
 * [checkMouseButtons](#checkmousebuttons)
 * [doubleClickInterval](#doubleclickinterval)
 * [isSecureInputEnabled](#issecureinputenabled)
 * [keyRepeatDelay](#keyrepeatdelay)
 * [keyRepeatInterval](#keyrepeatinterval)
 * [keyStroke](#keystroke)
 * [keyStrokes](#keystrokes)
 * [leftClick](#leftclick)
 * [middleClick](#middleclick)
 * [otherClick](#otherclick)
 * [rightClick](#rightclick)
 * [scrollWheel](#scrollwheel)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [isEnabled](#isenabled)
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Functions

#### [checkKeyboardModifiers](#checkkeyboardmodifiers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.checkKeyboardModifiers([raw]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the current key modifiers being pressed or in effect *at this instant* for the keyboard most recently used. |
| **Parameters**                                       | <ul><li>raw - an optional boolean value which, if true, includes the _raw key containing the numeric representation of all of the keyboard/modifier flags.</li></ul> |
| **Returns**                                          | <ul><li>Returns a table containing boolean values indicating which keyboard modifiers were held down when the function was invoked; The possible keys are:<ul><li>cmd (or ⌘)</li><li>alt (or ⌥)</li><li>shift (or ⇧)</li><li>ctrl (or ⌃)</li><li>capslock</li><li>fn  and optionally</li><li>_raw - a numeric representation of the numeric representation of all of the keyboard/modifier flags.</li></ul></li></ul> |
| **Notes**                                            | <ul><li>This is an instantaneous poll of the current keyboard modifiers for the most recently used keyboard, not a callback.  This is useful primarily in conjuction with other modules, such as <code>hs.menubar</code>, when a callback is already in progress or waiting for an event callback is not practical or possible.</li><li>the numeric value returned is useful if you need to detect device dependent flags or flags which we normally ignore because they are not present (or are accessible another way) on most keyboards.</li></ul> |

#### [checkMouseButtons](#checkmousebuttons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.checkMouseButtons() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the current mouse buttons being pressed *at this instant*. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns an array containing indicies starting from 1 up to the highest numbered button currently being pressed where the index is <code>true</code> if the button is currently pressed or <code>false</code> if it is not.</li><li>Special hash tag synonyms for <code>left</code> (button 1), <code>right</code> (button 2), and <code>middle</code> (button 3) are also set to true if these buttons are currently being pressed.</li></ul> |
| **Notes**                                            | <ul><li>This is an instantaneous poll of the current mouse buttons, not a callback.  This is useful primarily in conjuction with other modules, such as <code>hs.menubar</code>, when a callback is already in progress or waiting for an event callback is not practical or possible.</li></ul> |

#### [doubleClickInterval](#doubleclickinterval)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.doubleClickInterval() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the system-wide setting for the delay between two clicks, to register a double click event |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number containing the maximum number of seconds between two mouse click events, for a double click event to be registered</li></ul> |

#### [isSecureInputEnabled](#issecureinputenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.isSecureInputEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if macOS is preventing keyboard events from being sent to event taps |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if secure input is enabled, otherwise false</li></ul> |
| **Notes**                                            | <ul><li>If secure input is enabled, Hammerspoon is not able to intercept keyboard events</li><li>Secure input is enabled generally only in situations where an password field is focused in a web browser, system dialog or terminal</li></ul> |

#### [keyRepeatDelay](#keyrepeatdelay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.keyRepeatDelay() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the system-wide setting for the delay before keyboard repeat events begin |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number containing the number of seconds before repeat events begin, after a key is held down</li></ul> |

#### [keyRepeatInterval](#keyrepeatinterval)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.keyRepeatInterval() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the system-wide setting for the interval between repeated keyboard events |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number containing the number of seconds between keyboard events, if a key is held down</li></ul> |

#### [keyStroke](#keystroke)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.keyStroke(modifiers, character[, delay, application])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates and emits a single keystroke event pair for the supplied keyboard modifiers and character |
| **Parameters**                                       | <ul><li>modifiers - A table containing the keyboard modifiers to apply ("fn", "ctrl", "alt", "cmd", "shift", or their Unicode equivalents)</li><li>character - A string containing a character to be emitted</li><li>delay - An optional delay (in microseconds) between key down and up event. Defaults to 200000 (i.e. 200ms)</li><li>application - An optional hs.application object to send the keystroke to</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This function is ideal for sending single keystrokes with a modifier applied (e.g. sending ⌘-v to paste, with <code>hs.eventtap.keyStroke({"cmd"}, "v")</code>). If you want to emit multiple keystrokes for typing strings of text, see <code>hs.eventtap.keyStrokes()</code></li></ul> |

#### [keyStrokes](#keystrokes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.keyStrokes(text[, application])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates and emits keystroke events for the supplied text |
| **Parameters**                                       | <ul><li>text - A string containing the text to be typed</li><li>application - An optional hs.application object to send the keystrokes to</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>If you want to send a single keystroke with keyboard modifiers (e.g. sending ⌘-v to paste), see <code>hs.eventtap.keyStroke()</code></li></ul> |

#### [leftClick](#leftclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.leftClick(point[, delay])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a left mouse click event at the specified point |
| **Parameters**                                       | <ul><li>point - A table with keys <code>{x, y}</code> indicating the location where the mouse event should occur</li><li>delay - An optional delay (in microseconds) between mouse down and up event. Defaults to 200000 (i.e. 200ms)</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a wrapper around <code>hs.eventtap.event.newMouseEvent</code> that sends <code>leftmousedown</code> and <code>leftmouseup</code> events)</li></ul> |

#### [middleClick](#middleclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.middleClick(point[, delay])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a middle mouse click event at the specified point |
| **Parameters**                                       | <ul><li>point  - A table with keys <code>{x, y}</code> indicating the location where the mouse event should occur</li><li>delay  - An optional delay (in microseconds) between mouse down and up event. Defaults to 200000 (i.e. 200ms)</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This function is just a wrapper which calls <code>hs.eventtap.otherClick(point, delay, 2)</code> and is included solely for backwards compatibility.</li></ul> |

#### [otherClick](#otherclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.otherClick(point[, delay][, button])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates an "other" mouse click event at the specified point |
| **Parameters**                                       | <ul><li>point  - A table with keys <code>{x, y}</code> indicating the location where the mouse event should occur</li><li>delay  - An optional delay (in microseconds) between mouse down and up event. Defaults to 200000 (i.e. 200ms)</li><li>button - An optional integer, default 2, between 2 and 31 specifying the button number to be pressed.  If this parameter is specified then <code>delay</code> must also be specified, though you may specify it as <code>nil</code> to use the default.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a wrapper around <code>hs.eventtap.event.newMouseEvent</code> that sends <code>otherMouseDown</code> and <code>otherMouseUp</code> events)</li></ul> |

#### [rightClick](#rightclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.rightClick(point[, delay])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a right mouse click event at the specified point |
| **Parameters**                                       | <ul><li>point - A table with keys <code>{x, y}</code> indicating the location where the mouse event should occur</li><li>delay - An optional delay (in microseconds) between mouse down and up event. Defaults to 200000 (i.e. 200ms)</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This is a wrapper around <code>hs.eventtap.event.newMouseEvent</code> that sends <code>rightmousedown</code> and <code>rightmouseup</code> events)</li></ul> |

#### [scrollWheel](#scrollwheel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.scrollWheel(offsets, modifiers, unit) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates and emits a scroll wheel event |
| **Parameters**                                       | <ul><li>offsets - A table containing the {horizontal, vertical} amount to scroll. Positive values scroll up or left, negative values scroll down or right.</li><li>mods - A table containing zero or more of the following:</li><li>cmd</li><li>alt</li><li>shift</li><li>ctrl</li><li>fn</li><li>unit - An optional string containing the name of the unit for scrolling. Either "line" (the default) or "pixel"</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.new(types, fn) -> eventtap` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Create a new event tap object |
| **Parameters**                                       | <ul><li>types - A table that should contain values from <code>hs.eventtap.event.types</code></li><li>fn - A function that will be called when the specified event types occur. The function should take a single parameter, which will be an event object. It can optionally return two values. Firstly, a boolean, true if the event should be deleted, false if it should propagate to any other applications watching for that event. Secondly, a table of events to post.</li></ul> |
| **Returns**                                          | <ul><li>An event tap object</li></ul> |
| **Notes**                                            | <ul><li>If you specify the argument <code>types</code> as the special table {"all"[, events to ignore]}, then <em>all</em> events (except those you optionally list <em>after</em> the "all" string) will trigger a callback, even events which are not defined in the <a href="https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/Reference/reference.html">Quartz Event Reference</a>.</li></ul> |

### Methods

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap:isEnabled() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Determine whether or not an event tap object is enabled. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if the event tap is enabled or false if it is not.</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Starts an event tap |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The event tap object</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops an event tap |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The event tap object</li></ul> |

