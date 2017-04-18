# [docs](index.md) » hs.canvas
---

A different approach to drawing in Hammerspoon

`hs.drawing` approaches graphical images as independant primitives, each "shape" being a separate drawing object based on the core primitives: ellipse, rectangle, point, line, text, etc.  This model works well with graphical elements that are expected to be managed individually and don't have complex clipping interactions, but does not scale well when more complex combinations or groups of drawing elements need to be moved or manipulated as a group, and only allows for simple inclusionary clipping regions.

This module works by designating a canvas and then assigning a series of graphical primitives to the canvas.  Included in this assignment list are rules about how the individual elements interact with each other within the canvas (compositing and clipping rules), and direct modification of the canvas itself (move, resize, etc.) causes all of the assigned elements to be adjusted as a group.

The canvas elements are defined in an array, and each entry of the array is a table of key-value pairs describing the element at that position.  Elements are rendered in the order in which they are assigned to the array (i.e. element 1 is drawn before element 2, etc.).

Attributes for canvas elements are defined in [hs.canvas.attributes](#attributes). All canvas elements require the `type` field; all other attributes have default values.  Fields required to properly define the element (for example, `frame` for the `rectangle` element type) will be copied into the element definition with their default values if they are not specified at the time of creation. Optional attributes will only be assigned in the element definition if they are specified.  When the module requires the value for an element's attribute it first checks the element definition itself, then the defaults are looked for in the canvas defaults, and then finally in the module's built in defaults (specified in the descriptions below).

Some examples of how to use this module can be found at https://github.com/asmagill/hammerspoon/wiki/hs.canvas.examples

If you wish to test out the `hs.drawing` wrapper which may eventually replace the original `hs.drawing` module entirely, check out [hs.canvas.drawingWrapper](#drawingWrapper).

## Submodules
 * [hs.canvas.drawing](hs.canvas.drawing.md)
 * [hs.canvas.matrix](hs.canvas.matrix.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [compositeTypes[]](#compositetypes[])
 * [windowBehaviors[]](#windowbehaviors[])
 * [windowLevels](#windowlevels)
* Functions - API calls offered directly by the extension
 * [defaultTextStyle](#defaulttextstyle)
 * [disableScreenUpdates](#disablescreenupdates)
 * [elementSpec](#elementspec)
 * [enableScreenUpdates](#enablescreenupdates)
 * [help](#help)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be access from an object returned by a constructor
 * [attributes](#attributes)
 * [object[index]](#object[index])
 * [percentages](#percentages)
* Methods - API calls which can only be made on an object returned by a constructor
 * [alpha](#alpha)
 * [appendElements](#appendelements)
 * [assignElement](#assignelement)
 * [behavior](#behavior)
 * [behaviorAsLabels](#behavioraslabels)
 * [bringToFront](#bringtofront)
 * [canvasDefaultFor](#canvasdefaultfor)
 * [canvasDefaultKeys](#canvasdefaultkeys)
 * [canvasDefaults](#canvasdefaults)
 * [canvasElements](#canvaselements)
 * [canvasMouseEvents](#canvasmouseevents)
 * [clickActivating](#clickactivating)
 * [copy](#copy)
 * [delete](#delete)
 * [elementAttribute](#elementattribute)
 * [elementBounds](#elementbounds)
 * [elementCount](#elementcount)
 * [elementKeys](#elementkeys)
 * [frame](#frame)
 * [hide](#hide)
 * [imageFromCanvas](#imagefromcanvas)
 * [insertElement](#insertelement)
 * [isOccluded](#isoccluded)
 * [isShowing](#isshowing)
 * [isVisible](#isvisible)
 * [level](#level)
 * [minimumTextSize](#minimumtextsize)
 * [mouseCallback](#mousecallback)
 * [orderAbove](#orderabove)
 * [orderBelow](#orderbelow)
 * [removeElement](#removeelement)
 * [replaceElements](#replaceelements)
 * [rotateElement](#rotateelement)
 * [sendToBack](#sendtoback)
 * [show](#show)
 * [size](#size)
 * [topLeft](#topleft)
 * [transformation](#transformation)
 * [wantsLayer](#wantslayer)

## API Documentation

### Constants

#### [compositeTypes[]](#compositetypes[])
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.compositeTypes[]` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the possible compositing rules for elements within the canvas.                                                                                         |

#### [windowBehaviors[]](#windowbehaviors[])
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.windowBehaviors[]` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Array of window behavior labels for determining how a canvas or drawing object is handled in Spaces and Exposé                                                                                         |

#### [windowLevels](#windowlevels)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.windowLevels` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table of predefined window levels usable with [hs.canvas:level](#level)                                                                                         |
| **Notes**                                            | <ul><li>These key names map to the constants used in CoreGraphics to specify window levels and may not actually be used for what the name might suggest. For example, tests suggest that an active screen saver actually runs at a level of 2002, rather than at 1000, which is the window level corresponding to kCGScreenSaverWindowLevelKey.</li><li>Each window level is sorted separately and [hs.canvas:orderAbove](#orderAbove) and [hs.canvas:orderBelow](#orderBelow) only arrange windows within the same level.</li><li>If you use Dock hiding (or in 10.11, Menubar hiding) please note that when the Dock (or Menubar) is popped up, it is done so with an implicit orderAbove, which will place it above any items you may also draw at the Dock (or MainMenu) level.</li></ul>                |

### Functions

#### [defaultTextStyle](#defaulttextstyle)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.defaultTextStyle() -> `hs.styledtext` attributes table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table containing the default font, size, color, and paragraphStyle used by `hs.canvas` for text drawing objects.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table containing the default style attributes `hs.canvas` uses for text drawing objects in the `hs.styledtext` attributes table format.</li></ul>          |
| **Notes**                                            | <ul><li>This method is intended to be used in conjunction with `hs.styledtext` to create styledtext objects that are based on, or a slight variation of, the defaults used by `hs.canvas`.</li></ul>                |

#### [disableScreenUpdates](#disablescreenupdates)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.disableScreenUpdates() -> None` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Tells the OS X window server to pause updating the physical displays for a short while.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>This method can be used to allow multiple changes which are being made to the users display appear as if they all occur simultaneously by holding off on updating the screen on the regular schedule.</li><li>This method should always be balanced with a call to [hs.canvas.enableScreenUpdates](#enableScreenUpdates) when your updates have been completed.  Failure to do so will be logged in the system logs.</li></ul>                |

#### [elementSpec](#elementspec)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.elementSpec() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the list of attributes and their specifications that are recognized for canvas elements by this module.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the attributes and specifications defined for this module.</li></ul>          |
| **Notes**                                            | <ul><li>This is primarily for debugging purposes and may be removed in the future.</li></ul>                |

#### [enableScreenUpdates](#enablescreenupdates)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.enableScreenUpdates() -> None` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Tells the OS X window server to resume updating the physical displays after a previous pause.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>In conjunction with [hs.canvas.disableScreenUpdates](#disableScreenUpdates), this method can be used to allow multiple changes which are being made to the users display appear as if they all occur simultaneously by holding off on updating the screen on the regular schedule.</li><li>This method should always be preceded by a call to [hs.canvas.disableScreenUpdates](#disableScreenUpdates).  Failure to do so will be logged in the system logs.</li></ul>                |

#### [help](#help)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.help([attribute]) -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Provides specification information for the recognized attributes, or the specific attribute specified.                                                                                         |
| **Parameters**                                       | <ul><li>`attribute` - an optional string specifying an element attribute. If this argument is not provided, all attributes are listed.</li></ul> |
| **Returns**                                          | <ul><li>a string containing some of the information provided by the [hs.canvas.elementSpec](#elementSpec) in a manner that is easy to reference from the Hammerspoon console.</li></ul>          |

### Constructors

#### [new](#new)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.new(rect) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Create a new canvas object at the specified coordinates                                                                                         |
| **Parameters**                                       | <ul><li>`rect` - A rect-table containing the co-ordinates and size for the canvas object</li></ul> |
| **Returns**                                          | <ul><li>a new, empty, canvas object, or nil if the canvas cannot be created with the specified coordinates</li></ul>          |
| **Notes**                                            | <ul><li>The size of the canvas defines the visible area of the canvas -- any portion of a canvas element which extends past the canvas's edges will be clipped.</li><li>a rect-table is a table with key-value pairs specifying the top-left coordinate on the screen for the canvas (keys `x`  and `y`) and the size (keys `h` and `w`) of the canvas. The table may be crafted by any method which includes these keys, including the use of an `hs.geometry` object.</li></ul>                |

### Fields

#### [attributes](#attributes)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.attributes` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Canvas Element Attributes                                                                                         |

#### [object[index]](#object[index])
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.object[index]` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | An array-like method for accessing the attributes for the canvas element at the specified index                                                                                         |

#### [percentages](#percentages)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas.percentages` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Canvas attributes which specify the location and size of canvas elements can be specified with an absolute position or as a percentage of the canvas size.                                                                                         |

### Methods

#### [alpha](#alpha)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:alpha([alpha]) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the alpha level of the window containing the canvasObject.                                                                                         |
| **Parameters**                                       | <ul><li>`alpha` - an optional number specifying the new alpha level (0.0 - 1.0, inclusive) for the canvasObject</li></ul> |
| **Returns**                                          | <ul><li>If an argument is provided, the canvas object; otherwise the current value.</li></ul>          |

#### [appendElements](#appendelements)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:appendElements(element, ...) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Appends the elements specified to the canvas.                                                                                         |
| **Parameters**                                       | <ul><li>`element` - a table containing key-value pairs that define the element to be appended to the canvas.  You can specify one or more elements and they will be appended in the order they are listed.</li></ul> |
| **Returns**                                          | <ul><li>the canvas object</li></ul>          |
| **Notes**                                            | <ul><li>You can also specify multiple elements in a table as an array, where each index in the table contains an element table, and use the array as a single argument to this method if this style works better in your code.</li></ul>                |

#### [assignElement](#assignelement)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:assignElement(elementTable, [index]) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Assigns a new element to the canvas at the specified index.                                                                                         |
| **Parameters**                                       | <ul><li>`elementTable` - a table containing key-value pairs that define the element to be added to the canvas.</li><li>`index`        - an optional integer between 1 and the canvas element count + 1 specifying the index position to put the new element.  Any element currently at that index will be replaced.  Defaults to the canvas element count + 1 (i.e. after the end of the currently defined elements).</li></ul> |
| **Returns**                                          | <ul><li>the canvasObject</li></ul>          |
| **Notes**                                            | <ul><li>When the index specified is the canvas element count + 1, the behavior of this method is the same as [hs.canvas:insertElement](#insertElement); i.e. it adds the new element to the end of the currently defined element list.</li></ul>                |

#### [behavior](#behavior)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:behavior([behavior]) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the window behavior settings for the canvas object using labels defined in [hs.canvas.windowBehaviors](#windowBehaviors).                                                                                         |
| **Parameters**                                       | <ul><li>`behavior` - if present, the behavior should be a combination of values found in [hs.canvas.windowBehaviors](#windowBehaviors) describing the window behavior.  The behavior should be specified as one of the following:</li><li>  integer - a number representing the behavior which can be created by combining values found in [hs.canvas.windowBehaviors](#windowBehaviors) with the logical or operator.</li><li>  string  - a single key from [hs.canvas.windowBehaviors](#windowBehaviors) which will be toggled in the current window behavior.</li><li>  table   - a list of keys from [hs.canvas.windowBehaviors](#windowBehaviors) which will be combined to make the final behavior by combining their values with the logical or operator.</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, then the canvasObject is returned; otherwise the current behavior value is returned.</li></ul>          |

#### [behaviorAsLabels](#behavioraslabels)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:behaviorAsLabels(behaviorTable) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the window behavior settings for the canvas object using labels defined in [hs.canvas.windowBehaviors](#windowBehaviors).                                                                                         |
| **Parameters**                                       | <ul><li>behaviorTable - an optional table of strings and/or integers specifying the desired window behavior for the canvas object.</li></ul> |
| **Returns**                                          | <ul><li>If an argument is provided, the canvas object; otherwise the current value as a table of strings.</li></ul>          |

#### [bringToFront](#bringtofront)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:bringToFront([aboveEverything]) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Places the canvas object on top of normal windows                                                                                         |
| **Parameters**                                       | <ul><li>aboveEverything - An optional boolean value that controls how far to the front the canvas should be placed. Defaults to false.</li><li>  if true, place the canvas on top of all windows (including the dock and menubar and fullscreen windows).</li><li>  if false, place the canvas above normal windows, but below the dock, menubar and fullscreen windows.</li></ul> |
| **Returns**                                          | <ul><li>The canvas object</li></ul>          |

#### [canvasDefaultFor](#canvasdefaultfor)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:canvasDefaultFor(keyName, [newValue]) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the element default specified by keyName.                                                                                         |
| **Returns**                                          | <ul><li>If an argument is provided, the canvas object; otherwise the current value.</li></ul>          |
| **Notes**                                            | <ul><li>Not all keys will apply to all element types.</li><li>Currently set and built-in defaults may be retrieved in a table with [hs.canvas:canvasDefaults](#canvasDefaults).</li></ul>                |

#### [canvasDefaultKeys](#canvasdefaultkeys)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:canvasDefaultKeys([module]) -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a list of the key names for the attributes set for the canvas defaults.                                                                                         |
| **Parameters**                                       | <ul><li>`module` - an optional boolean flag, default false, indicating whether the key names for the module defaults (true) should be included in the list.  If false, only those defaults which have been explicitly set for the canvas are included.</li></ul> |
| **Returns**                                          | <ul><li>a table containing the key names for the defaults which are set for this canvas. May also optionally include key names for all attributes which have a default value defined by the module.</li></ul>          |

#### [canvasDefaults](#canvasdefaults)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:canvasDefaults([module]) -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get a table of the default key-value pairs which apply to the canvas.                                                                                         |
| **Parameters**                                       | <ul><li>`module` - an optional boolean flag, default false, indicating whether module defaults (true) should be included in the table.  If false, only those defaults which have been explicitly set for the canvas are returned.</li></ul> |
| **Returns**                                          | <ul><li>a table containing key-value pairs for the defaults which apply to the canvas.</li></ul>          |
| **Notes**                                            | <ul><li>Not all keys will apply to all element types.</li><li>To change the defaults for the canvas, use [hs.canvas:canvasDefaultFor](#canvasDefaultFor).</li></ul>                |

#### [canvasElements](#canvaselements)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:canvasElements() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an array containing the elements defined for this canvas.  Each array entry will be a table containing the key-value pairs which have been set for that canvas element.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an array of element tables which are defined for the canvas.</li></ul>          |

#### [canvasMouseEvents](#canvasmouseevents)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:canvasMouseEvents([down], [up], [enterExit], [move]) -> canvasObject | current values` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set whether or not regions of the canvas which are not otherwise covered by an element with mouse tracking enabled should generate a callback for mouse events.                                                                                         |
| **Parameters**                                       | <ul><li>`down`      - an optional boolean, or nil placeholder, specifying whether or not the mouse button being pushed down should generate a callback for the canvas areas not otherwise covered by an element with mouse tracking enabled.</li><li>`up`        - an optional boolean, or nil placeholder, specifying whether or not the mouse button being released should generate a callback for the canvas areas not otherwise covered by an element with mouse tracking enabled.</li><li>`enterExit` - an optional boolean, or nil placeholder, specifying whether or not the mouse pointer entering or exiting the canvas bounds should generate a callback for the canvas areas not otherwise covered by an element with mouse tracking enabled.</li><li>`move`      - an optional boolean, or nil placeholder, specifying whether or not the mouse pointer moving within the canvas bounds should generate a callback for the canvas areas not otherwise covered by an element with mouse tracking enabled.</li></ul> |
| **Returns**                                          | <ul><li>If any arguments are provided, returns the canvas Object, otherwise returns the current values as four separate boolean values (i.e. not in a table).</li></ul>          |
| **Notes**                                            | <ul><li>Each value that you wish to set must be provided in the order given above, but you may specify a position as `nil` to indicate that whatever it's current state, no change should be applied.  For example, to activate a callback for entering and exiting the canvas without changing the current callback status for up or down button clicks, you could use: `hs.canvas:canvasMouseTracking(nil, nil, true)`.</li></ul>                |

#### [clickActivating](#clickactivating)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:clickActivating([flag]) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set whether or not clicking on a canvas with a click callback defined should bring all of Hammerspoon's open windows to the front.                                                                                         |
| **Parameters**                                       | <ul><li>`flag` - an optional boolean indicating whether or not clicking on a canvas with a click callback function defined should activate Hammerspoon and bring its windows forward. Defaults to true.</li></ul> |
| **Returns**                                          | <ul><li>If an argument is provided, returns the canvas object; otherwise returns the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>Setting this to false changes a canvas object's AXsubrole value and may affect the results of filters used with `hs.window.filter`, depending upon how they are defined.</li></ul>                |

#### [copy](#copy)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:copy() -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a copy of the canvas.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a copy of the canvas</li></ul>          |
| **Notes**                                            | <ul><li>The copy of the canvas will be identical in all respectes except:</li><li>  The new canvas will not have a callback function assigned, even if the original canvas does.</li><li>  The new canvas will not initially be visible, even if the original is.</li><li>The new canvas is an independant entity -- any subsequent changes to either canvas will not be reflected in the other canvas.</li></ul>                |

#### [delete](#delete)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:delete([fadeOutTime]) -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Destroys the canvas object, optionally fading it out first (if currently visible).                                                                                         |
| **Parameters**                                       | <ul><li>`fadeOutTime` - An optional number of seconds over which to fade out the canvas object. Defaults to zero.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>This method is automatically called during garbage collection, notably during a Hammerspoon termination or reload, with a fade time of 0.</li></ul>                |

#### [elementAttribute](#elementattribute)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:elementAttribute(index, key, [value]) -> canvasObject | current value` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the attribute `key` for the canvas element at the specified index.                                                                                         |
| **Parameters**                                       | <ul><li>`index` - the index of the canvas element whose attribute is to be retrieved or set.</li><li>`key`   - the key name of the attribute to get or set.</li><li>`value` - an optional value to assign to the canvas element's attribute.</li></ul> |
| **Returns**                                          | <ul><li>if a value for the attribute is specified, returns the canvas object; otherwise returns the current value for the specified attribute.</li></ul>          |

#### [elementBounds](#elementbounds)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:elementBounds(index) -> rectTable` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the smallest rectangle which can fully contain the canvas element at the specified index.                                                                                         |
| **Parameters**                                       | <ul><li>`index` - the index of the canvas element to get the bounds for</li></ul> |
| **Returns**                                          | <ul><li>a rect table containing the smallest rectangle which can fully contain the canvas element.</li></ul>          |
| **Notes**                                            | <ul><li>For many elements, this will be the same as the element frame.  For items without a frame (e.g. `segments`, `circle`, etc.) this will be the smallest rectangle which can fully contain the canvas element as specified by it's attributes.</li></ul>                |

#### [elementCount](#elementcount)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:elementCount() -> integer` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the number of elements currently defined for the canvas object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the number of elements currently defined for the canvas object.</li></ul>          |

#### [elementKeys](#elementkeys)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:elementKeys(index, [optional]) -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a list of the key names for the attributes set for the canvas element at the specified index.                                                                                         |
| **Parameters**                                       | <ul><li>`index`    - the index of the element to get the assigned key list from.</li><li>`optional` - an optional boolean, default false, indicating whether optional, but unset, keys relevant to this canvas object should also be included in the list returned.</li></ul> |
| **Returns**                                          | <ul><li>a table containing the keys that are set for this canvas element.  May also optionally include keys which are not specifically set for this element but use inherited values from the canvas or module defaults.</li></ul>          |
| **Notes**                                            | <ul><li>Any attribute which has been explicitly set for the element will be included in the key list (even if it is ignored for the element type).  If the `optional` flag is set to true, the *additional* attribute names added to the list will only include those which are relevant to the element type.</li></ul>                |

#### [frame](#frame)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:frame([rect]) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the frame of the canvasObject.                                                                                         |
| **Parameters**                                       | <ul><li>rect - An optional rect-table containing the co-ordinates and size the canvas object should be moved and set to</li></ul> |
| **Returns**                                          | <ul><li>If an argument is provided, the canvas object; otherwise the current value.</li></ul>          |
| **Notes**                                            | <ul><li>a rect-table is a table with key-value pairs specifying the new top-left coordinate on the screen of the canvas (keys `x`  and `y`) and the new size (keys `h` and `w`).  The table may be crafted by any method which includes these keys, including the use of an `hs.geometry` object.</li></ul>                |

#### [hide](#hide)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:hide([fadeOutTime]) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the canvas object                                                                                         |
| **Parameters**                                       | <ul><li>`fadeOutTime` - An optional number of seconds over which to fade out the canvas object. Defaults to zero.</li></ul> |
| **Returns**                                          | <ul><li>The canvas object</li></ul>          |

#### [imageFromCanvas](#imagefromcanvas)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:imageFromCanvas() -> hs.image object` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an image of the canvas contents as an `hs.image` object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an `hs.image` object</li></ul>          |
| **Notes**                                            | <ul><li>The canvas does not have to be visible in order for an image to be generated from it.</li></ul>                |

#### [insertElement](#insertelement)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:insertElement(elementTable, [index]) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Insert a new element into the canvas at the specified index.                                                                                         |
| **Parameters**                                       | <ul><li>`elementTable` - a table containing key-value pairs that define the element to be added to the canvas.</li><li>`index`        - an optional integer between 1 and the canvas element count + 1 specifying the index position to put the new element.  Any element currently at that index, and those that follow, will be moved one position up in the element array.  Defaults to the canvas element count + 1 (i.e. after the end of the currently defined elements).</li></ul> |
| **Returns**                                          | <ul><li>the canvasObject</li></ul>          |
| **Notes**                                            | <ul><li>see also [hs.canvas:assignElement](#assignElement).</li></ul>                |

#### [isOccluded](#isoccluded)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:isOccluded() -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the canvas is currently occluded (hidden by other windows, off screen, etc).                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a boolean indicating whether or not the canvas is currently being occluded.</li></ul>          |
| **Notes**                                            | <ul><li>If any part of the canvas is visible (even if that portion of the canvas does not contain any canvas elements), then the canvas is not considered occluded.</li><li>a canvas which is completely covered by one or more opaque windows is considered occluded; however, if the windows covering the canvas are not opaque, then the canvas is not occluded.</li><li>a canvas that is currently hidden or with a height of 0 or a width of 0 is considered occluded.</li><li>See also [hs.canvas:isShowing](#isShowing).</li></ul>                |

#### [isShowing](#isshowing)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:isShowing() -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the canvas is currently being shown.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a boolean indicating whether or not the canvas is currently being shown (true) or is currently hidden (false).</li></ul>          |
| **Notes**                                            | <ul><li>This method only determines whether or not the canvas is being shown or is hidden -- it does not indicate whether or not the canvas is currently off screen or is occluded by other objects.</li><li>See also [hs.canvas:isOccluded](#isOccluded).</li></ul>                |

#### [isVisible](#isvisible)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:isVisible() -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the canvas is currently showing and is (at least partially) visible on screen.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a boolean indicating whether or not the canvas is currently visible.</li></ul>          |
| **Notes**                                            | <ul><li>This is syntactic sugar for `not hs.canvas:isOccluded()`.</li><li>See [hs.canvas:isOccluded](#isOccluded) for more details.</li></ul>                |

#### [level](#level)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:level([level]) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the window level more precisely than sendToBack and bringToFront.                                                                                         |
| **Parameters**                                       | <ul><li>`level` - an optional level, specified as a number or as a string, specifying the new window level for the canvasObject. If it is a string, it must match one of the keys in [hs.canvas.windowLevels](#windowLevels).</li></ul> |
| **Returns**                                          | <ul><li>If an argument is provided, the canvas object; otherwise the current value.</li></ul>          |

#### [minimumTextSize](#minimumtextsize)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:minimumTextSize([index], text) -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table specifying the size of the rectangle which can fully render the text with the specified style so that is will be completely visible.                                                                                         |
| **Parameters**                                       | <ul><li>`index` - an optional index specifying the element in the canvas which contains the text attributes which should be used when determining the size of the text. If not provided, the canvas defaults will be used instead. Ignored if `text` is an hs.styledtext object.</li><li>`text`  - a string or hs.styledtext object specifying the text.</li></ul> |
| **Returns**                                          | <ul><li>a size table specifying the height and width of a rectangle which could fully contain the text when displayed in the canvas</li></ul>          |
| **Notes**                                            | <ul><li>Multi-line text (separated by a newline or return) is supported.  The height will be for the multiple lines and the width returned will be for the longest line.</li></ul>                |

#### [mouseCallback](#mousecallback)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:mouseCallback(mouseCallbackFn) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets a callback for mouse events with respect to the canvas                                                                                         |
| **Parameters**                                       | <ul><li>`mouseCallbackFn`   - A function, can be nil, that will be called when a mouse event occurs within the canvas, and an element beneath the mouse's current position has one of the `trackMouse...` attributes set to true.</li></ul> |
| **Returns**                                          | <ul><li>The canvas object</li></ul>          |
| **Notes**                                            | <ul><li>The callback function should expect 5 arguments: the canvas object itself, a message specifying the type of mouse event, the canvas element `id` (or index position in the canvas if the `id` attribute is not set for the element), the x position of the mouse when the event was triggered within the rendered portion of the canvas element, and the y position of the mouse when the event was triggered within the rendered portion of the canvas element.</li><li>See also [hs.canvas:canvasMouseEvents](#canvasMouseEvents) for tracking mouse events in regions of the canvas not covered by an element with mouse tracking enabled.</li></ul>                |

#### [orderAbove](#orderabove)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:orderAbove([canvas2]) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves canvas object above canvas2, or all canvas objects in the same presentation level, if canvas2 is not given.                                                                                         |
| **Parameters**                                       | <ul><li>`canvas2` -An optional canvas object to place the canvas object above.</li></ul> |
| **Returns**                                          | <ul><li>The canvas object</li></ul>          |
| **Notes**                                            | <ul><li>If the canvas object and canvas2 are not at the same presentation level, this method will will move the canvas object as close to the desired relationship as possible without changing the canvas object's presentation level. See [hs.canvas.level](#level).</li></ul>                |

#### [orderBelow](#orderbelow)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:orderBelow([canvas2]) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves canvas object below canvas2, or all canvas objects in the same presentation level, if canvas2 is not given.                                                                                         |
| **Parameters**                                       | <ul><li>`canvas2` -An optional canvas object to place the canvas object below.</li></ul> |
| **Returns**                                          | <ul><li>The canvas object</li></ul>          |
| **Notes**                                            | <ul><li>If the canvas object and canvas2 are not at the same presentation level, this method will will move the canvas object as close to the desired relationship as possible without changing the canvas object's presentation level. See [hs.canvas.level](#level).</li></ul>                |

#### [removeElement](#removeelement)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:removeElement([index]) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Insert a new element into the canvas at the specified index.                                                                                         |
| **Parameters**                                       | <ul><li>`index`        - an optional integer between 1 and the canvas element count specifying the index of the canvas element to remove. Any elements that follow, will be moved one position down in the element array.  Defaults to the canvas element count (i.e. the last element of the currently defined elements).</li></ul> |
| **Returns**                                          | <ul><li>the canvasObject</li></ul>          |

#### [replaceElements](#replaceelements)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:replaceElements(element, ...) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Replaces all of the elements in the canvas with the elements specified.  Shortens or lengthens the canvas element count if necessary to accomodate the new canvas elements.                                                                                         |
| **Parameters**                                       | <ul><li>`element` - a table containing key-value pairs that define the element to be assigned to the canvas.  You can specify one or more elements and they will be appended in the order they are listed.</li></ul> |
| **Returns**                                          | <ul><li>the canvas object</li></ul>          |
| **Notes**                                            | <ul><li>You can also specify multiple elements in a table as an array, where each index in the table contains an element table, and use the array as a single argument to this method if this style works better in your code.</li></ul>                |

#### [rotateElement](#rotateelement)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:rotateElement(index, angle, [point], [append]) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Rotates an element about the point specified, or the elements center if no point is specified.                                                                                         |
| **Parameters**                                       | <ul><li>`index`  - the index of the element to rotate</li><li>`angle`  - the angle to rotate the object in a clockwise direction</li><li>`point`  - an optional point table, defaulting to the elements center, specifying the point around which the object should be rotated</li><li>`append` - an optional boolean, default false, specifying whether or not the rotation transformation matrix should be appended to the existing transformation assigned to the element (true) or replace it (false).</li></ul> |
| **Returns**                                          | <ul><li>the canvas object</li></ul>          |
| **Notes**                                            | <ul><li>a point-table is a table with key-value pairs specifying a coordinate in the canvas (keys `x`  and `y`). The table may be crafted by any method which includes these keys, including the use of an `hs.geometry` object.</li><li>The center of the object is determined by getting the element's bounds with [hs.canvas:elementBounds](#elementBounds).</li><li>If the third argument is a boolean value, the `point` argument is assumed to be the element's center and the boolean value is used as the `append` argument.</li></ul>                |

#### [sendToBack](#sendtoback)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:sendToBack() -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Places the canvas object behind normal windows, between the desktop wallpaper and desktop icons                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The canvas object</li></ul>          |

#### [show](#show)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:show([fadeInTime]) -> canvasObject` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Displays the canvas object                                                                                         |
| **Parameters**                                       | <ul><li>`fadeInTime` - An optional number of seconds over which to fade in the canvas object. Defaults to zero.</li></ul> |
| **Returns**                                          | <ul><li>The canvas object</li></ul>          |
| **Notes**                                            | <ul><li>if the canvas is in use as an element in another canvas, this method will result in an error.</li></ul>                |

#### [size](#size)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:size([size]) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the size of a canvas object                                                                                         |
| **Parameters**                                       | <ul><li>`size` - An optional size-table specifying the width and height the canvas object should be resized to</li></ul> |
| **Returns**                                          | <ul><li>If an argument is provided, the canvas object; otherwise the current value.</li></ul>          |
| **Notes**                                            | <ul><li>a size-table is a table with key-value pairs specifying the size (keys `h` and `w`) the canvas should be resized to. The table may be crafted by any method which includes these keys, including the use of an `hs.geometry` object.</li></ul>                |

#### [topLeft](#topleft)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:topLeft([point]) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the top-left coordinate of the canvas object                                                                                         |
| **Parameters**                                       | <ul><li>`point` - An optional point-table specifying the new coordinate the top-left of the canvas object should be moved to</li></ul> |
| **Returns**                                          | <ul><li>If an argument is provided, the canvas object; otherwise the current value.</li></ul>          |
| **Notes**                                            | <ul><li>a point-table is a table with key-value pairs specifying the new top-left coordinate on the screen of the canvas (keys `x`  and `y`). The table may be crafted by any method which includes these keys, including the use of an `hs.geometry` object.</li></ul>                |

#### [transformation](#transformation)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:transformation([matrix]) -> canvasObject | current value` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the matrix transformation which is applied to every element in the canvas before being individually processed and added to the canvas.                                                                                         |
| **Parameters**                                       | <ul><li>`matrix` - an optional table specifying the matrix table, as defined by the [hs.canvas.matrix](MATRIX.md) module, to be applied to every element of the canvas, or an explicit `nil` to reset the transformation to the identity matrix.</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the canvasObject, otherwise returns the current value</li></ul>          |
| **Notes**                                            | <ul><li>An example use for this method would be to change the canvas's origin point { x = 0, y = 0 } from the lower left corner of the canvas to somewhere else, like the middle of the canvas.</li></ul>                |

#### [wantsLayer](#wantslayer)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.canvas:wantsLayer([flag]) -> canvasObject | currentValue` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set whether or not the canvas object should be rendered by the view or by Core Animation.                                                                                         |
| **Parameters**                                       | <ul><li>`flag` - optional boolean (default false) which indicates whether the canvas object should be rendered by the containing view (false) or by Core Animation (true).</li></ul> |
| **Returns**                                          | <ul><li>If an argument is provided, the canvas object; otherwise the current value.</li></ul>          |
| **Notes**                                            | <ul><li>This method can help smooth the display of small text objects on non-Retina monitors.</li></ul>                |

