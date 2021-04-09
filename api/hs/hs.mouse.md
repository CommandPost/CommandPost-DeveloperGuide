# [docs](index.md) » hs.mouse
---

Inspect/manipulate the position of the mouse pointer

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

This module uses ManyMouse by Ryan C. Gordon.

MANYMOUSE LICENSE:

Copyright (c) 2005-2012 Ryan C. Gordon and others.

This software is provided 'as-is', without any express or implied warranty.
In no event will the authors be held liable for any damages arising from
the use of this software.

Permission is granted to anyone to use this software for any purpose,
including commercial applications, and to alter it and redistribute it
freely, subject to the following restrictions:

1. The origin of this software must not be misrepresented; you must not
claim that you wrote the original software. If you use this software in a
product, an acknowledgment in the product documentation would be
appreciated but is not required.

2. Altered source versions must be plainly marked as such, and must not be
misrepresented as being the original software.

3. This notice may not be removed or altered from any source distribution.

    Ryan C. Gordon <icculus@icculus.org>

## API Overview
* Functions - API calls offered directly by the extension
 * [absolutePosition](#absoluteposition)
 * [count](#count)
 * [getButtons](#getbuttons)
 * [getCurrentScreen](#getcurrentscreen)
 * [getRelativePosition](#getrelativeposition)
 * [names](#names)
 * [scrollDirection](#scrolldirection)
 * [setRelativePosition](#setrelativeposition)
 * [trackingSpeed](#trackingspeed)

## API Documentation

### Functions

#### [absolutePosition](#absoluteposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.absolutePosition([point]) -> point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get or set the absolute co-ordinates of the mouse pointer |
| **Parameters**                                       | <ul><li>An optional point table containing the absolute x and y co-ordinates to move the mouse pointer to</li></ul> |
| **Returns**                                          | <ul><li>A point table containing the absolute x and y co-ordinates of the mouse pointer</li></ul> |
| **Notes**                                            | <ul><li>If no parameters are supplied, the current position will be returned. If a point table parameter is supplied, the mouse pointer poisition will be set and the new co-ordinates returned</li></ul> |

#### [count](#count)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.count([includeInternal]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the total number of mice connected to your system. |
| **Parameters**                                       | <ul><li>includeInternal - A boolean which sets whether or not you want to include internal Trackpad's in the count. Defaults to false.</li></ul> |
| **Returns**                                          | <ul><li>The number of mice connected to your system</li></ul> |
| **Notes**                                            | <ul><li>This function leverages code from <a href="http://icculus.org/manymouse/">ManyMouse</a>.</li><li>This function considers any mouse labelled as "Apple Internal Keyboard / Trackpad" to be an internal mouse.</li></ul> |

#### [getButtons](#getbuttons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getButtons() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the current mouse buttons being pressed *at this instant*. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns an array containing indicies starting from 1 up to the highest numbered button currently being pressed where the index is <code>true</code> if the button is currently pressed or <code>false</code> if it is not.</li><li>Special hash tag synonyms for <code>left</code> (button 1), <code>right</code> (button 2), and <code>middle</code> (button 3) are also set to true if these buttons are currently being pressed.</li></ul> |
| **Notes**                                            | <ul><li>This function is a wrapper to <code>hs.eventtap.checkMouseButtons</code></li><li>This is an instantaneous poll of the current mouse buttons, not a callback.</li></ul> |

#### [getCurrentScreen](#getcurrentscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getCurrentScreen() -> screen or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the screen the mouse pointer is on |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.screen</code> object that the mouse pointer is on, or nil if an error occurred</li></ul> |

#### [getRelativePosition](#getrelativeposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getRelativePosition() -> point or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the co-ordinates of the mouse pointer, relative to the screen it is on |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A point-table containing the relative x and y co-ordinates of the mouse pointer, or nil if an error occured</li></ul> |
| **Notes**                                            | <ul><li>The co-ordinates returned by this function are relative to the top left pixel of the screen the mouse is on (see <code>hs.mouse.getAbsolutePosition</code> if you need the location in the full desktop space)</li></ul> |

#### [names](#names)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.names() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the names of any mice connected to the system. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing strings of all the mice connected to the system.</li></ul> |
| **Notes**                                            | <ul><li>This function leverages code from <a href="http://icculus.org/manymouse/">ManyMouse</a>.</li></ul> |

#### [scrollDirection](#scrolldirection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.scrollDirection() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the system-wide direction of scolling |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string, either "natural" or "normal"</li></ul> |

#### [setRelativePosition](#setrelativeposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.setRelativePosition(point[, screen])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets the co-ordinates of the mouse pointer, relative to a screen |
| **Parameters**                                       | <ul><li>point - A point-table containing the relative x and y co-ordinates to move the mouse pointer to</li><li>screen - An optional <code>hs.screen</code> object. Defaults to the screen the mouse pointer is currently on</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [trackingSpeed](#trackingspeed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.trackingSpeed([speed]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets/Sets the current system mouse tracking speed setting |
| **Parameters**                                       | <ul><li>speed - An optional number containing the new tracking speed to set. If this is ommitted, the current setting is returned</li></ul> |
| **Returns**                                          | <ul><li>A number indicating the current tracking speed setting for mice</li></ul> |
| **Notes**                                            | <ul><li>This is represented in the System Preferences as the "Tracking speed" setting for mice</li><li>Note that not all values will work, they should map to the steps defined in the System Preferences app, which are:</li><li>0.0, 0.125, 0.5, 0.6875, 0.875, 1.0, 1.5, 2.0, 2.5, 3.0</li><li>Note that changes to this value will not be noticed immedaitely by macOS</li></ul> |

