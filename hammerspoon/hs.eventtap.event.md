# Hammerspoon docs: hs.eventtap.event

Create, modify and inspect events for `hs.eventtap`

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constants - Useful values which cannot be changed</li>
  * properties
  * types
* Constructors - API calls which return an object, typically one that offers API methods</li>
  * copy
  * newKeyEvent
  * newMouseEvent
  * newScrollEvent
  * newSystemKeyEvent
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * getButtonState
  * getCharacters
  * getFlags
  * getKeyCode
  * getProperty
  * getRawEventData
  * getType
  * post
  * setFlags
  * setKeyCode
  * setProperty
  * systemKey

## API Documentation

### Constants

#### properties
  * Signature: hs.eventtap.event.properties -> table
  * Type: Constant
  * Description: A table containing property types for use with `hs.eventtap.event:getProperty()` and `hs.eventtap.event:setProperty()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility.
  The constants defined in this table are as follows:
       (I) in the description indicates that this property is returned or set as an integer
       (N) in the description indicates that this property is returned or set as a number (floating point)
      * mouseEventNumber                              -- (I) The mouse button event number. Matching mouse-down and mouse-up events will have the same event number.
      * mouseEventClickState                          -- (I) The mouse button click state. A click state of 1 represents a single click. A click state of 2 represents a double-click. A click state of 3 represents a triple-click.
      * mouseEventPressure                            -- (N) The mouse button pressure. The pressure value may range from 0 to 1, with 0 representing the mouse being up. This value is commonly set by tablet pens mimicking a mouse.
      * mouseEventButtonNumber                        -- (I) The mouse button number. For information about the possible values, see Mouse Buttons.
      * mouseEventDeltaX                              -- (I) The horizontal mouse delta since the last mouse movement event.
      * mouseEventDeltaY                              -- (I) The vertical mouse delta since the last mouse movement event.
      * mouseEventInstantMouser                       -- (I) The value is non-zero if the event should be ignored by the Inkwell subsystem.
      * mouseEventSubtype                             -- (I) Encoding of the mouse event subtype as a kCFNumberIntType.
      * keyboardEventAutorepeat                       -- (I) Non-zero when this is an autorepeat of a key-down, and zero otherwise.
      * keyboardEventKeycode                          -- (I) The virtual keycode of the key-down or key-up event.
      * keyboardEventKeyboardType                     -- (I) The keyboard type identifier.
      * scrollWheelEventDeltaAxis1                    -- (I) Scrolling data. This field typically contains the change in vertical position since the last scrolling event from a Mighty Mouse scroller or a single-wheel mouse scroller.
      * scrollWheelEventDeltaAxis2                    -- (I) Scrolling data. This field typically contains the change in horizontal position since the last scrolling event from a Mighty Mouse scroller.
      * scrollWheelEventDeltaAxis3                    -- (I) This field is not used.
      * scrollWheelEventFixedPtDeltaAxis1             -- (N) Contains scrolling data which represents a line-based or pixel-based change in vertical position since the last scrolling event from a Mighty Mouse scroller or a single-wheel mouse scroller.
      * scrollWheelEventFixedPtDeltaAxis2             -- (N) Contains scrolling data which represents a line-based or pixel-based change in horizontal position since the last scrolling event from a Mighty Mouse scroller.
      * scrollWheelEventFixedPtDeltaAxis3             -- (N) This field is not used.
      * scrollWheelEventPointDeltaAxis1               -- (I) Pixel-based scrolling data. The scrolling data represents the change in vertical position since the last scrolling event from a Mighty Mouse scroller or a single-wheel mouse scroller.
      * scrollWheelEventPointDeltaAxis2               -- (I) Pixel-based scrolling data. The scrolling data represents the change in horizontal position since the last scrolling event from a Mighty Mouse scroller.
      * scrollWheelEventPointDeltaAxis3               -- (I) This field is not used.
      * scrollWheelEventInstantMouser                 -- (I) Indicates whether the event should be ignored by the Inkwell subsystem. If the value is non-zero, the event should be ignored.
      * tabletEventPointX                             -- (I) The absolute X coordinate in tablet space at full tablet resolution.
      * tabletEventPointY                             -- (I) The absolute Y coordinate in tablet space at full tablet resolution.
      * tabletEventPointZ                             -- (I) The absolute Z coordinate in tablet space at full tablet resolution.
      * tabletEventPointButtons                       -- (I) The tablet button state. Bit 0 is the first button, and a set bit represents a closed or pressed button. Up to 16 buttons are supported.
      * tabletEventPointPressure                      -- (N) The tablet pen pressure. A value of 0.0 represents no pressure, and 1.0 represents maximum pressure.
      * tabletEventTiltX                              -- (N) The horizontal tablet pen tilt. A value of 0.0 represents no tilt, and 1.0 represents maximum tilt.
      * tabletEventTiltY                              -- (N) The vertical tablet pen tilt. A value of 0.0 represents no tilt, and 1.0 represents maximum tilt.
      * tabletEventRotation                           -- (N) The tablet pen rotation.
      * tabletEventTangentialPressure                 -- (N) The tangential pressure on the device. A value of 0.0 represents no pressure, and 1.0 represents maximum pressure.
      * tabletEventDeviceID                           -- (I) The system-assigned unique device ID.
      * tabletEventVendor1                            -- (I) A vendor-specified value.
      * tabletEventVendor2                            -- (I) A vendor-specified value.
      * tabletEventVendor3                            -- (I) A vendor-specified value.
      * tabletProximityEventVendorID                  -- (I) The vendor-defined ID, typically the USB vendor ID.
      * tabletProximityEventTabletID                  -- (I) The vendor-defined tablet ID, typically the USB product ID.
      * tabletProximityEventPointerID                 -- (I) The vendor-defined ID of the pointing device.
      * tabletProximityEventDeviceID                  -- (I) The system-assigned device ID.
      * tabletProximityEventSystemTabletID            -- (I) The system-assigned unique tablet ID.
      * tabletProximityEventVendorPointerType         -- (I) The vendor-assigned pointer type.
      * tabletProximityEventVendorPointerSerialNumber -- (I) The vendor-defined pointer serial number.
      * tabletProximityEventVendorUniqueID            -- (I) The vendor-defined unique ID.
      * tabletProximityEventCapabilityMask            -- (I) The device capabilities mask.
      * tabletProximityEventPointerType               -- (I) The pointer type.
      * tabletProximityEventEnterProximity            -- (I) Indicates whether the pen is in proximity to the tablet. The value is non-zero if the pen is in proximity to the tablet and zero when leaving the tablet.
      * eventTargetProcessSerialNumber                -- (I) The event target process serial number. The value is a 64-bit long word.
      * eventTargetUnixProcessID                      -- (I) The event target Unix process ID.
      * eventSourceUnixProcessID                      -- (I) The event source Unix process ID.
      * eventSourceUserData                           -- (I) Event source user-supplied data, up to 64 bits.
      * eventSourceUserID                             -- (I) The event source Unix effective UID.
      * eventSourceGroupID                            -- (I) The event source Unix effective GID.
      * eventSourceStateID                            -- (I) The event source state ID used to create this event.
      * scrollWheelEventIsContinuous                  -- (I) Indicates whether a scrolling event contains continuous, pixel-based scrolling data. The value is non-zero when the scrolling data is pixel-based and zero when the scrolling data is line-based.
  * Notes:
     * This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.eventtap.event.properties`.
     * In previous versions of Hammerspoon, property labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format.

