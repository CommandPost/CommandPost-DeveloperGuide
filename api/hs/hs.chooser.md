# [docs](index.md) » hs.chooser
---

Graphical, interactive tool for choosing/searching data

Notes:
 * This module was influenced heavily by Choose, by Steven Degutis (https://github.com/sdegutis/choose)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [bgDark](#bgdark)
 * [cancel](#cancel)
 * [choices](#choices)
 * [delete](#delete)
 * [fgColor](#fgcolor)
 * [hide](#hide)
 * [isVisible](#isvisible)
 * [query](#query)
 * [queryChangedCallback](#querychangedcallback)
 * [refreshChoicesCallback](#refreshchoicescallback)
 * [rightClickCallback](#rightclickcallback)
 * [rows](#rows)
 * [searchSubText](#searchsubtext)
 * [select](#select)
 * [selectedRow](#selectedrow)
 * [selectedRowContents](#selectedrowcontents)
 * [show](#show)
 * [showCallback](#showcallback)
 * [subTextColor](#subtextcolor)
 * [width](#width)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser.new(completionFn) -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new chooser object                                                                                         |
| **Parameters**                                       | <ul><li>completionFn - A function that will be called when the chooser is dismissed. It should accept one parameter, which will be nil if the user dismissed the chooser window, otherwise it will be a table containing whatever information you supplied for the item the user chose.</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.chooser</code> object</li></ul>            |

### Methods

#### [bgDark](#bgdark)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:bgDark([beDark]) -> hs.chooser object or boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the background of the chooser between light and dark                                                                                         |
| **Parameters**                                       | <ul><li>beDark - A optional boolean, true to be dark, false to be light. If this parameter is omitted, the current setting will be returned</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object or a boolean, true if the window is dark, false if it is light</li></ul>            |
| **Notes**                                            | <ul><li>The text colors will not automatically change when you toggle the darkness of the chooser window, you should also set appropriate colors with <code>hs.chooser:fgColor()</code> and <code>hs.chooser:subTextColor()</code></li></ul>                 |

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:cancel() -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Cancels the chooser                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object</li></ul>            |

#### [choices](#choices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:choices(choices) -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the choices for a chooser                                                                                         |
| **Parameters**                                       | <ul><li>choices - Either a function to call when the list of choices is needed, or nil to remove any existing choices/callback, or a table containing static choices.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object</li></ul>            |
| **Notes**                                            | <ul><li>The table of choices (be it provided statically, or returned by the callback) must contain at least the following keys for each choice:</li></ul><ul><li>text - A string or hs.styledtext object that will be shown as the main text of the choice</li></ul><ul><li>Each choice may also optionally contain the following keys:</li></ul><ul><li>subText - A string or hs.styledtext object that will be shown underneath the main text of the choice</li></ul><ul><li>image - An <code>hs.image</code> image object that will be displayed next to the choice</li></ul><ul><li>Any other keys/values in each choice table will be retained by the chooser and returned to the completion callback when a choice is made. This is useful for storing UUIDs or other non-user-facing information, however, it is important to note that you should not store userdata objects in the table - it is run through internal conversion functions, so only basic Lua types should be stored.</li></ul><ul><li>If a function is given, it will be called once, when the chooser window is displayed. The results are then cached until this method is called again, or <code>hs.chooser:refreshChoicesCallback()</code> is called.</li></ul>                 |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:delete()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deletes a chooser                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [fgColor](#fgcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:fgColor(color) -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the foreground color of the chooser                                                                                         |
| **Parameters**                                       | <ul><li>color - An optional table containing a color specification (see <code>hs.drawing.color</code>), or nil to restore the default color. If this parameter is omitted, the existing color will be returned</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object or a color table</li></ul>            |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:hide() -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the chooser                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object</li></ul>            |

#### [isVisible](#isvisible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:isVisible() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the chooser is currently displayed                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A boolean, true if the chooser is displayed on screen, false if not</li></ul>            |

#### [query](#query)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:query([queryString]) -> hs.chooser object or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets/gets the search string                                                                                         |
| **Parameters**                                       | <ul><li>queryString - An optional string to search for, or an explicit nil to clear the query. If omitted, the current contents of the search box are returned</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object or a string</li></ul>            |
| **Notes**                                            | <ul><li>You can provide an explicit nil or empty string to clear the current query string.</li></ul>                 |

#### [queryChangedCallback](#querychangedcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:queryChangedCallback([fn]) -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets/clears a callback for when the search query changes                                                                                         |
| **Parameters**                                       | <ul><li>fn - An optional function that will be called whenever the search query changes. If this parameter is omitted, the existing callback will be removed.</li></ul>   |
| **Returns**                                          | <ul><li>The hs.chooser object</li></ul>            |
| **Notes**                                            | <ul><li>As the user is typing, the callback function will be called for every keypress. You may wish to do filtering on each call, or you may wish to use a delayed <code>hs.timer</code> object to only react when they have finished typing.</li></ul><ul><li>The callback function should accept a single argument:</li></ul><ul><li>A string containing the new search query</li></ul>                 |

#### [refreshChoicesCallback](#refreshchoicescallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:refreshChoicesCallback() -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Refreshes the choices data from a callback                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object</li></ul>            |
| **Notes**                                            | <ul><li>This method will do nothing if you have not set a function with <code>hs.chooser:choices()</code></li></ul>                 |

#### [rightClickCallback](#rightclickcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:rightClickCallback([fn]) -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets/clears a callback for right clicking on choices                                                                                         |
| **Parameters**                                       | <ul><li>fn - An optional function that will be called whenever the user right clicks on a choice. If this parameter is omitted, the existing callback will be removed.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object</li></ul>            |
| **Notes**                                            | <ul><li>The callback may accept one argument, the row the right click occurred in or 0 if there is currently no selectable row where the right click occurred. To determine the location of the mouse pointer at the right click, see <code>hs.mouse</code>.</li></ul><ul><li>To display a context menu, see <code>hs.menubar</code>, specifically the <code>:popupMenu()</code> method</li></ul>                 |

#### [rows](#rows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:rows([numRows]) -> hs.chooser object or number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets/Sets the number of rows that will be shown                                                                                         |
| **Parameters**                                       | <ul><li>numRows - An optional number of choices to show (i.e. the vertical height of the chooser window). If this parameter is omitted, the current value will be returned</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object or a number</li></ul>            |

#### [searchSubText](#searchsubtext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:searchSubText([searchSubText]) -> hs.chooser object or boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets/Sets whether the chooser should search in the sub-text of each item                                                                                         |
| **Parameters**                                       | <ul><li>searchSubText - An optional boolean, true to search sub-text, false to not search sub-text. If this parameter is omitted, the current configuration value will be returned</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object if a value was set, or a boolean if no parameter was passed</li></ul>            |
| **Notes**                                            | <ul><li>This should be used before a chooser has been displayed</li></ul>                 |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:select([row]) -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Closes the chooser by selecting the specified row, or the currently selected row if not given                                                                                         |
| **Parameters**                                       | <ul><li><code>row</code> - an optional integer specifying the row to select.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object</li></ul>            |

#### [selectedRow](#selectedrow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:selectedRow([row]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the currently selected row                                                                                         |
| **Parameters**                                       | <ul><li><code>row</code> - an optional integer specifying the row to select.</li></ul>   |
| **Returns**                                          | <ul><li>If an argument is provided, returns the hs.chooser object; otherwise returns a number containing the row currently selected (i.e. the one highlighted in the UI)</li></ul>            |

#### [selectedRowContents](#selectedrowcontents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:selectedRowContents([row]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the contents of the currently selected or specified row                                                                                         |
| **Parameters**                                       | <ul><li><code>row</code> - an optional integer specifying the specific row to return the contents of</li></ul>   |
| **Returns**                                          | <ul><li>a table containing whatever information was supplied for the row currently selected or an empty table if no row is selected or the specified row does not exist.</li></ul>            |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:show([topLeftPoint]) -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Displays the chooser                                                                                         |
| **Parameters**                                       | <ul><li>An optional <code>hs.geometry</code> point object describing the absolute screen co-ordinates for the top left point of the chooser window. Defaults to centering the window on the primary screen</li></ul>   |
| **Returns**                                          | <ul><li>The hs.chooser object</li></ul>            |

#### [showCallback](#showcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:showCallback([fn]) -> hs.chooser object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets/clears a callback for when the chooser window is shown                                                                                         |
| **Parameters**                                       | <ul><li>fn - An optional function that will be called when the chooser window is shown. If this parameter is omitted, the existing callback will be removed.</li></ul>   |
| **Returns**                                          | <ul><li>The hs.chooser object</li></ul>            |

#### [subTextColor](#subtextcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:subTextColor(color) -> hs.chooser object or hs.color object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the sub-text color of the chooser                                                                                         |
| **Parameters**                                       | <ul><li>color - An optional table containing a color specification (see <code>hs.drawing.color</code>), or nil to restore the default color. If this parameter is omitted, the existing color will be returned</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object or a color table</li></ul>            |

#### [width](#width)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.chooser:width([percent]) -> hs.chooser object or number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets/Sets the width of the chooser                                                                                         |
| **Parameters**                                       | <ul><li>percent - An optional number indicating the percentage of the width of the screen that the chooser should occupy. If this parameter is omitted, the current width will be returned</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.chooser</code> object or a number</li></ul>            |
| **Notes**                                            | <ul><li>This should be used before a chooser has been displayed</li></ul>                 |

