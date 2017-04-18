# [docs](index.md) » hs.mouse
---

Inspect/manipulate the position of the mouse pointer

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Functions - API calls offered directly by the extension
 * [getAbsolutePosition](#getabsoluteposition)
 * [getButtons](#getbuttons)
 * [getCurrentScreen](#getcurrentscreen)
 * [getRelativePosition](#getrelativeposition)
 * [setAbsolutePosition](#setabsoluteposition)
 * [setRelativePosition](#setrelativeposition)
 * [trackingSpeed](#trackingspeed)

## API Documentation

### Functions

#### [getAbsolutePosition](#getabsoluteposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getAbsolutePosition() -> point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the absolute co-ordinates of the mouse pointer                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A point-table containing the absolute x and y co-ordinates of the mouse pointer</li></ul>          |
| **Notes**                                            | <ul><li>The co-ordinates returned by this function are in relation to the full size of your desktop. If you have multiple monitors, the desktop is a large virtual rectangle that contains them all (e.g. if you have two 1920x1080 monitors and the mouse is in the middle of the second monitor, the returned table would be `{ x=2879, y=540 }`)</li><li>Multiple monitors of different sizes can cause the co-ordinates of some areas of the desktop to be negative. This is perfectly normal. 0,0 in the co-ordinates of the desktop is the top left of the primary monitor</li></ul>                |

#### [getButtons](#getbuttons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getButtons() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table containing the current mouse buttons being pressed *at this instant*.                                                                                         |
| **Parameters**                                       | <ul><li> None</li></ul> |
| **Returns**                                          | <ul><li>Returns an array containing indicies starting from 1 up to the highest numbered button currently being pressed where the index is `true` if the button is currently pressed or `false` if it is not.</li><li>Special hash tag synonyms for `left` (button 1), `right` (button 2), and `middle` (button 3) are also set to true if these buttons are currently being pressed.</li></ul>          |
| **Notes**                                            | <ul><li>This function is a wrapper to `hs.eventtap.checkMouseButtons`</li><li>This is an instantaneous poll of the current mouse buttons, not a callback.</li></ul>                |

#### [getCurrentScreen](#getcurrentscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getCurrentScreen() -> screen or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the screen the mouse pointer is on                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `hs.screen` object that the mouse pointer is on, or nil if an error occurred</li></ul>          |

#### [getRelativePosition](#getrelativeposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getRelativePosition() -> point or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the co-ordinates of the mouse pointer, relative to the screen it is on                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A point-table containing the relative x and y co-ordinates of the mouse pointer, or nil if an error occured</li></ul>          |
| **Notes**                                            | <ul><li>The co-ordinates returned by this function are relative to the top left pixel of the screen the mouse is on (see `hs.mouse.getAbsolutePosition` if you need the location in the full desktop space)</li></ul>                |

#### [setAbsolutePosition](#setabsoluteposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.setAbsolutePosition(point)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the absolute co-ordinates of the mouse pointer                                                                                         |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>The co-ordinates given to this function must be in relation to the full size of your desktop. See the notes for `hs.mouse.getAbsolutePosition` for more information</li></ul>                |

#### [setRelativePosition](#setrelativeposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.setRelativePosition(point[, screen])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the co-ordinates of the mouse pointer, relative to a screen                                                                                         |
| **Parameters**                                       | <ul><li>point - A point-table containing the relative x and y co-ordinates to move the mouse pointer to</li><li>screen - An optional `hs.screen` object. Defaults to the screen the mouse pointer is currently on</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [trackingSpeed](#trackingspeed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.trackingSpeed([speed]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets/Sets the current system mouse tracking speed setting                                                                                         |
| **Parameters**                                       | <ul><li>speed - An optional number containing the new tracking speed to set. If this is ommitted, the current setting is returned</li></ul> |
| **Returns**                                          | <ul><li>A number (currently between 0.0 and 3.0) indicating the current tracking speed setting for mice, or -1 if an error occurred</li></ul>          |
| **Notes**                                            | <ul><li>This is represented in the System Preferences as the "Tracking speed" setting for mice</li><li>Note that not all values will work, they should map to the steps defined in the System Preferences app</li></ul>                |

