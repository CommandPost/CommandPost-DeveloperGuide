# [docs](index.md) » hs.eventtap.event
---

Create, modify and inspect events for `hs.eventtap`

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constants - Useful values which cannot be changed
 * [properties](#properties)
 * [types](#types)
* Constructors - API calls which return an object, typically one that offers API methods
 * [copy](#copy)
 * [newKeyEvent](#newkeyevent)
 * [newMouseEvent](#newmouseevent)
 * [newScrollEvent](#newscrollevent)
 * [newSystemKeyEvent](#newsystemkeyevent)
* Methods - API calls which can only be made on an object returned by a constructor
 * [getButtonState](#getbuttonstate)
 * [getCharacters](#getcharacters)
 * [getFlags](#getflags)
 * [getKeyCode](#getkeycode)
 * [getProperty](#getproperty)
 * [getRawEventData](#getraweventdata)
 * [getType](#gettype)
 * [post](#post)
 * [setFlags](#setflags)
 * [setKeyCode](#setkeycode)
 * [setProperty](#setproperty)
 * [systemKey](#systemkey)

## API Documentation

### Constants

#### [properties](#properties)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.properties -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing property types for use with `hs.eventtap.event:getProperty()` and `hs.eventtap.event:setProperty()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility.                                                                                         |
| **Notes**                                            | <ul><li>This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.eventtap.event.properties`.</li><li>In previous versions of Hammerspoon, property labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format.</li></ul>                |

#### [types](#types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.types -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing event types to be used with `hs.eventtap.new(...)` and returned by `hs.eventtap.event:type()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility.                                                                                         |
| **Notes**                                            | <ul><li>This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.eventtap.event.types`.</li><li>In previous versions of Hammerspoon, type labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format.</li></ul>                |

### Constructors

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:copy() -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Duplicates an `hs.eventtap.event` event for further modification or injection                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A new `hs.eventtap.event` object</li></ul>          |

#### [newKeyEvent](#newkeyevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newKeyEvent(mods, key, isdown) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a keyboard event                                                                                         |
| **Parameters**                                       | <ul><li>mods - A table containing zero or more of the following:</li><li> cmd</li><li> alt</li><li> shift</li><li> ctrl</li><li> fn</li><li>key - A string containing the name of a key (see `hs.hotkey` for more information)</li><li>isdown - A boolean, true if the event should be a key-down, false if it should be a key-up</li></ul> |
| **Returns**                                          | <ul><li>An `hs.eventtap.event` object</li></ul>          |

#### [newMouseEvent](#newmouseevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newMouseEvent(eventtype, point[, modifiers) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new mouse event                                                                                         |
| **Parameters**                                       | <ul><li>eventtype - One of the values from `hs.eventtap.event.types`</li><li>point - An hs.geometry point table (i.e. of the form `{x=123, y=456}`) indicating the location where the mouse event should occur</li><li>modifiers - An optional table containing zero or more of the following keys:</li><li> cmd</li><li> alt</li><li> shift</li><li> ctrl</li><li> fn</li></ul> |
| **Returns**                                          | <ul><li>An `hs.eventtap` object</li></ul>          |

#### [newScrollEvent](#newscrollevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newScrollEvent(offsets, mods, unit) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a scroll wheel event                                                                                         |
| **Parameters**                                       | <ul><li>offsets - A table containing the {horizontal, vertical} amount to scroll. Positive values scroll up or left, negative values scroll down or right.</li><li>mods - A table containing zero or more of the following:</li><li> cmd</li><li> alt</li><li> shift</li><li> ctrl</li><li> fn</li><li>unit - An optional string containing the name of the unit for scrolling. Either "line" (the default) or "pixel"</li></ul> |
| **Returns**                                          | <ul><li>An `hs.eventtap.event` object</li></ul>          |

#### [newSystemKeyEvent](#newsystemkeyevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newSystemKeyEvent(key, isdown) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a keyboard event for special keys (e.g. media playback)                                                                                         |
| **Parameters**                                       | <ul><li>key - A string containing the name of a special key. The possible names are:</li><li> SOUND_UP</li><li> SOUND_DOWN</li><li> MUTE</li><li> BRIGHTNESS_UP</li><li> BRIGHTNESS_DOWN</li><li> CONTRAST_UP</li><li> CONTRAST_DOWN</li><li> POWER</li><li> LAUNCH_PANEL</li><li> VIDMIRROR</li><li> PLAY</li><li> EJECT</li><li> NEXT</li><li> PREVIOUS</li><li> FAST</li><li> REWIND</li><li> ILLUMINATION_UP</li><li> ILLUMINATION_DOWN</li><li> ILLUMINATION_TOGGLE</li><li> CAPS_LOCK</li><li> HELP</li><li> NUM_LOCK</li><li>isdown - A boolean, true if the event should be a key-down, false if it should be a key-up</li></ul> |
| **Returns**                                          | <ul><li>An `hs.eventtap.event` object</li></ul>          |
| **Notes**                                            | <ul><li>To set modifiers on a system key event (e.g. cmd/ctrl/etc), see the `hs.eventtap.event:setFlags()` method</li><li>The event names are case sensitive</li></ul>                |

### Methods

#### [getButtonState](#getbuttonstate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getButtonState(button) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the state of a mouse button in the event                                                                                         |
| **Parameters**                                       | <ul><li>button - A number between 0 and 31. The left mouse button is 0, the right mouse button is 1 and the middle mouse button is 2. The meaning of the remaining buttons varies by hardware, and their functionality varies by application (typically they are not present on a mouse and have no effect in an application)</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the specified mouse button is to be clicked by the event</li></ul>          |
| **Notes**                                            | <ul><li>This method should only be called on mouse events</li></ul>                |

#### [getCharacters](#getcharacters)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getCharacters([clean]) -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Unicode character, if any, represented by a keyDown or keyUp event.                                                                                         |
| **Parameters**                                       | <ul><li>clean -- an optional parameter, default `false`, which indicates if key modifiers, other than Shift, should be stripped from the keypress before converting to Unicode.</li></ul> |
| **Returns**                                          | <ul><li>A string containing the Unicode character represented by the keyDown or keyUp event, or nil if the event is not a keyUp or keyDown.</li></ul>          |
| **Notes**                                            | <ul><li>This method should only be used on keyboard events</li><li>If `clean` is true, all modifiers except for Shift are stripped from the character before converting to the Unicode character represented by the keypress.</li><li>If the keypress does not correspond to a valid Unicode character, an empty string is returned (e.g. if `clean` is false, then Opt-E will return an empty string, while Opt-Shift-E will return an accent mark).</li></ul>                |

#### [getFlags](#getflags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getFlags() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the keyboard modifiers of an event                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the keyboard modifiers that present in the event - i.e. zero or more of the following keys, each with a value of `true`:</li><li> cmd</li><li> alt</li><li> shift</li><li> ctrl</li><li> fn</li><li>The table responds to the following methods:</li><li> contain(mods) -> boolean</li><li>  Returns true if the modifiers contain all of given modifiers</li><li> containExactly(mods) -> boolean</li><li>  Returns true if the modifiers contain all of given modifiers exactly and nothing else</li><li>Parameter mods is a table containing zero or more of the following:</li><li> cmd or ⌘</li><li> alt or ⌥</li><li> shift or ⇧</li><li> ctrl or ⌃</li><li> fn</li></ul>          |

#### [getKeyCode](#getkeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getKeyCode() -> keycode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the raw keycode for the event                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number containing the raw keycode, taken from `hs.keycodes.map`</li></ul>          |
| **Notes**                                            | <ul><li>This method should only be used on keyboard events</li></ul>                |

#### [getProperty](#getproperty)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getProperty(prop) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a property of the event                                                                                         |
| **Parameters**                                       | <ul><li>prop - A value taken from `hs.eventtap.event.properties`</li></ul> |
| **Returns**                                          | <ul><li>A number containing the value of the requested property</li></ul>          |
| **Notes**                                            | <ul><li>The properties are `CGEventField` values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField</li></ul>                |

#### [getRawEventData](#getraweventdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getRawEventData() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns raw data about the event                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table with two keys:</li><li>  CGEventData -- a table with keys containing CGEvent data about the event.</li><li>  NSEventData -- a table with keys containing NSEvent data about the event.</li></ul>          |
| **Notes**                                            | <ul><li>Most of the data in `CGEventData` is already available through other methods, but is presented here without any cleanup or parsing.</li><li>This method is expected to be used mostly for testing and expanding the range of possibilities available with the hs.eventtap module.  If you find that you are regularly using specific data from this method for common or re-usable purposes, consider submitting a request for adding a more targeted method to hs.eventtap or hs.eventtap.event -- it will likely be more efficient and faster for common tasks, something eventtaps need to be to minimize affecting system responsiveness.</li></ul>                |

#### [getType](#gettype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getType() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the type of the event                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number containing the type of the event, taken from `hs.eventtap.event.types`</li></ul>          |

#### [post](#post)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:post([app])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Posts the event to the OS - i.e. emits the keyboard/mouse input defined by the event                                                                                         |
| **Parameters**                                       | <ul><li>app - An optional `hs.application` object. If specified, the event will only be sent to that application</li></ul> |
| **Returns**                                          | <ul><li>The `hs.eventtap.event` object</li></ul>          |

#### [setFlags](#setflags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setFlags(table)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the keyboard modifiers of an event                                                                                         |
| **Parameters**                                       | <ul><li>A table containing the keyboard modifiers to be sent with the event - i.e. zero or more of the following keys, each with a value of `true`:</li><li> cmd</li><li> alt</li><li> shift</li><li> ctrl</li><li> fn</li></ul> |
| **Returns**                                          | <ul><li>The `hs.eventap.event` object.</li></ul>          |

#### [setKeyCode](#setkeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setKeyCode(keycode)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the raw keycode for the event                                                                                         |
| **Parameters**                                       | <ul><li>keycode - A number containing a raw keycode, taken from `hs.keycodes.map`</li></ul> |
| **Returns**                                          | <ul><li>The `hs.eventtap.event` object</li></ul>          |
| **Notes**                                            | <ul><li>This method should only be used on keyboard events</li></ul>                |

#### [setProperty](#setproperty)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setProperty(prop, value)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets a property of the event                                                                                         |
| **Parameters**                                       | <ul><li>prop - A value from `hs.eventtap.event.properties`</li><li>value - A number containing the value of the specified property</li></ul> |
| **Returns**                                          | <ul><li>The `hs.eventtap.event` object.</li></ul>          |
| **Notes**                                            | <ul><li>The properties are `CGEventField` values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField</li></ul>                |

#### [systemKey](#systemkey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:systemKey() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the special key and its state if the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS (special-key pressed)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>If the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, a table with the following keys defined:</li><li>  key    -- a string containing one of the following labels indicating the key involved:</li><li>    SOUND_UP</li><li>    SOUND_DOWN</li><li>    MUTE</li><li>    BRIGHTNESS_UP</li><li>    BRIGHTNESS_DOWN</li><li>    CONTRAST_UP</li><li>    CONTRAST_DOWN</li><li>    POWER</li><li>    LAUNCH_PANEL</li><li>    VIDMIRROR</li><li>    PLAY</li><li>    EJECT</li><li>    NEXT</li><li>    PREVIOUS</li><li>    FAST</li><li>    REWIND</li><li>    ILLUMINATION_UP</li><li>    ILLUMINATION_DOWN</li><li>    ILLUMINATION_TOGGLE</li><li>    CAPS_LOCK</li><li>    HELP</li><li>    NUM_LOCK</li><li>     or "undefined" if the key detected is unrecognized.</li><li>  keyCode -- the numeric keyCode corresponding to the key specified in `key`.</li><li>  down   -- a boolean value indicating if the key is pressed down (true) or just released (false)</li><li>  repeat -- a boolean indicating if this event is because the keydown is repeating.  This will always be false for a key release.</li><li>If the event does not correspond to a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, then an empty table is returned.</li></ul>          |
| **Notes**                                            | <ul><li>* CAPS_LOCK seems to sometimes generate 0 or 2 key release events (down == false), especially on builtin laptop keyboards, so it is probably safest (more reliable) to look for cases where down == true only.</li><li>* If the key field contains "undefined", you can use the number in keyCode to look it up in `/System/Library/Frameworks/IOKit.framework/Headers/hidsystem/ev_keymap.h`.  If you believe the numeric value is part of a new system update or was otherwise mistakenly left out, please submit the label (it will defined in the header file as `NX_KEYTYPE_something`) and number to the Hammerspoon maintainers at https://github.com/Hammerspoon/hammerspoon with a request for inclusion in the next Hammerspoon update.</li></ul>                |

