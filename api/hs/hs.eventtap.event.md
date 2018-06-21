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
 * [location](#location)
 * [post](#post)
 * [rawFlags](#rawflags)
 * [setFlags](#setflags)
 * [setKeyCode](#setkeycode)
 * [setProperty](#setproperty)
 * [setType](#settype)
 * [systemKey](#systemkey)
 * [timestamp](#timestamp)

## API Documentation

### Constants

#### [properties](#properties)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.properties -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing property types for use with `hs.eventtap.event:getProperty()` and `hs.eventtap.event:setProperty()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility.                                                                                         |
| **Notes**                                            |  * This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.eventtap.event.properties`. * In previous versions of Hammerspoon, property labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format.                                                      |

#### [rawFlagMasks](#rawflagmasks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.rawFlagMasks[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing key-value pairs describing the raw modifier flags which can be manipulated with [hs.eventtap.event:rawFlags](#rawFlags).                                                                                         |

#### [types](#types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.types -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing event types to be used with `hs.eventtap.new(...)` and returned by `hs.eventtap.event:type()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility.                                                                                         |
| **Notes**                                            |  * This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.eventtap.event.types`. * In previous versions of Hammerspoon, type labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format.                                                      |

### Functions

#### [newKeyEventSequence](#newkeyeventsequence)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newKeyEventSequence(modifiers, character) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a table containing the keydown and keyup events to generate the keystroke with the specified modifiers.                                                                                         |
| **Parameters**                                       |  * modifiers - A table containing the keyboard modifiers to apply ("cmd", "alt", "shift", "ctrl", "rightCmd", "rightAlt", "rightShift", "rightCtrl", or "fn") * character - A string containing a character to be emitted                                       |
| **Returns**                                          |  * a table with events which contains the individual events that Apple recommends for building up a keystroke combination (see [hs.eventtap.event.newKeyEvent](#newKeyEvents)) in the order that they should be posted (i.e. the first half will contain keyDown events and the second half will contain keyUp events)                                                |
| **Notes**                                            |  * The `modifiers` table must contain the full name of the modifiers you wish used for the keystroke as defined in `hs.keycodes.map` -- the Unicode equivalents are not supported by this function. * The returned table will always contain an even number of events -- the first half will be the keyDown events and the second half will be the keyUp events. * The events have not been posted; the table can be used without change as the return value for a callback to a watcher defined with [hs.eventtap.new](#new).                                                      |

### Constructors

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:copy() -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Duplicates an `hs.eventtap.event` event for further modification or injection                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A new `hs.eventtap.event` object                                                |

#### [newEvent](#newevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newEvent() -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a blank event.  You will need to set its type with [hs.eventtap.event:setType](#setType)                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * a new `hs.eventtap.event` object                                                |
| **Notes**                                            |  * this is an empty event that you should set a type for and whatever other properties may be appropriate before posting.                                                      |

#### [newEventFromData](#neweventfromdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newEventFromData(data) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates an event from the data encoded in the string provided.                                                                                         |
| **Parameters**                                       |  * data - a string containing binary data provided by [hs.eventtap.event:asData](#asData) representing an event.                                       |
| **Returns**                                          |  * a new `hs.eventtap.event` object or nil if the string did not represent a valid event                                                |

#### [newKeyEvent](#newkeyevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newKeyEvent([mods], key, isdown) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a keyboard event                                                                                         |
| **Parameters**                                       |  * mods - An optional table containing zero or more of the following:  * cmd  * alt  * shift  * ctrl  * fn * key - A string containing the name of a key (see `hs.hotkey` for more information) or an integer specifying the virtual keycode for the key. * isdown - A boolean, true if the event should be a key-down, false if it should be a key-up                                       |
| **Returns**                                          |  * An `hs.eventtap.event` object                                                |
| **Notes**                                            |  * The original version of this constructor utilized a shortcut which merged `flagsChanged` and `keyUp`/`keyDown` events into one.  This approach is still supported for backwards compatibility and because it *does* work in most cases. * According to Apple Documentation, the proper way to perform a keypress with modifiers is through multiple key events; for example to generate 'Å', you should do the following:~~~lua    hs.eventtap.event.newKeyEvent(hs.keycodes.map.shift, true):post()    hs.eventtap.event.newKeyEvent(hs.keycodes.map.alt, true):post()    hs.eventtap.event.newKeyEvent("a", true):post()    hs.eventtap.event.newKeyEvent("a", false):post()    hs.eventtap.event.newKeyEvent(hs.keycodes.map.alt, false):post()    hs.eventtap.event.newKeyEvent(hs.keycodes.map.shift, false):post()~~~ * The shortcut method is still supported, though if you run into odd behavior or need to generate `flagsChanged` events without a corresponding `keyUp` or `keyDown`, please check out the syntax demonstrated above.~~~lua    hs.eventtap.event.newKeyEvent({"shift", "alt"}, "a", true):post()    hs.eventtap.event.newKeyEvent({"shift", "alt"}, "a", false):post()~~~                                                      |

#### [newMouseEvent](#newmouseevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newMouseEvent(eventtype, point[, modifiers) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new mouse event                                                                                         |
| **Parameters**                                       |  * eventtype - One of the values from `hs.eventtap.event.types` * point - An hs.geometry point table (i.e. of the form `{x=123, y=456}`) indicating the location where the mouse event should occur * modifiers - An optional table containing zero or more of the following keys:  * cmd  * alt  * shift  * ctrl  * fn                                       |
| **Returns**                                          |  * An `hs.eventtap` object                                                |

#### [newScrollEvent](#newscrollevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newScrollEvent(offsets, mods, unit) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a scroll wheel event                                                                                         |
| **Parameters**                                       |  * offsets - A table containing the {horizontal, vertical} amount to scroll. Positive values scroll up or left, negative values scroll down or right. * mods - A table containing zero or more of the following:  * cmd  * alt  * shift  * ctrl  * fn * unit - An optional string containing the name of the unit for scrolling. Either "line" (the default) or "pixel"                                       |
| **Returns**                                          |  * An `hs.eventtap.event` object                                                |

#### [newSystemKeyEvent](#newsystemkeyevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event.newSystemKeyEvent(key, isdown) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a keyboard event for special keys (e.g. media playback)                                                                                         |
| **Parameters**                                       |  * key - A string containing the name of a special key. The possible names are:  * SOUND_UP  * SOUND_DOWN  * MUTE  * BRIGHTNESS_UP  * BRIGHTNESS_DOWN  * CONTRAST_UP  * CONTRAST_DOWN  * POWER  * LAUNCH_PANEL  * VIDMIRROR  * PLAY  * EJECT  * NEXT  * PREVIOUS  * FAST  * REWIND  * ILLUMINATION_UP  * ILLUMINATION_DOWN  * ILLUMINATION_TOGGLE  * CAPS_LOCK  * HELP  * NUM_LOCK * isdown - A boolean, true if the event should be a key-down, false if it should be a key-up                                       |
| **Returns**                                          |  * An `hs.eventtap.event` object                                                |
| **Notes**                                            |  * To set modifiers on a system key event (e.g. cmd/ctrl/etc), see the `hs.eventtap.event:setFlags()` method * The event names are case sensitive                                                      |

### Methods

#### [asData](#asdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:asData() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a string containing binary data representing the event.  This can be used to record events for later use.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * a string representing the event or nil if the event cannot be represented as a string                                                |
| **Notes**                                            |  * You can recreate the event for later posting with [hs.eventtap.event.newnEventFromData](#newEventFromData)                                                      |

#### [getButtonState](#getbuttonstate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getButtonState(button) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the state of a mouse button in the event                                                                                         |
| **Parameters**                                       |  * button - A number between 0 and 31. The left mouse button is 0, the right mouse button is 1 and the middle mouse button is 2. The meaning of the remaining buttons varies by hardware, and their functionality varies by application (typically they are not present on a mouse and have no effect in an application)                                       |
| **Returns**                                          |  * A boolean, true if the specified mouse button is to be clicked by the event                                                |
| **Notes**                                            |  * This method should only be called on mouse events                                                      |

#### [getCharacters](#getcharacters)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getCharacters([clean]) -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Unicode character, if any, represented by a keyDown or keyUp event.                                                                                         |
| **Parameters**                                       |  * clean -- an optional parameter, default `false`, which indicates if key modifiers, other than Shift, should be stripped from the keypress before converting to Unicode.                                       |
| **Returns**                                          |  * A string containing the Unicode character represented by the keyDown or keyUp event, or nil if the event is not a keyUp or keyDown.                                                |
| **Notes**                                            |  * This method should only be used on keyboard events * If `clean` is true, all modifiers except for Shift are stripped from the character before converting to the Unicode character represented by the keypress. * If the keypress does not correspond to a valid Unicode character, an empty string is returned (e.g. if `clean` is false, then Opt-E will return an empty string, while Opt-Shift-E will return an accent mark).                                                      |

#### [getFlags](#getflags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getFlags() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the keyboard modifiers of an event                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the keyboard modifiers that present in the event - i.e. zero or more of the following keys, each with a value of `true`:  * cmd  * alt  * shift  * ctrl  * fn * The table responds to the following methods:  * contain(mods) -> boolean   * Returns true if the modifiers contain all of given modifiers  * containExactly(mods) -> boolean   * Returns true if the modifiers contain all of given modifiers exactly and nothing else * Parameter mods is a table containing zero or more of the following:  * cmd or ⌘  * alt or ⌥  * shift or ⇧  * ctrl or ⌃  * fn                                                |

#### [getKeyCode](#getkeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getKeyCode() -> keycode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the raw keycode for the event                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A number containing the raw keycode, taken from `hs.keycodes.map`                                                |
| **Notes**                                            |  * This method should only be used on keyboard events                                                      |

#### [getProperty](#getproperty)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getProperty(prop) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a property of the event                                                                                         |
| **Parameters**                                       |  * prop - A value taken from `hs.eventtap.event.properties`                                       |
| **Returns**                                          |  * A number containing the value of the requested property                                                |
| **Notes**                                            |  * The properties are `CGEventField` values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField                                                      |

#### [getRawEventData](#getraweventdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getRawEventData() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns raw data about the event                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table with two keys:   * CGEventData -- a table with keys containing CGEvent data about the event.   * NSEventData -- a table with keys containing NSEvent data about the event.                                                |
| **Notes**                                            |  * Most of the data in `CGEventData` is already available through other methods, but is presented here without any cleanup or parsing. * This method is expected to be used mostly for testing and expanding the range of possibilities available with the hs.eventtap module.  If you find that you are regularly using specific data from this method for common or re-usable purposes, consider submitting a request for adding a more targeted method to hs.eventtap or hs.eventtap.event -- it will likely be more efficient and faster for common tasks, something eventtaps need to be to minimize affecting system responsiveness.                                                      |

#### [getType](#gettype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:getType() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the type of the event                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A number containing the type of the event, taken from `hs.eventtap.event.types`                                                |

#### [location](#location)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:location([pointTable]) -> event | table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the current mouse pointer location as defined for the event.                                                                                         |
| **Parameters**                                       |  * pointTable - an optional point table specifying the x and y coordinates of the mouse pointer location for the event                                       |
| **Returns**                                          |  * if pointTable is provided, returns the `hs.eventtap.event` object; otherwise returns a point table containing x and y key-value pairs specifying the mouse pointer location as specified for this event.                                                |
| **Notes**                                            |  * the use or effect of this method is undefined if the event is not a mouse type event.                                                      |

#### [post](#post)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:post([app])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Posts the event to the OS - i.e. emits the keyboard/mouse input defined by the event                                                                                         |
| **Parameters**                                       |  * app - An optional `hs.application` object. If specified, the event will only be sent to that application                                       |
| **Returns**                                          |  * The `hs.eventtap.event` object                                                |

#### [rawFlags](#rawflags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:rawFlags([flags]) -> event | integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Experimental method to get or set the modifier flags for an event directly.                                                                                         |
| **Parameters**                                       |  * flags - an optional integer, made by logically combining values from [hs.eventtap.event.rawFlagMasks](#rawFlagMasks) specifying the modifier keys which should be set for this event                                       |
| **Returns**                                          |  * if flags is provided, returns the `hs.eventtap.event` object; otherwise returns the current flags set as an integer                                                |
| **Notes**                                            |  * This method is experimental and may undergo changes or even removal in the future * See [hs.eventtap.event.rawFlagMasks](#rawFlagMasks) for more information                                                      |

#### [setFlags](#setflags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setFlags(table) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the keyboard modifiers of an event                                                                                         |
| **Parameters**                                       |  * A table containing the keyboard modifiers to be sent with the event - i.e. zero or more of the following keys, each with a value of `true`:  * cmd  * alt  * shift  * ctrl  * fn                                       |
| **Returns**                                          |  * The `hs.eventap.event` object.                                                |

#### [setKeyCode](#setkeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setKeyCode(keycode)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the raw keycode for the event                                                                                         |
| **Parameters**                                       |  * keycode - A number containing a raw keycode, taken from `hs.keycodes.map`                                       |
| **Returns**                                          |  * The `hs.eventtap.event` object                                                |
| **Notes**                                            |  * This method should only be used on keyboard events                                                      |

#### [setProperty](#setproperty)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setProperty(prop, value)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets a property of the event                                                                                         |
| **Parameters**                                       |  * prop - A value from `hs.eventtap.event.properties` * value - A number containing the value of the specified property                                       |
| **Returns**                                          |  * The `hs.eventtap.event` object.                                                |
| **Notes**                                            |  * The properties are `CGEventField` values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField                                                      |

#### [setType](#settype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:setType(type) -> event` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set the type for this event.                                                                                         |
| **Parameters**                                       |  * type - an integer matching one of the event types described in [hs.eventtap.event.types](#types)                                       |
| **Returns**                                          |  * the `hs.eventtap.event` object                                                |

#### [systemKey](#systemkey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:systemKey() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the special key and its state if the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS (special-key pressed)                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * If the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, a table with the following keys defined:   * key    -- a string containing one of the following labels indicating the key involved:     * SOUND_UP     * SOUND_DOWN     * MUTE     * BRIGHTNESS_UP     * BRIGHTNESS_DOWN     * CONTRAST_UP     * CONTRAST_DOWN     * POWER     * LAUNCH_PANEL     * VIDMIRROR     * PLAY     * EJECT     * NEXT     * PREVIOUS     * FAST     * REWIND     * ILLUMINATION_UP     * ILLUMINATION_DOWN     * ILLUMINATION_TOGGLE     * CAPS_LOCK     * HELP     * NUM_LOCK     or "undefined" if the key detected is unrecognized.   * keyCode -- the numeric keyCode corresponding to the key specified in `key`.   * down   -- a boolean value indicating if the key is pressed down (true) or just released (false)   * repeat -- a boolean indicating if this event is because the keydown is repeating.  This will always be false for a key release. * If the event does not correspond to a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, then an empty table is returned.                                                |
| **Notes**                                            | * CAPS_LOCK seems to sometimes generate 0 or 2 key release events (down == false), especially on builtin laptop keyboards, so it is probably safest (more reliable) to look for cases where down == true only.* If the key field contains "undefined", you can use the number in keyCode to look it up in `/System/Library/Frameworks/IOKit.framework/Headers/hidsystem/ev_keymap.h`.  If you believe the numeric value is part of a new system update or was otherwise mistakenly left out, please submit the label (it will defined in the header file as `NX_KEYTYPE_something`) and number to the Hammerspoon maintainers at https://github.com/Hammerspoon/hammerspoon with a request for inclusion in the next Hammerspoon update.                                                      |

#### [timestamp](#timestamp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.eventtap.event:timestamp([absolutetime]) -> event | integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the timestamp of the event.                                                                                         |
| **Parameters**                                       |  * absolutetime - an optional integer specifying the timestamp for the event.                                       |
| **Returns**                                          |  * if absolutetime is provided, returns the `hs.eventtap.event` object; otherwise returns the current timestamp for the event.                                                |
| **Notes**                                            |  * Synthesized events have a timestamp of 0 by default. * The timestamp, if specified, is expressed as an integer representing the number of nanoseconds since the system was last booted.  See `hs.timer.absoluteTime`. * This field appears to be informational only and is not required when crafting your own events with this module.                                                      |

