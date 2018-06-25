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
 * [scrollDirection](#scrolldirection)
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
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A point-table containing the absolute x and y co-ordinates of the mouse pointer</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The co-ordinates returned by this function are in relation to the full size of your desktop. If you have multiple monitors, the desktop is a large virtual rectangle that contains them all (e.g. if you have two 1920x1080 monitors and the mouse is in the middle of the second monitor, the returned table would be <code>{ x=2879, y=540 }</code>) * Multiple monitors of different sizes can cause the co-ordinates of some areas of the desktop to be negative. This is perfectly normal. 0,0 in the co-ordinates of the desktop is the top left of the primary monitor</li><br /></ul>                                             |

#### [getButtons](#getbuttons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getButtons() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table containing the current mouse buttons being pressed *at this instant*.                                                                                         |
| **Parameters**                                       | <p>None</p>                                        |
| **Returns**                                          | <ul><br /><li>Returns an array containing indicies starting from 1 up to the highest numbered button currently being pressed where the index is <code>true</code> if the button is currently pressed or <code>false</code> if it is not. * Special hash tag synonyms for <code>left</code> (button 1), <code>right</code> (button 2), and <code>middle</code> (button 3) are also set to true if these buttons are currently being pressed.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This function is a wrapper to <code>hs.eventtap.checkMouseButtons</code> * This is an instantaneous poll of the current mouse buttons, not a callback.</li><br /></ul>                                             |

#### [getCurrentScreen](#getcurrentscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getCurrentScreen() -> screen or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the screen the mouse pointer is on                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object that the mouse pointer is on, or nil if an error occurred</li><br /></ul>                                           |

#### [getRelativePosition](#getrelativeposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.getRelativePosition() -> point or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the co-ordinates of the mouse pointer, relative to the screen it is on                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A point-table containing the relative x and y co-ordinates of the mouse pointer, or nil if an error occured</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The co-ordinates returned by this function are relative to the top left pixel of the screen the mouse is on (see <code>hs.mouse.getAbsolutePosition</code> if you need the location in the full desktop space)</li><br /></ul>                                             |

#### [scrollDirection](#scrolldirection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.scrollDirection() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the system-wide direction of scolling                                                                                         |
| **Returns**                                          | <ul><br /><li>A string, either "natural" or "normal"</li><br /></ul>                                           |

#### [setAbsolutePosition](#setabsoluteposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.setAbsolutePosition(point)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the absolute co-ordinates of the mouse pointer                                                                                         |
| **Parameters**                                       | <ul><br /><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The co-ordinates given to this function must be in relation to the full size of your desktop. See the notes for <code>hs.mouse.getAbsolutePosition</code> for more information</li><br /></ul>                                             |

#### [setRelativePosition](#setrelativeposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.setRelativePosition(point[, screen])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the co-ordinates of the mouse pointer, relative to a screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>point - A point-table containing the relative x and y co-ordinates to move the mouse pointer to * screen - An optional <code>hs.screen</code> object. Defaults to the screen the mouse pointer is currently on</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [trackingSpeed](#trackingspeed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.mouse.trackingSpeed([speed]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets/Sets the current system mouse tracking speed setting                                                                                         |
| **Parameters**                                       | <ul><br /><li>speed - An optional number containing the new tracking speed to set. If this is ommitted, the current setting is returned</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A number (currently between 0.0 and 3.0) indicating the current tracking speed setting for mice, or -1 if an error occurred</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This is represented in the System Preferences as the "Tracking speed" setting for mice * Note that not all values will work, they should map to the steps defined in the System Preferences app</li><br /></ul>                                             |

