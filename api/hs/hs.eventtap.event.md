# [docs](index.md) » hs.eventtap.event
---

Create, modify and inspect events for `hs.eventtap`

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constants - Useful values which cannot be changed
 * [properties](#properties)
 * [rawFlagMasks](#rawflagmasks)
 * [types](#types)
* Functions - API calls offered directly by the extension
 * [newKeyEventSequence](#newkeyeventsequence)
* Constructors - API calls which return an object, typically one that offers API methods
 * [copy](#copy)
 * [newEvent](#newevent)
 * [newEventFromData](#neweventfromdata)
 * [newKeyEvent](#newkeyevent)
 * [newMouseEvent](#newmouseevent)
 * [newScrollEvent](#newscrollevent)
 * [newSystemKeyEvent](#newsystemkeyevent)
* Methods - API calls which can only be made on an object returned by a constructor
 * [asData](#asdata)
 * [getButtonState](#getbuttonstate)
 * [getCharacters](#getcharacters)
 * [getFlags](#getflags)
 * [getKeyCode](#getkeycode)
 * [getProperty](#getproperty)
 * [getRawEventData](#getraweventdata)
 * [getType](#gettype)
 * [getUnicodeString](#getunicodestring)
 * [location](#location)
 * [post](#post)
 * [rawFlags](#rawflags)
 * [setFlags](#setflags)
 * [setKeyCode](#setkeycode)
 * [setProperty](#setproperty)
 * [setType](#settype)
 * [setUnicodeString](#setunicodestring)
 * [systemKey](#systemkey)
 * [timestamp](#timestamp)

## API Documentation

### Constants

#### [properties](#properties)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.properties -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table containing property types for use with `hs.eventtap.event:getProperty()` and `hs.eventtap.event:setProperty()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility. |
| **Notes**                                            | <ul><li>This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing <code>hs.eventtap.event.properties</code>.</li><li>In previous versions of Hammerspoon, property labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format.</li></ul> |

#### [rawFlagMasks](#rawflagmasks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.rawFlagMasks[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table containing key-value pairs describing the raw modifier flags which can be manipulated with [hs.eventtap.event:rawFlags](#rawFlags). |

#### [types](#types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.types -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table containing event types to be used with `hs.eventtap.new(...)` and returned by `hs.eventtap.event:type()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility. |
| **Notes**                                            | <ul><li>This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing <code>hs.eventtap.event.types</code>.</li><li>In previous versions of Hammerspoon, type labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format.</li></ul> |

### Functions

#### [newKeyEventSequence](#newkeyeventsequence)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newKeyEventSequence(modifiers, character) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a table containing the keydown and keyup events to generate the keystroke with the specified modifiers. |
| **Parameters**                                       | <ul><li>modifiers - A table containing the keyboard modifiers to apply ("cmd", "alt", "shift", "ctrl", "rightCmd", "rightAlt", "rightShift", "rightCtrl", or "fn")</li><li>character - A string containing a character to be emitted</li></ul> |
| **Returns**                                          | <ul><li>a table with events which contains the individual events that Apple recommends for building up a keystroke combination (see <a href="#newKeyEvents">hs.eventtap.event.newKeyEvent</a>) in the order that they should be posted (i.e. the first half will contain keyDown events and the second half will contain keyUp events)</li></ul> |
| **Notes**                                            | <ul><li>The <code>modifiers</code> table must contain the full name of the modifiers you wish used for the keystroke as defined in <code>hs.keycodes.map</code> -- the Unicode equivalents are not supported by this function.</li><li>The returned table will always contain an even number of events -- the first half will be the keyDown events and the second half will be the keyUp events.</li><li>The events have not been posted; the table can be used without change as the return value for a callback to a watcher defined with <a href="#new">hs.eventtap.new</a>.</li></ul> |

### Constructors

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:copy() -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Duplicates an `hs.eventtap.event` event for further modification or injection |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A new <code>hs.eventtap.event</code> object</li></ul> |

#### [newEvent](#newevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newEvent() -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a blank event.  You will need to set its type with [hs.eventtap.event:setType](#setType) |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a new <code>hs.eventtap.event</code> object</li></ul> |
| **Notes**                                            | <ul><li>this is an empty event that you should set a type for and whatever other properties may be appropriate before posting.</li></ul> |

#### [newEventFromData](#neweventfromdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newEventFromData(data) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an event from the data encoded in the string provided. |
| **Parameters**                                       | <ul><li>data - a string containing binary data provided by <a href="#asData">hs.eventtap.event:asData</a> representing an event.</li></ul> |
| **Returns**                                          | <ul><li>a new <code>hs.eventtap.event</code> object or nil if the string did not represent a valid event</li></ul> |

#### [newKeyEvent](#newkeyevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newKeyEvent([mods], key, isdown) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a keyboard event |
| **Parameters**                                       | <ul><li>mods - An optional table containing zero or more of the following:</li><li>cmd</li><li>alt</li><li>shift</li><li>ctrl</li><li>fn</li><li>key - A string containing the name of a key (see <code>hs.hotkey</code> for more information) or an integer specifying the virtual keycode for the key.</li><li>isdown - A boolean, true if the event should be a key-down, false if it should be a key-up</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.eventtap.event</code> object</li></ul> |
| **Notes**                                            | <ul><li>The original version of this constructor utilized a shortcut which merged <code>flagsChanged</code> and <code>keyUp</code>/<code>keyDown</code> events into one.  This approach is still supported for backwards compatibility and because it <em>does</em> work in most cases.</li><li>According to Apple Documentation, the proper way to perform a keypress with modifiers is through multiple key events; for example to generate 'Å', you should do the following:~~~lua    hs.eventtap.event.newKeyEvent(hs.keycodes.map.shift, true):post()    hs.eventtap.event.newKeyEvent(hs.keycodes.map.alt, true):post()    hs.eventtap.event.newKeyEvent("a", true):post()    hs.eventtap.event.newKeyEvent("a", false):post()    hs.eventtap.event.newKeyEvent(hs.keycodes.map.alt, false):post()    hs.eventtap.event.newKeyEvent(hs.keycodes.map.shift, false):post()~~~</li><li>The shortcut method is still supported, though if you run into odd behavior or need to generate <code>flagsChanged</code> events without a corresponding <code>keyUp</code> or <code>keyDown</code>, please check out the syntax demonstrated above.~~~lua    hs.eventtap.event.newKeyEvent({"shift", "alt"}, "a", true):post()    hs.eventtap.event.newKeyEvent({"shift", "alt"}, "a", false):post()~~~</li></ul> |

#### [newMouseEvent](#newmouseevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newMouseEvent(eventtype, point[, modifiers) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new mouse event |
| **Parameters**                                       | <ul><li>eventtype - One of the mouse related values from <code>hs.eventtap.event.types</code></li><li>point - An hs.geometry point table (i.e. of the form <code>{x=123, y=456}</code>) indicating the location where the mouse event should occur</li><li>modifiers - An optional table (e.g. {"cmd", "alt"}) containing zero or more of the following keys:</li><li>cmd</li><li>alt</li><li>shift</li><li>ctrl</li><li>fn</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.eventtap</code> object</li></ul> |

#### [newScrollEvent](#newscrollevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newScrollEvent(offsets, mods, unit) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a scroll wheel event |
| **Parameters**                                       | <ul><li>offsets - A table containing the {horizontal, vertical} amount to scroll. Positive values scroll up or left, negative values scroll down or right.</li><li>mods - A table containing zero or more of the following:</li><li>cmd</li><li>alt</li><li>shift</li><li>ctrl</li><li>fn</li><li>unit - An optional string containing the name of the unit for scrolling. Either "line" (the default) or "pixel"</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.eventtap.event</code> object</li></ul> |

#### [newSystemKeyEvent](#newsystemkeyevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newSystemKeyEvent(key, isdown) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a keyboard event for special keys (e.g. media playback) |
| **Parameters**                                       | <ul><li>key - A string containing the name of a special key. The possible names are:</li><li>SOUND_UP</li><li>SOUND_DOWN</li><li>MUTE</li><li>BRIGHTNESS_UP</li><li>BRIGHTNESS_DOWN</li><li>CONTRAST_UP</li><li>CONTRAST_DOWN</li><li>POWER</li><li>LAUNCH_PANEL</li><li>VIDMIRROR</li><li>PLAY</li><li>EJECT</li><li>NEXT</li><li>PREVIOUS</li><li>FAST</li><li>REWIND</li><li>ILLUMINATION_UP</li><li>ILLUMINATION_DOWN</li><li>ILLUMINATION_TOGGLE</li><li>CAPS_LOCK</li><li>HELP</li><li>NUM_LOCK</li><li>isdown - A boolean, true if the event should be a key-down, false if it should be a key-up</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.eventtap.event</code> object</li></ul> |
| **Notes**                                            | <ul><li>To set modifiers on a system key event (e.g. cmd/ctrl/etc), see the <code>hs.eventtap.event:setFlags()</code> method</li><li>The event names are case sensitive</li></ul> |

### Methods

#### [asData](#asdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:asData() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a string containing binary data representing the event.  This can be used to record events for later use. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string representing the event or nil if the event cannot be represented as a string</li></ul> |
| **Notes**                                            | <ul><li>You can recreate the event for later posting with <a href="#newEventFromData">hs.eventtap.event.newnEventFromData</a></li></ul> |

#### [getButtonState](#getbuttonstate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getButtonState(button) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the state of a mouse button in the event |
| **Parameters**                                       | <ul><li>button - A number between 0 and 31. The left mouse button is 0, the right mouse button is 1 and the middle mouse button is 2. The meaning of the remaining buttons varies by hardware, and their functionality varies by application (typically they are not present on a mouse and have no effect in an application)</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the specified mouse button is to be clicked by the event</li></ul> |
| **Notes**                                            | <ul><li>This method should only be called on mouse events</li></ul> |

#### [getCharacters](#getcharacters)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getCharacters([clean]) -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Unicode character, if any, represented by a keyDown or keyUp event. |
| **Parameters**                                       | <ul><li>clean -- an optional parameter, default <code>false</code>, which indicates if key modifiers, other than Shift, should be stripped from the keypress before converting to Unicode.</li></ul> |
| **Returns**                                          | <ul><li>A string containing the Unicode character represented by the keyDown or keyUp event, or nil if the event is not a keyUp or keyDown.</li></ul> |
| **Notes**                                            | <ul><li>This method should only be used on keyboard events</li><li>If <code>clean</code> is true, all modifiers except for Shift are stripped from the character before converting to the Unicode character represented by the keypress.</li><li>If the keypress does not correspond to a valid Unicode character, an empty string is returned (e.g. if <code>clean</code> is false, then Opt-E will return an empty string, while Opt-Shift-E will return an accent mark).</li></ul> |

#### [getFlags](#getflags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getFlags() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the keyboard modifiers of an event |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the keyboard modifiers that present in the event - i.e. zero or more of the following keys, each with a value of <code>true</code>:</li><li>cmd</li><li>alt</li><li>shift</li><li>ctrl</li><li>fn</li><li>The table responds to the following methods:</li><li>contain(mods) -&gt; boolean</li><li>Returns true if the modifiers contain all of given modifiers</li><li>containExactly(mods) -&gt; boolean</li><li>Returns true if the modifiers contain all of given modifiers exactly and nothing else</li><li>Parameter mods is a table containing zero or more of the following:</li><li>cmd or ⌘</li><li>alt or ⌥</li><li>shift or ⇧</li><li>ctrl or ⌃</li><li>fn</li></ul> |

#### [getKeyCode](#getkeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getKeyCode() -> keycode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the raw keycode for the event |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number containing the raw keycode, taken from <code>hs.keycodes.map</code></li></ul> |
| **Notes**                                            | <ul><li>This method should only be used on keyboard events</li></ul> |

#### [getProperty](#getproperty)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getProperty(prop) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets a property of the event |
| **Parameters**                                       | <ul><li>prop - A value taken from <code>hs.eventtap.event.properties</code></li></ul> |
| **Returns**                                          | <ul><li>A number containing the value of the requested property</li></ul> |
| **Notes**                                            | <ul><li>The properties are <code>CGEventField</code> values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField</li></ul> |

#### [getRawEventData](#getraweventdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getRawEventData() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns raw data about the event |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table with two keys:</li><li>CGEventData -- a table with keys containing CGEvent data about the event.</li><li>NSEventData -- a table with keys containing NSEvent data about the event.</li></ul> |
| **Notes**                                            | <ul><li>Most of the data in <code>CGEventData</code> is already available through other methods, but is presented here without any cleanup or parsing.</li><li>This method is expected to be used mostly for testing and expanding the range of possibilities available with the hs.eventtap module.  If you find that you are regularly using specific data from this method for common or re-usable purposes, consider submitting a request for adding a more targeted method to hs.eventtap or hs.eventtap.event -- it will likely be more efficient and faster for common tasks, something eventtaps need to be to minimize affecting system responsiveness.</li></ul> |

#### [getType](#gettype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getType() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the type of the event |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number containing the type of the event, taken from <code>hs.eventtap.event.types</code></li></ul> |

#### [getUnicodeString](#getunicodestring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getUnicodeString()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the single unicode character of an event |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the unicode character</li></ul> |

#### [location](#location)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:location([pointTable]) -> event | table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the current mouse pointer location as defined for the event. |
| **Parameters**                                       | <ul><li>pointTable - an optional point table specifying the x and y coordinates of the mouse pointer location for the event</li></ul> |
| **Returns**                                          | <ul><li>if pointTable is provided, returns the <code>hs.eventtap.event</code> object; otherwise returns a point table containing x and y key-value pairs specifying the mouse pointer location as specified for this event.</li></ul> |
| **Notes**                                            | <ul><li>the use or effect of this method is undefined if the event is not a mouse type event.</li></ul> |

#### [post](#post)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:post([app])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Posts the event to the OS - i.e. emits the keyboard/mouse input defined by the event |
| **Parameters**                                       | <ul><li>app - An optional <code>hs.application</code> object. If specified, the event will only be sent to that application</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.eventtap.event</code> object</li></ul> |

#### [rawFlags](#rawflags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:rawFlags([flags]) -> event | integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Experimental method to get or set the modifier flags for an event directly. |
| **Parameters**                                       | <ul><li>flags - an optional integer, made by logically combining values from <a href="#rawFlagMasks">hs.eventtap.event.rawFlagMasks</a> specifying the modifier keys which should be set for this event</li></ul> |
| **Returns**                                          | <ul><li>if flags is provided, returns the <code>hs.eventtap.event</code> object; otherwise returns the current flags set as an integer</li></ul> |
| **Notes**                                            | <ul><li>This method is experimental and may undergo changes or even removal in the future</li><li>See <a href="#rawFlagMasks">hs.eventtap.event.rawFlagMasks</a> for more information</li></ul> |

#### [setFlags](#setflags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setFlags(table) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the keyboard modifiers of an event |
| **Parameters**                                       | <ul><li>A table containing the keyboard modifiers to be sent with the event - i.e. zero or more of the following keys, each with a value of <code>true</code>:</li><li>cmd</li><li>alt</li><li>shift</li><li>ctrl</li><li>fn</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.eventap.event</code> object.</li></ul> |

#### [setKeyCode](#setkeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setKeyCode(keycode)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the raw keycode for the event |
| **Parameters**                                       | <ul><li>keycode - A number containing a raw keycode, taken from <code>hs.keycodes.map</code></li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.eventtap.event</code> object</li></ul> |
| **Notes**                                            | <ul><li>This method should only be used on keyboard events</li></ul> |

#### [setProperty](#setproperty)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setProperty(prop, value)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets a property of the event |
| **Parameters**                                       | <ul><li>prop - A value from <code>hs.eventtap.event.properties</code></li><li>value - A number containing the value of the specified property</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.eventtap.event</code> object.</li></ul> |
| **Notes**                                            | <ul><li>The properties are <code>CGEventField</code> values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField</li></ul> |

#### [setType](#settype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setType(type) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Set the type for this event. |
| **Parameters**                                       | <ul><li>type - an integer matching one of the event types described in <a href="#types">hs.eventtap.event.types</a></li></ul> |
| **Returns**                                          | <ul><li>the <code>hs.eventtap.event</code> object</li></ul> |

#### [setUnicodeString](#setunicodestring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setUnicodeString(string)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets a unicode string as the output of the event |
| **Parameters**                                       | <ul><li>string - A string containing unicode characters, which will be applied to the event</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.eventtap.event</code> object</li></ul> |
| **Notes**                                            | <ul><li>Calling this method will reset any flags previously set on the event (because they don't make any sense, and you should not try to set flags again)</li><li>This is likely to only work with short unicode strings that resolve to a single character</li></ul> |

#### [systemKey](#systemkey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:systemKey() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the special key and its state if the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS (special-key pressed) |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>If the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, a table with the following keys defined:</li><li>key    -- a string containing one of the following labels indicating the key involved:<ul><li>SOUND_UP</li><li>SOUND_DOWN</li><li>MUTE</li><li>BRIGHTNESS_UP</li><li>BRIGHTNESS_DOWN</li><li>CONTRAST_UP</li><li>CONTRAST_DOWN</li><li>POWER</li><li>LAUNCH_PANEL</li><li>VIDMIRROR</li><li>PLAY</li><li>EJECT</li><li>NEXT</li><li>PREVIOUS</li><li>FAST</li><li>REWIND</li><li>ILLUMINATION_UP</li><li>ILLUMINATION_DOWN</li><li>ILLUMINATION_TOGGLE</li><li>CAPS_LOCK</li><li>HELP</li><li>NUM_LOCK or "undefined" if the key detected is unrecognized.</li></ul></li><li>keyCode -- the numeric keyCode corresponding to the key specified in <code>key</code>.</li><li>down   -- a boolean value indicating if the key is pressed down (true) or just released (false)</li><li>repeat -- a boolean indicating if this event is because the keydown is repeating.  This will always be false for a key release.</li><li>If the event does not correspond to a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, then an empty table is returned.</li></ul> |
| **Notes**                                            | <ul><li>CAPS_LOCK seems to sometimes generate 0 or 2 key release events (down == false), especially on builtin laptop keyboards, so it is probably safest (more reliable) to look for cases where down == true only.</li><li>If the key field contains "undefined", you can use the number in keyCode to look it up in <code>/System/Library/Frameworks/IOKit.framework/Headers/hidsystem/ev_keymap.h</code>.  If you believe the numeric value is part of a new system update or was otherwise mistakenly left out, please submit the label (it will defined in the header file as <code>NX_KEYTYPE_something</code>) and number to the Hammerspoon maintainers at https://github.com/Hammerspoon/hammerspoon with a request for inclusion in the next Hammerspoon update.</li></ul> |

#### [timestamp](#timestamp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:timestamp([absolutetime]) -> event | integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the timestamp of the event. |
| **Parameters**                                       | <ul><li>absolutetime - an optional integer specifying the timestamp for the event.</li></ul> |
| **Returns**                                          | <ul><li>if absolutetime is provided, returns the <code>hs.eventtap.event</code> object; otherwise returns the current timestamp for the event.</li></ul> |
| **Notes**                                            | <ul><li>Synthesized events have a timestamp of 0 by default.</li><li>The timestamp, if specified, is expressed as an integer representing the number of nanoseconds since the system was last booted.  See <code>hs.timer.absoluteTime</code>.</li><li>This field appears to be informational only and is not required when crafting your own events with this module.</li></ul> |