#### types
  * Signature: hs.eventtap.event.types -> table
  * Type: Constant
  * Description: A table containing event types to be used with `hs.eventtap.new(...)` and returned by `hs.eventtap.event:type()`.  The table supports forward (label to number) and reverse (number to label) lookups to increase its flexibility.
  The constants defined in this table are as follows:
      * nullEvent               --  Specifies a null event.
      * leftMouseDown           --  Specifies a mouse down event with the left button.
      * leftMouseUp             --  Specifies a mouse up event with the left button.
      * rightMouseDown          --  Specifies a mouse down event with the right button.
      * rightMouseUp            --  Specifies a mouse up event with the right button.
      * mouseMoved              --  Specifies a mouse moved event.
      * leftMouseDragged        --  Specifies a mouse drag event with the left button down.
      * rightMouseDragged       --  Specifies a mouse drag event with the right button down.
      * keyDown                 --  Specifies a key down event.
      * keyUp                   --  Specifies a key up event.
      * flagsChanged            --  Specifies a key changed event for a modifier or status key.
      * scrollWheel             --  Specifies a scroll wheel moved event.
      * tabletPointer           --  Specifies a tablet pointer event.
      * tabletProximity         --  Specifies a tablet proximity event.
      * otherMouseDown          --  Specifies a mouse down event with one of buttons 2-31.
      * otherMouseUp            --  Specifies a mouse up event with one of buttons 2-31.
      * otherMouseDragged       --  Specifies a mouse drag event with one of buttons 2-31 down.
     The following events, also included in the lookup table, are provided through NSEvent and currently may require the use of `hs.eventtap.event:getRawEventData()` to retrieve supporting information.  Target specific methods may be added as the usability of these events is explored.
      * NSMouseEntered          --  See Mouse-Tracking and Cursor-Update Events in Cocoa Event Handling Guide.
      * NSMouseExited           --  See Mouse-Tracking and Cursor-Update Events in Cocoa Event Handling Guide.
      * NSCursorUpdate          --  See Mouse-Tracking and Cursor-Update Events in Cocoa Event Handling Guide.
      * NSAppKitDefined         --  See Event Objects and Types in Cocoa Event Handling Guide.
      * NSSystemDefined         --  See Event Objects and Types in Cocoa Event Handling Guide.
      * NSApplicationDefined    --  See Event Objects and Types in Cocoa Event Handling Guide.
      * NSPeriodic              --  See Event Objects and Types in Cocoa Event Handling Guide.
      * NSEventTypeGesture      --  An event that represents some type of gesture such as NSEventTypeMagnify, NSEventTypeSwipe, NSEventTypeRotate, NSEventTypeBeginGesture, or NSEventTypeEndGesture.
      * NSEventTypeMagnify      --  An event representing a pinch open or pinch close gesture.
      * NSEventTypeSwipe        --  An event representing a swipe gesture.
      * NSEventTypeRotate       --  An event representing a rotation gesture.
      * NSEventTypeBeginGesture --  An event that represents a gesture beginning.
      * NSEventTypeEndGesture   --  An event that represents a gesture ending.
      * NSEventTypeSmartMagnify --  NSEvent type for the smart zoom gesture (2-finger double tap on trackpads) along with a corresponding NSResponder method. In response to this event, you should intelligently magnify the content.
      * NSEventTypeQuickLook    --  Supports the new event responder method that initiates a Quicklook.
      * NSEventTypePressure     --  An NSEvent type representing a change in pressure on a pressure-sensitive device. Requires a 64-bit processor.
  * Notes:
     * This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.eventtap.event.types`.
     * In previous versions of Hammerspoon, type labels were defined with the labels in all lowercase.  This practice is deprecated, but an __index metamethod allows the lowercase labels to still be used; however a warning will be printed to the Hammerspoon console.  At some point, this may go away, so please update your code to follow the new format.

### Constructors

#### copy
  * Signature: hs.eventtap.event:copy() -> event
  * Type: Constructor
  * Description: Duplicates an `hs.eventtap.event` event for further modification or injection
  * Parameters:
     * None
  * Returns:
     * A new `hs.eventtap.event` object

#### newKeyEvent
  * Signature: hs.eventtap.event.newKeyEvent(mods, key, isdown) -> event
  * Type: Constructor
  * Description: Creates a keyboard event
  * Parameters:
     * mods - A table containing zero or more of the following:
      * cmd
      * alt
      * shift
      * ctrl
      * fn
     * key - A string containing the name of a key (see `hs.hotkey` for more information)
     * isdown - A boolean, true if the event should be a key-down, false if it should be a key-up
  * Returns:
     * An `hs.eventtap.event` object

#### newMouseEvent
  * Signature: hs.eventtap.event.newMouseEvent(eventtype, point[, modifiers) -> event
  * Type: Constructor
  * Description: Creates a new mouse event
  * Parameters:
     * eventtype - One of the values from `hs.eventtap.event.types`
     * point - A table with keys `{x, y}` indicating the location where the mouse event should occur
     * modifiers - An optional table containing zero or more of the following keys:
      * cmd
      * alt
      * shift
      * ctrl
      * fn
  * Returns:
     * An `hs.eventtap` object

#### newScrollEvent
  * Signature: hs.eventtap.event.newScrollEvent(offsets, mods, unit) -> event
  * Type: Constructor
  * Description: Creates a scroll wheel event
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
     * An `hs.eventtap.event` object

#### newSystemKeyEvent
  * Signature: hs.eventtap.event.newSystemKeyEvent(key, isdown) -> event
  * Type: Constructor
  * Description: Creates a keyboard event for special keys (e.g. media playback)
  * Parameters:
     * key - A string containing the name of a special key. The possible names are:
      * SOUND_UP
      * SOUND_DOWN
      * MUTE
      * BRIGHTNESS_UP
      * BRIGHTNESS_DOWN
      * CONTRAST_UP
      * CONTRAST_DOWN
      * POWER
      * LAUNCH_PANEL
      * VIDMIRROR
      * PLAY
      * EJECT
      * NEXT
      * PREVIOUS
      * FAST
      * REWIND
      * ILLUMINATION_UP
      * ILLUMINATION_DOWN
      * ILLUMINATION_TOGGLE
      * CAPS_LOCK
      * HELP
      * NUM_LOCK
     * isdown - A boolean, true if the event should be a key-down, false if it should be a key-up
  * Returns:
     * An `hs.eventtap.event` object
  * Notes:
     * To set modifiers on a system key event (e.g. cmd/ctrl/etc), see the `hs.eventtap.event:setFlags()` method
     * The event names are case sensitive

### Methods

#### getButtonState
  * Signature: hs.eventtap.event:getButtonState(button) -> bool
  * Type: Method
  * Description: Gets the state of a mouse button in the event
  * Parameters:
     * button - A number between 0 and 31. The left mouse button is 0, the right mouse button is 1 and the middle mouse button is 2. The meaning of the remaining buttons varies by hardware, and their functionality varies by application (typically they are not present on a mouse and have no effect in an application)
  * Returns:
     * A boolean, true if the specified mouse button is to be clicked by the event
  * Notes:
     * This method should only be called on mouse events

#### getCharacters
  * Signature: hs.eventtap.event:getCharacters([clean]) -> string or nil
  * Type: Method
  * Description: Returns the Unicode character, if any, represented by a keyDown or keyUp event.
  * Parameters:
     * clean -- an optional parameter, default `false`, which indicates if key modifiers, other than Shift, should be stripped from the keypress before converting to Unicode.
  * Returns:
     * A string containing the Unicode character represented by the keyDown or keyUp event, or nil if the event is not a keyUp or keyDown.
  * Notes:
     * This method should only be used on keyboard events
     * If `clean` is true, all modifiers except for Shift are stripped from the character before converting to the Unicode character represented by the keypress.
     * If the keypress does not correspond to a valid Unicode character, an empty string is returned (e.g. if `clean` is false, then Opt-E will return an empty string, while Opt-Shift-E will return an accent mark).

#### getFlags
  * Signature: hs.eventtap.event:getFlags() -> table
  * Type: Method
  * Description: Gets the keyboard modifiers of an event
  * Parameters:
     * None
  * Returns:
     * A table containing the keyboard modifiers that present in the event - i.e. zero or more of the following keys, each with a value of `true`:
      * cmd
      * alt
      * shift
      * ctrl
      * fn

#### getKeyCode
  * Signature: hs.eventtap.event:getKeyCode() -> keycode
  * Type: Method
  * Description: Gets the raw keycode for the event
  * Parameters:
     * None
  * Returns:
     * A number containing the raw keycode, taken from `hs.keycodes.map`
  * Notes:
     * This method should only be used on keyboard events

#### getProperty
  * Signature: hs.eventtap.event:getProperty(prop) -> number
  * Type: Method
  * Description: Gets a property of the event
  * Parameters:
     * prop - A value taken from `hs.eventtap.event.properties`
  * Returns:
     * A number containing the value of the requested property
  * Notes:
     * The properties are `CGEventField` values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField

#### getRawEventData
  * Signature: hs.eventtap.event:getRawEventData() -> table
  * Type: Method
  * Description: Returns raw data about the event
  * Parameters:
     * None
  * Returns:
     * A table with two keys:
       * CGEventData -- a table with keys containing CGEvent data about the event.
       * NSEventData -- a table with keys containing NSEvent data about the event.
  * Notes:
     * Most of the data in `CGEventData` is already available through other methods, but is presented here without any cleanup or parsing.
     * This method is expected to be used mostly for testing and expanding the range of possibilities available with the hs.eventtap module.  If you find that you are regularly using specific data from this method for common or re-usable purposes, consider submitting a request for adding a more targeted method to hs.eventtap or hs.eventtap.event -- it will likely be more efficient and faster for common tasks, something eventtaps need to be to minimize affecting system responsiveness.

#### getType
  * Signature: hs.eventtap.event:getType() -> number
  * Type: Method
  * Description: Gets the type of the event
  * Parameters:
     * None
  * Returns:
     * A number containing the type of the event, taken from `hs.eventtap.event.types`

#### post
  * Signature: hs.eventtap.event:post([app])
  * Type: Method
  * Description: Posts the event to the OS - i.e. emits the keyboard/mouse input defined by the event
  * Parameters:
     * app - An optional `hs.application` object. If specified, the event will only be sent to that application
  * Returns:
     * The `hs.eventtap.event` object

#### setFlags
  * Signature: hs.eventtap.event:setFlags(table)
  * Type: Method
  * Description: Sets the keyboard modifiers of an event
  * Parameters:
     * A table containing the keyboard modifiers to be sent with the event - i.e. zero or more of the following keys, each with a value of `true`:
      * cmd
      * alt
      * shift
      * ctrl
      * fn
  * Returns:
     * The `hs.eventap.event` object.

#### setKeyCode
  * Signature: hs.eventtap.event:setKeyCode(keycode)
  * Type: Method
  * Description: Sets the raw keycode for the event
  * Parameters:
     * keycode - A number containing a raw keycode, taken from `hs.keycodes.map`
  * Returns:
     * The `hs.eventtap.event` object
  * Notes:
     * This method should only be used on keyboard events

#### setProperty
  * Signature: hs.eventtap.event:setProperty(prop, value)
  * Type: Method
  * Description: Sets a property of the event
  * Parameters:
     * prop - A value from `hs.eventtap.event.properties`
     * value - A number containing the value of the specified property
  * Returns:
     * The `hs.eventtap.event` object.
  * Notes:
     * The properties are `CGEventField` values, as documented at https://developer.apple.com/library/mac/documentation/Carbon/Reference/QuartzEventServicesRef/index.html#//apple_ref/c/tdef/CGEventField

#### systemKey
  * Signature: hs.eventtap.event:systemKey() -> table
  * Type: Method
  * Description: Returns the special key and its state if the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS (special-key pressed)
  * Parameters:
     * None
  * Returns:
     * If the event is a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, a table with the following keys defined:
       * key    -- a string containing one of the following labels indicating the key involved:
         * SOUND_UP
         * SOUND_DOWN
         * MUTE
         * BRIGHTNESS_UP
         * BRIGHTNESS_DOWN
         * CONTRAST_UP
         * CONTRAST_DOWN
         * POWER
         * LAUNCH_PANEL
         * VIDMIRROR
         * PLAY
         * EJECT
         * NEXT
         * PREVIOUS
         * FAST
         * REWIND
         * ILLUMINATION_UP
         * ILLUMINATION_DOWN
         * ILLUMINATION_TOGGLE
         * CAPS_LOCK
         * HELP
         * NUM_LOCK
         or "undefined" if the key detected is unrecognized.
       * keyCode -- the numeric keyCode corresponding to the key specified in `key`.
       * down   -- a boolean value indicating if the key is pressed down (true) or just released (false)
       * repeat -- a boolean indicating if this event is because the keydown is repeating.  This will always be false for a key release.
     * If the event does not correspond to a NSSystemDefined event of subtype AUX_CONTROL_BUTTONS, then an empty table is returned.
  * Notes:
    * CAPS_LOCK seems to sometimes generate 0 or 2 key release events (down == false), especially on builtin laptop keyboards, so it is probably safest (more reliable) to look for cases where down == true only.
    * If the key field contains "undefined", you can use the number in keyCode to look it up in `/System/Library/Frameworks/IOKit.framework/Headers/hidsystem/ev_keymap.h`.  If you believe the numeric value is part of a new system update or was otherwise mistakenly left out, please submit the label (it will defined in the header file as `NX_KEYTYPE_something`) and number to the Hammerspoon maintainers at https://github.com/Hammerspoon/hammerspoon with a request for inclusion in the next Hammerspoon update.
