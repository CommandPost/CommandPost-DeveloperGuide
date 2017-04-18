# [docs](index.md) » hs.menubar
---

Create and manage menubar icons

## API Overview
* Constants - Useful values which cannot be changed
 * [priorities[]](#priorities[])
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [newWithPriority](#newwithpriority)
* Methods - API calls which can only be made on an object returned by a constructor
 * [delete](#delete)
 * [frame](#frame)
 * [icon](#icon)
 * [isInMenuBar](#isinmenubar)
 * [popupMenu](#popupmenu)
 * [priority](#priority)
 * [removeFromMenuBar](#removefrommenubar)
 * [returnToMenuBar](#returntomenubar)
 * [setClickCallback](#setclickcallback)
 * [setIcon](#seticon)
 * [setMenu](#setmenu)
 * [setTitle](#settitle)
 * [setTooltip](#settooltip)
 * [stateImageSize](#stateimagesize)
 * [title](#title)

## API Documentation

### Constants

#### [priorities[]](#priorities[])
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar.priorities[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Pre-defined list of priority levels which can be used for positioning menubar items.                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar.new([inMenuBar]) -> menubaritem or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new menu bar item object and optionally add it to the system menubar                                                                                         |
| **Parameters**                                       | <ul><li>inMenuBar -- an optional parameter which defaults to true.  If it is true, the menubaritem is added to the system menubar, otherwise the menubaritem is hidden.</li></ul> |
| **Returns**                                          | <ul><li>menubar item object to use with other API methods, or nil if it could not be created</li></ul>          |
| **Notes**                                            | <ul><li>You should call hs.menubar:setTitle() or hs.menubar:setIcon() after creating the object, otherwise it will be invisible</li></ul>                |

#### [newWithPriority](#newwithpriority)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar.newWithPriority(priority) -> menubaritem or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new menu bar item object with the specified priority                                                                                         |
| **Parameters**                                       | <ul><li>priority - an integer specifying the menubar item's priority.  A menubar item's position is determined by its priority value.</li></ul> |
| **Returns**                                          | <ul><li>menubar item object to use with other API methods, or nil if it could not be created</li></ul>          |
| **Notes**                                            | <ul><li>Default priority levels can be found in the [hs.menubar.priorities](#priorities) table.</li></ul>                |

### Methods

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:delete()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Removes the menubar item from the menubar and destroys it                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:frame() -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the menubar item frame                                                                                         |
| **Returns**                                          | <ul><li>an hs.geometry rect describing the menubar item's frame</li></ul>          |
| **Notes**                                            | <ul><li>This will return a frame even if no icon or title is set</li></ul>                |

#### [icon](#icon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:icon() -> hs.image object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current icon of the menubar item object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the menubar item icon as an hs.image object, or nil, if there isn't one.</li></ul>          |

#### [isInMenuBar](#isinmenubar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:isInMenuBar() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a boolean indicating whether or not the specified menu is currently in the OS X menubar.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a boolean indicating whether or not the specified menu is currently in the OS X menubar</li></ul>          |

#### [popupMenu](#popupmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:popupMenu(point) -> menubaritem` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Display a menubaritem as a pop up menu at the specified screen point.                                                                                         |
| **Parameters**                                       | <ul><li>point -- the location of the upper left corner of the pop-up menu to be displayed.</li></ul> |
| **Returns**                                          | <ul><li>The menubaritem</li></ul>          |
| **Notes**                                            | <ul><li>Items which trigger hs.menubar:setClickCallback() will invoke the callback function, but we cannot control the positioning of any visual elements the function may create -- calling this method on such an object is the equivalent of invoking its callback function directly.</li></ul>                |

#### [priority](#priority)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:priority([priority]) -> menubaritem | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set a menubar item's priority                                                                                         |
| **Parameters**                                       | <ul><li>priority - an optional integer specifying the menubar item's priority.  A menubar item's position is determined by its priority value.</li></ul> |
| **Returns**                                          | <ul><li>if a priority is provided, then the menubaritem object is returned; otherwise the current priority value is returned.</li></ul>          |
| **Notes**                                            | <ul><li>Default priority levels can be found in the [hs.menubar.priorities](#priorities) table.</li></ul>                |

#### [removeFromMenuBar](#removefrommenubar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:removeFromMenuBar() -> menubaritem` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Removes a menu from the system menu bar.  The item can still be used as a pop-up menu, unless you also delete it.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the menubaritem</li></ul>          |

#### [returnToMenuBar](#returntomenubar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:returnToMenuBar() -> menubaritem` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a previously removed menu back to the system menu bar.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the menubaritem</li></ul>          |

#### [setClickCallback](#setclickcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:setClickCallback(fn) -> menubaritem` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers a function to be called when the menubar item is clicked                                                                                         |
| **Parameters**                                       | <ul><li>`fn` - A function to be called when the menubar item is clicked. If the argument is `nil`, any existing function will be removed. The function can optionally accept a single argument, which will be a table containing boolean values indicating which keyboard modifiers were held down when the menubar item was clicked; The possible keys are:</li><li> cmd</li><li> alt</li><li> shift</li><li> ctrl</li><li> fn</li></ul> |
| **Returns**                                          | <ul><li>the menubaritem</li></ul>          |
| **Notes**                                            | <ul><li>If a menu has been attached to the menubar item, this callback will never be called</li><li>Has no affect on the display of a pop-up menu, but changes will be be in effect if hs.menubar:returnToMenuBar() is called on the menubaritem.</li></ul>                |

#### [setIcon](#seticon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:setIcon(imageData[, template]) -> menubaritem or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the image of a menubar item object. The image will be displayed in the system menubar                                                                                         |
| **Parameters**                                       | <ul><li>imageData - This can one of the following:</li><li> An `hs.image` object</li><li> A string containing a path to an image file</li><li> A string beginning with `ASCII:` which signifies that the rest of the string is interpreted as a special form of ASCII diagram, which will be rendered to an image and used as the icon. See the notes below for information about the special format of ASCII diagram.</li><li> nil, indicating that the current image is to be removed</li><li>template - An optional boolean value which defaults to true. If it's true, the provided image will be treated as a "template" image, which allows it to automatically support OS X 10.10's Dark Mode. If it's false, the image will be used as is, supporting colour.</li></ul> |
| **Returns**                                          | <ul><li>the menubaritem if the image was loaded and set, `nil` if it could not be found or loaded</li></ul>          |
| **Notes**                                            | <ul><li>** API Change **</li><li>  This method used to return true on success -- this has been changed to return the menubaritem on success to facilitate method chaining.  Since Lua treats any value which is not nil or false as "true", this should only affect code where the return value was actually being compared to true, e.g. `if result == true then...` rather than the (unaffected) `if result then...`.</li></ul>                |

#### [setMenu](#setmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:setMenu(menuTable) -> menubaritem` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Attaches a dropdown menu to the menubar item                                                                                         |
| **Parameters**                                       | <ul><li>`menuTable`:</li><li>    If this argument is `nil`:</li><li>       Removes any previously registered menu</li><li>    If this argument is a table:</li><li>       Sets the menu for this menubar item to the supplied table. The format of the table is documented below</li><li>    If this argument is a function:</li><li>       The function will be called each time the user clicks on the menubar item and the function should return a table that specifies the menu to be displayed. The table should be of the same format as described below. The function can optionally accept a single argument, which will be a table containing boolean values indicating which keyboard modifiers were held down when the menubar item was clicked; The possible keys are:</li><li>          cmd</li><li>          alt</li><li>          shift</li><li>          ctrl</li><li>          fn</li></ul> |
| **Returns**                                          | <ul><li>the menubaritem</li></ul>          |
| **Notes**                                            | <ul><li>If you are using the callback function, you should take care not to take too long to generate the menu, as you will block the process and the OS may decide to remove the menubar item</li></ul>                |

#### [setTitle](#settitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:setTitle(title) -> menubaritem` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the title of a menubar item object. The title will be displayed in the system menubar                                                                                         |
| **Parameters**                                       | <ul><li>`title` - A string or `hs.styledtext` object to use as the title, or nil to remove the title</li></ul> |
| **Returns**                                          | <ul><li>the menubar item</li></ul>          |
| **Notes**                                            | <ul><li>If you set an icon as well as a title, they will both be displayed next to each other</li><li>Has no affect on the display of a pop-up menu, but changes will be be in effect if hs.menubar:returnToMenuBar() is called on the menubaritem.</li></ul>                |

#### [setTooltip](#settooltip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:setTooltip(tooltip) -> menubaritem` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the tooltip text on a menubar item                                                                                         |
| **Parameters**                                       | <ul><li>`tooltip` - A string to use as the tooltip</li></ul> |
| **Returns**                                          | <ul><li>the menubaritem</li></ul>          |
| **Notes**                                            | <ul><li>Has no affect on the display of a pop-up menu, but changes will be be in effect if hs.menubar:returnToMenuBar() is called on the menubaritem.</li></ul>                |

#### [stateImageSize](#stateimagesize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:stateImageSize([size]) -> hs.image object | current value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the size for state images when the menu is displayed.                                                                                         |
| **Parameters**                                       | <ul><li>size - an optional table specifying the size for state images displayed when using the `checked` or `state` key in a menu table definition.  Defaults to a size determined by the system menu font point size.  If you specify an explicit nil, the size is reset to this default.</li></ul> |
| **Returns**                                          | <ul><li>if a parameter is provided, returns the menubar item; otherwise returns the current value.</li></ul>          |
| **Notes**                                            | <ul><li>An image is used rather than a checkmark or dash only when you set them with the `onStateImage`, `offStateImage`, or `mixedStateImage` keys.  If you are not using these keys, then this method will have no visible effect on the menu's rendering.  See  [hs.menubar:setMenu](#setMenu) for more information.</li><li>If you are setting the menu contents with a static table, you should invoke this method before invoking [hs.menubar:setMenu](#setMenu), as changes will only go into effect when the table is next converted to a menu structure.</li></ul>                |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.menubar:title([styled]) -> string | styledtextObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current title of the menubar item object.                                                                                         |
| **Parameters**                                       | <ul><li>styled - an optional boolean, defaulting to false, indicating that a styledtextObject representing the text of the menu title should be returned</li></ul> |
| **Returns**                                          | <ul><li>the menubar item title, or an empty string, if there isn't one.  If `styled` is not set or is false, then a string is returned; otherwise a styledtextObject will be returned.</li></ul>          |

