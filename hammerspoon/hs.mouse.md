# [docs](index.md) » hs.mouse
---

Inspect/manipulate the position of the mouse pointer

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Functions - API calls offered directly by the extension
** [getAbsolutePosition](#getAbsolutePosition)
** [getButtons](#getButtons)
** [getCurrentScreen](#getCurrentScreen)
** [getRelativePosition](#getRelativePosition)
** [setAbsolutePosition](#setAbsolutePosition)
** [setRelativePosition](#setRelativePosition)
** [trackingSpeed](#trackingSpeed)

## API Documentation

### Functions

#### [getAbsolutePosition](#getAbsolutePosition)
| | |
|-|-|
| Signature   | hs.mouse.getAbsolutePosition() -> point  |
| Type        | Function |
| Description | Gets the absolute co-ordinates of the mouse pointer |
| Parameters |  * None | | Returns |  * A point-table containing the absolute x and y co-ordinates of the mouse pointer | | Notes |  * The co-ordinates returned by this function are in relation to the full size of your desktop. If you have multiple monitors, the desktop is a large virtual rectangle that contains them all (e.g. if you have two 1920x1080 monitors and the mouse is in the middle of the second monitor, the returned table would be `{ x=2879, y=540 }`) * Multiple monitors of different sizes can cause the co-ordinates of some areas of the desktop to be negative. This is perfectly normal. 0,0 in the co-ordinates of the desktop is the top left of the primary monitor | 
#### [getButtons](#getButtons)
| | |
|-|-|
| Signature   | hs.mouse.getButtons() -> table  |
| Type        | Function |
| Description | Returns a table containing the current mouse buttons being pressed *at this instant*. |
| Parameters |  None | | Returns |  * Returns an array containing indicies starting from 1 up to the highest numbered button currently being pressed where the index is `true` if the button is currently pressed or `false` if it is not. * Special hash tag synonyms for `left` (button 1), `right` (button 2), and `middle` (button 3) are also set to true if these buttons are currently being pressed. | | Notes |  * This function is a wrapper to `hs.eventtap.checkMouseButtons` * This is an instantaneous poll of the current mouse buttons, not a callback. | 
#### [getCurrentScreen](#getCurrentScreen)
| | |
|-|-|
| Signature   | hs.mouse.getCurrentScreen() -> screen or nil  |
| Type        | Function |
| Description | Gets the screen the mouse pointer is on |
| Parameters |  * None | | Returns |  * An `hs.screen` object that the mouse pointer is on, or nil if an error occurred | 
#### [getRelativePosition](#getRelativePosition)
| | |
|-|-|
| Signature   | hs.mouse.getRelativePosition() -> point or nil  |
| Type        | Function |
| Description | Gets the co-ordinates of the mouse pointer, relative to the screen it is on |
| Parameters |  * None | | Returns |  * A point-table containing the relative x and y co-ordinates of the mouse pointer, or nil if an error occured | | Notes |  * The co-ordinates returned by this function are relative to the top left pixel of the screen the mouse is on (see `hs.mouse.getAbsolutePosition` if you need the location in the full desktop space) | 
#### [setAbsolutePosition](#setAbsolutePosition)
| | |
|-|-|
| Signature   | hs.mouse.setAbsolutePosition(point)  |
| Type        | Function |
| Description | Sets the absolute co-ordinates of the mouse pointer |
| Parameters |  * point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to | | Returns |  * None | | Notes |  * The co-ordinates given to this function must be in relation to the full size of your desktop. See the notes for `hs.mouse.getAbsolutePosition` for more information | 
#### [setRelativePosition](#setRelativePosition)
| | |
|-|-|
| Signature   | hs.mouse.setRelativePosition(point[, screen])  |
| Type        | Function |
| Description | Sets the co-ordinates of the mouse pointer, relative to a screen |
| Parameters |  * point - A point-table containing the relative x and y co-ordinates to move the mouse pointer to * screen - An optional `hs.screen` object. Defaults to the screen the mouse pointer is currently on | | Returns |  * None | 
#### [trackingSpeed](#trackingSpeed)
| | |
|-|-|
| Signature   | hs.mouse.trackingSpeed([speed]) -> number  |
| Type        | Function |
| Description | Gets/Sets the current system mouse tracking speed setting |
| Parameters |  * speed - An optional number containing the new tracking speed to set. If this is ommitted, the current setting is returned | | Returns |  * A number (currently between 0.0 and 3.0) indicating the current tracking speed setting for mice, or -1 if an error occurred | | Notes |  * This is represented in the System Preferences as the "Tracking speed" setting for mice * Note that not all values will work, they should map to the steps defined in the System Preferences app | 