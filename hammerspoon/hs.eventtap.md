# Hammerspoon docs: hs.eventtap

Tap into input events (mouse, keyboard, trackpad) for observation and possibly overriding them
It also provides convenience wrappers for sending mouse and keyboard events. If you need to construct finely controlled mouse/keyboard events, see hs.eventtap.event

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## Submodules
 * [hs.eventtap.event](hs.eventtap.event.md)

## API Overview
* Functions - API calls offered directly by the extension</li>
  * checkKeyboardModifiers
  * checkMouseButtons
  * doubleClickInterval
  * keyRepeatDelay
  * keyRepeatInterval
  * keyStroke
  * keyStrokes
  * leftClick
  * middleClick
  * rightClick
  * scrollWheel
* Constructors - API calls which return an object, typically one that offers API methods</li>
  * new
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * isEnabled
  * start
  * stop

## API Documentation

### Functions

#### checkKeyboardModifiers
  * Signature: hs.eventtap.checkKeyboardModifiers([raw]) -> table
  * Type: Function
  * Description: Returns a table containing the current key modifiers being pressed or in effect *at this instant* for the keyboard most recently used.
  * Parameters:
     * raw - an optional boolean value which, if true, includes the _raw key contining the numeric representation of all of the keyboard/modifier flags.
  * Returns:
     * Returns a table containing boolean values indicating which keyboard modifiers were held down when the function was invoked; The possible keys are:
        * cmd (or ⌘)
        * alt (or ⌥)
        * shift (or ⇧)
        * ctrl (or ⌃)
        * capslock
        * fn
      and optionally
        * _raw - a numeric representation of the numeric representation of all of the keyboard/modifier flags.
  * Notes:
     * This is an instantaneous poll of the current keyboard modifiers for the most recently used keyboard, not a callback.  This is useful primarily in conjuction with other modules, such as `hs.menubar`, when a callback is already in progress or waiting for an event callback is not practical or possible.
     * the numeric value returned is useful if you need to detect device dependent flags or flags which we normally ignore because they are not present (or are accessible another way) on most keyboards.

#### checkMouseButtons
  * Signature: hs.eventtap.checkMouseButtons() -> table
  * Type: Function
  * Description: Returns a table containing the current mouse buttons being pressed *at this instant*.
  * Parameters:
     None
  * Returns:
     * Returns an array containing indicies starting from 1 up to the highest numbered button currently being pressed where the index is `true` if the button is currently pressed or `false` if it is not.
     * Special hash tag synonyms for `left` (button 1), `right` (button 2), and `middle` (button 3) are also set to true if these buttons are currently being pressed.
  * Notes:
     * This is an instantaneous poll of the current mouse buttons, not a callback.  This is useful primarily in conjuction with other modules, such as `hs.menubar`, when a callback is already in progress or waiting for an event callback is not practical or possible.

#### doubleClickInterval
  * Signature: hs.eventtap.doubleClickInterval() -> number
  * Type: Function
  * Description: Returns the system-wide setting for the delay between two clicks, to register a double click event
  * Parameters:
     * None
  * Returns:
     * A number containing the maximum number of seconds between two mouse click events, for a double click event to be registered

#### keyRepeatDelay
  * Signature: hs.eventtap.keyRepeatDelay() -> number
  * Type: Function
  * Description: Returns the system-wide setting for the delay before keyboard repeat events begin
  * Parameters:
     * None
  * Returns:
     * A number containing the number of seconds before repeat events begin, after a key is held down

#### keyRepeatInterval
  * Signature: hs.eventtap.keyRepeatInterval() -> number
  * Type: Function
  * Description: Returns the system-wide setting for the interval between repeated keyboard events
  * Parameters:
     * None
  * Returns:
     * A number containing the number of seconds between keyboard events, if a key is held down

#### keyStroke
  * Signature: hs.eventtap.keyStroke(modifiers, character[, delay])
  * Type: Function
  * Description: Generates and emits a single keystroke event pair for the supplied keyboard modifiers and character
  * Parameters:
     * modifiers - A table containing the keyboard modifiers to apply ("fn", "ctrl", "alt", "cmd", "shift", "fn", or their Unicode equivalents)
     * character - A string containing a character to be emitted
     * delay - An optional delay (in microseconds) between mouse down and up event. Defaults to 200000 (i.e. 200ms)
  * Returns:
     * None
  * Notes:
     * This function is ideal for sending single keystrokes with a modifier applied (e.g. sending ⌘-v to paste, with `hs.eventtap.keyStroke({"cmd"}, "v")`). If you want to emit multiple keystrokes for typing strings of text, see `hs.eventtap.keyStrokes()`

