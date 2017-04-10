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
 * [newKeyEvent](#newKeyEvent)
 * [newMouseEvent](#newMouseEvent)
 * [newScrollEvent](#newScrollEvent)
 * [newSystemKeyEvent](#newSystemKeyEvent)
* Methods - API calls which can only be made on an object returned by a constructor
 * [getButtonState](#getButtonState)
 * [getCharacters](#getCharacters)
 * [getFlags](#getFlags)
 * [getKeyCode](#getKeyCode)
 * [getProperty](#getProperty)
 * [getRawEventData](#getRawEventData)
 * [getType](#getType)
 * [post](#post)
 * [setFlags](#setFlags)
 * [setKeyCode](#setKeyCode)
 * [setProperty](#setProperty)
 * [systemKey](#systemKey)

## API Documentation
### Constants

#### [properties](#properties)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event.properties -> table  |
| Type        | Constant |
| Description | A table containing property types for use with `hs.eventtap.event:getProperty()` and `hs.eventtap.event:setProperty()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility. |
| Notes |  * This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.eventtap.event.properties`. * In previous versions of Hammerspoon, property labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format.

#### [types](#types)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event.types -> table  |
| Type        | Constant |
| Description | A table containing event types to be used with `hs.eventtap.new(...)` and returned by `hs.eventtap.event:type()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility. |
| Notes |  * This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.eventtap.event.types`. * In previous versions of Hammerspoon, type labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format. |

### Constructors

#### [copy](#copy)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:copy() -> event  |
| Type        | Constructor |
| Description | Duplicates an `hs.eventtap.event` event for further modification or injection |
| Parameters |  * None |
| Returns |  * A new `hs.eventtap.event` object |


#### [newKeyEvent](#newKeyEvent)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event.newKeyEvent(mods, key, isdown) -> event  |
| Type        | Constructor |
| Description | Creates a keyboard event |
| Parameters |  * mods - A table containing zero or more of the following:  * cmd  * alt  * shift  * ctrl  * fn * key - A string containing the name of a key (see `hs.hotkey` for more information) * isdown - A boolean, true if the event should be a key-down, false if it should be a key-up |
| Returns |  * An `hs.eventtap.event` object |


#### [newMouseEvent](#newMouseEvent)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event.newMouseEvent(eventtype, point[, modifiers) -> event  |
| Type        | Constructor |
| Description | Creates a new mouse event |
| Parameters |  * eventtype - One of the values from `hs.eventtap.event.types` * point - A table with keys `{x, y}` indicating the location where the mouse event should occur * modifiers - An optional table containing zero or more of the following keys:  * cmd  * alt  * shift  * ctrl  * fn |
| Returns |  * An `hs.eventtap` object |


#### [newScrollEvent](#newScrollEvent)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event.newScrollEvent(offsets, mods, unit) -> event  |
| Type        | Constructor |
| Description | Creates a scroll wheel event |
| Parameters |  * offsets - A table containing the {horizontal, vertical} amount to scroll. Positive values scroll up or left, negative values scroll down or right. * mods - A table containing zero or more of the following:  * cmd  * alt  * shift  * ctrl  * fn * unit - An optional string containing the name of the unit for scrolling. Either "line" (the default) or "pixel" |
| Returns |  * An `hs.eventtap.event` object |


#### [newSystemKeyEvent](#newSystemKeyEvent)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event.newSystemKeyEvent(key, isdown) -> event  |
| Type        | Constructor |
| Description | Creates a keyboard event for special keys (e.g. media playback) |
| Parameters |  * key - A string containing the name of a special key. The possible names are:  * SOUND_UP  * SOUND_DOWN  * MUTE  * BRIGHTNESS_UP  * BRIGHTNESS_DOWN  * CONTRAST_UP  * CONTRAST_DOWN  * POWER  * LAUNCH_PANEL  * VIDMIRROR  * PLAY  * EJECT  * NEXT  * PREVIOUS  * FAST  * REWIND  * ILLUMINATION_UP  * ILLUMINATION_DOWN  * ILLUMINATION_TOGGLE  * CAPS_LOCK  * HELP  * NUM_LOCK * isdown - A boolean, true if the event should be a key-down, false if it should be a key-up |
| Returns |  * An `hs.eventtap.event` object |
| Notes |  * To set modifiers on a system key event (e.g. cmd/ctrl/etc), see the `hs.eventtap.event:setFlags()` method * The event names are case sensitive |

### Methods

#### [getButtonState](#getButtonState)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:getButtonState(button) -> bool  |
| Type        | Method |
| Description | Gets the state of a mouse button in the event |
| Parameters |  * button - A number between 0 and 31. The left mouse button is 0, the right mouse button is 1 and the middle mouse button is 2. The meaning of the remaining buttons varies by hardware, and their functionality varies by application (typically they are not present on a mouse and have no effect in an application) |
| Returns |  * A boolean, true if the specified mouse button is to be clicked by the event |
| Notes |  * This method should only be called on mouse events

#### [getCharacters](#getCharacters)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:getCharacters([clean]) -> string or nil  |
| Type        | Method |
| Description | Returns the Unicode character, if any, represented by a keyDown or keyUp event. |
| Parameters |  * clean -- an optional parameter, default `false`, which indicates if key modifiers, other than Shift, should be stripped from the keypress before converting to Unicode. |
| Returns |  * A string containing the Unicode character represented by the keyDown or keyUp event, or nil if the event is not a keyUp or keyDown. |
| Notes |  * This method should only be used on keyboard events * If `clean` is true, all modifiers except for Shift are stripped from the character before converting to the Unicode character represented by the keypress. * If the keypress does not correspond to a valid Unicode character, an empty string is returned (e.g. if `clean` is false, then Opt-E will return an empty string, while Opt-Shift-E will return an accent mark).

#### [getFlags](#getFlags)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:getFlags() -> table  |
| Type        | Method |
| Description | Gets the keyboard modifiers of an event |
| Parameters |  * None |
| Returns |  * A table containing the keyboard modifiers that present in the event - i.e. zero or more of the following keys, each with a value of `true`:  * cmd  * alt  * shift  * ctrl  * fn |


#### [getKeyCode](#getKeyCode)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:getKeyCode() -> keycode  |
| Type        | Method |
| Description | Gets the raw keycode for the event |
| Parameters |  * None |
| Returns |  * A number containing the raw keycode, taken from `hs.keycodes.map` |
| Notes |  * This method should only be used on keyboard events

#### [getProperty](#getProperty)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:getProperty(prop) -> number  |
| Type        | Method |
| Description | Gets a property of the event |
| Parameters |  * prop - A value taken from `hs.eventtap.event.properties` |
| Returns |  * A number containing the value of the requested property |
| Notes |  * The properties are `CGEventField` values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField

#### [getRawEventData](#getRawEventData)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:getRawEventData() -> table  |
| Type        | Method |
| Description | Returns raw data about the event |
| Parameters |  * None |
| Returns |  * A table with two keys:   * CGEventData -- a table with keys containing CGEvent data about the event.   * NSEventData -- a table with keys containing NSEvent data about the event. |
| Notes |  * Most of the data in `CGEventData` is already available through other methods, but is presented here without any cleanup or parsing. * This method is expected to be used mostly for testing and expanding the range of possibilities available with the hs.eventtap module.  If you find that you are regularly using specific data from this method for common or re-usable purposes, consider submitting a request for adding a more targeted method to hs.eventtap or hs.eventtap.event -- it will likely be more efficient and faster for common tasks, something eventtaps need to be to minimize affecting system responsiveness.

#### [getType](#getType)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:getType() -> number  |
| Type        | Method |
| Description | Gets the type of the event |
| Parameters |  * None |
| Returns |  * A number containing the type of the event, taken from `hs.eventtap.event.types` |


#### [post](#post)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:post([app])  |
| Type        | Method |
| Description | Posts the event to the OS - i.e. emits the keyboard/mouse input defined by the event |
| Parameters |  * app - An optional `hs.application` object. If specified, the event will only be sent to that application |
| Returns |  * The `hs.eventtap.event` object |


#### [setFlags](#setFlags)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:setFlags(table)  |
| Type        | Method |
| Description | Sets the keyboard modifiers of an event |
| Parameters |  * A table containing the keyboard modifiers to be sent with the event - i.e. zero or more of the following keys, each with a value of `true`:  * cmd  * alt  * shift  * ctrl  * fn |
| Returns |  * The `hs.eventap.event` object. |


#### [setKeyCode](#setKeyCode)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:setKeyCode(keycode)  |
| Type        | Method |
| Description | Sets the raw keycode for the event |
| Parameters |  * keycode - A number containing a raw keycode, taken from `hs.keycodes.map` |
| Returns |  * The `hs.eventtap.event` object |
| Notes |  * This method should only be used on keyboard events

#### [setProperty](#setProperty)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:setProperty(prop, value)  |
| Type        | Method |
| Description | Sets a property of the event |
| Parameters |  * prop - A value from `hs.eventtap.event.properties` * value - A number containing the value of the specified property |
| Returns |  * The `hs.eventtap.event` object. |
| Notes |  * The properties are `CGEventField` values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField

#### [systemKey](#systemKey)
|             |                 |
| ------------|-----------------|
| Signature   | hs.eventtap.event:systemKey() -> table  |
| Type        | Method |
| Description | Returns the special key and its state if the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS (special-key pressed) |
| Parameters |  * None |
| Returns |  * If the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, a table with the following keys defined:   * key    -- a string containing one of the following labels indicating the key involved:     * SOUND_UP     * SOUND_DOWN     * MUTE     * BRIGHTNESS_UP     * BRIGHTNESS_DOWN     * CONTRAST_UP     * CONTRAST_DOWN     * POWER     * LAUNCH_PANEL     * VIDMIRROR     * PLAY     * EJECT     * NEXT     * PREVIOUS     * FAST     * REWIND     * ILLUMINATION_UP     * ILLUMINATION_DOWN     * ILLUMINATION_TOGGLE     * CAPS_LOCK     * HELP     * NUM_LOCK     or "undefined" if the key detected is unrecognized.   * keyCode -- the numeric keyCode corresponding to the key specified in `key`.   * down   -- a boolean value indicating if the key is pressed down (true) or just released (false)   * repeat -- a boolean indicating if this event is because the keydown is repeating.  This will always be false for a key release. * If the event does not correspond to a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, then an empty table is returned. |
| Notes | * CAPS_LOCK seems to sometimes generate 0 or 2 key release events (down == false), especially on builtin laptop keyboards, so it is probably safest (more reliable) to look for cases where down == true only.* If the key field contains "undefined", you can use the number in keyCode to look it up in `/System/Library/Frameworks/IOKit.framework/Headers/hidsystem/ev_keymap.h`.  If you believe the numeric value is part of a new system update or was otherwise mistakenly left out, please submit the label (it will defined in the header file as `NX_KEYTYPE_something`) and number to the Hammerspoon maintainers at https://github.com/Hammerspoon/hammerspoon with a request for inclusion in the next Hammerspoon update. |