#### keyStrokes
  * Signature: hs.eventtap.keyStrokes(text)
  * Type: Function
  * Description: Generates and emits keystroke events for the supplied text
  * Parameters:
     * text - A string containing the text to be typed
  * Returns:
     * None
  * Notes:
     * If you want to send a single keystroke with keyboard modifiers (e.g. sending ⌘-v to paste), see `hs.eventtap.keyStroke()`

#### leftClick
  * Signature: hs.eventtap.leftClick(point[, delay])
  * Type: Function
  * Description: Generates a left mouse click event at the specified point
  * Parameters:
     * point - A table with keys `{x, y}` indicating the location where the mouse event should occur
     * delay - An optional delay (in microseconds) between mouse down and up event. Defaults to 200000 (i.e. 200ms)
  * Returns:
     * None
  * Notes:
     * This is a wrapper around `hs.eventtap.event.newMouseEvent` that sends `leftmousedown` and `leftmouseup` events)

#### middleClick
  * Signature: hs.eventtap.middleClick(point[, delay])
  * Type: Function
  * Description: Generates a middle mouse click event at the specified point
  * Parameters:
     * point - A table with keys `{x, y}` indicating the location where the mouse event should occur
     * delay - An optional delay (in microseconds) between mouse down and up event. Defaults to 200000 (i.e. 200ms)
  * Returns:
     * None
  * Notes:
     * This is a wrapper around `hs.eventtap.event.newMouseEvent` that sends `middlemousedown` and `middlemouseup` events)

#### rightClick
  * Signature: hs.eventtap.rightClick(point[, delay])
  * Type: Function
  * Description: Generates a right mouse click event at the specified point
  * Parameters:
     * point - A table with keys `{x, y}` indicating the location where the mouse event should occur
     * delay - An optional delay (in microseconds) between mouse down and up event. Defaults to 200000 (i.e. 200ms)
  * Returns:
     * None
  * Notes:
     * This is a wrapper around `hs.eventtap.event.newMouseEvent` that sends `rightmousedown` and `rightmouseup` events)

#### scrollWheel
  * Signature: hs.eventtap.scrollWheel(offsets, modifiers, unit) -> event
  * Type: Function
  * Description: Generates and emits a scroll wheel event
  * Parameters:
     * offsets - A table containing the {horizontal, vertical} amount to scroll. Positive values scroll up or left, negative values scroll down or right.
     * mods - A table containing zero or more of the following:
      * cmd
      * alt
      * shift
      * ctrl
      * fn
     * unit - An optional string containing the name of the unit for scrolling. Either "line" (the default) or "pixel"
  * Returns:
     * None

### Constructors

#### new
  * Signature: hs.eventtap.new(types, fn) -> eventtap
  * Type: Constructor
  * Description: Create a new event tap object
  * Parameters:
     * types - A table that should contain values from `hs.eventtap.event.types`
     * fn - A function that will be called when the specified event types occur. The function should take a single parameter, which will be an event object. It can optionally return two values. Firstly, a boolean, true if the event should be deleted, false if it should propagate to any other applications watching for that event. Secondly, a table of events to post.
  * Returns:
     * An event tap object
  * Notes:
     * If you specify the argument `types` as the special table {"all"[, events to ignore]}, then *all* events (except those you optionally list *after* the "all" string) will trigger a callback, even events which are not defined in the [Quartz Event Reference](https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/Reference/reference.html).

### Methods

#### isEnabled
  * Signature: hs.eventtap:isEnabled() -> bool
  * Type: Method
  * Description: Determine whether or not an event tap object is enabled.
  * Parameters:
     * None
  * Returns:
     * True if the event tap is enabled or false if it is not.

#### start
  * Signature: hs.eventtap:start()
  * Type: Method
  * Description: Starts an event tap
  * Parameters:
     * None
  * Returns:
     * The event tap object

#### stop
  * Signature: hs.eventtap:stop()
  * Type: Method
  * Description: Stops an event tap
  * Parameters:
     * None
  * Returns:
     * The event tap object
