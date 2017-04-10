# [docs](index.md) » hs.chooser
---

Graphical, interactive tool for choosing/searching data

Notes:
 * This module was influenced heavily by Choose, by Steven Degutis (https://github.com/sdegutis/choose)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
* [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
* [bgDark](#bgDark)
* [cancel](#cancel)
* [choices](#choices)
* [delete](#delete)
* [fgColor](#fgColor)
* [hide](#hide)
* [isVisible](#isVisible)
* [query](#query)
* [queryChangedCallback](#queryChangedCallback)
* [refreshChoicesCallback](#refreshChoicesCallback)
* [rightClickCallback](#rightClickCallback)
* [rows](#rows)
* [searchSubText](#searchSubText)
* [select](#select)
* [selectedRow](#selectedRow)
* [selectedRowContents](#selectedRowContents)
* [show](#show)
* [showCallback](#showCallback)
* [subTextColor](#subTextColor)
* [width](#width)

## API Documentation

### Constructors

#### [new](#new)
| Signature   | hs.chooser.new(completionFn) -> hs.chooser object  |
| Type        | Constructor |
| Description | Creates a new chooser object |
| Parameters |  * completionFn - A function that will be called when the chooser is dismissed. It should accept one parameter, which will be nil if the user dismissed the chooser window, otherwise it will be a table containing whatever information you supplied for the item the user chose. | | Returns |  * An `hs.chooser` object | 
### Methods

#### [bgDark](#bgDark)
| Signature   | hs.chooser:bgDark([beDark]) -> hs.chooser object or boolean  |
| Type        | Method |
| Description | Sets the background of the chooser between light and dark |
| Parameters |  * beDark - A optional boolean, true to be dark, false to be light. If this parameter is omitted, the current setting will be returned | | Returns |  * The `hs.chooser` object or a boolean, true if the window is dark, false if it is light | | Notes |  * The text colors will not automatically change when you toggle the darkness of the chooser window, you should also set appropriate colors with `hs.chooser:fgColor()` and `hs.chooser:subTextColor()` | 
#### [cancel](#cancel)
| Signature   | hs.chooser:cancel() -> hs.chooser object  |
| Type        | Method |
| Description | Cancels the chooser |
| Parameters |  * None | | Returns |  * The `hs.chooser` object | 
#### [choices](#choices)
| Signature   | hs.chooser:choices(choices) -> hs.chooser object  |
| Type        | Method |
| Description | Sets the choices for a chooser |
  Example:
     ```
    local choices = {
     {
      ["text"] = "First Choice",
      ["subText"] = "This is the subtext of the first choice",
      ["uuid"] = "0001"
     },
     { ["text"] = "Second Option",
       ["subText"] = "I wonder what I should type here?",
       ["uuid"] = "Bbbb"
     },
     { ["text"] = "Third Possibility",
       ["subText"] = "What a lot of choosing there is going on here!",
       ["uuid"] = "III3"
     },
    }
     ```
| Parameters |  * choices - Either a function to call when the list of choices is needed, or nil to remove any existing choices/callback, or a table containing static choices. | | Returns |  * The `hs.chooser` object | | Notes |  * The table of choices (be it provided statically, or returned by the callback) must contain at least the following keys for each choice:  * text - A string that will be shown as the main text of the choice * Each choice may also optionally contain the following keys:  * subText - A string that will be shown underneath the main text of the choice  * image - An `hs.image` image object that will be displayed next to the choice * Any other keys/values in each choice table will be retained by the chooser and returned to the completion callback when a choice is made. This is useful for storing UUIDs or other non-user-facing information, however, it is important to note that you should not store userdata objects in the table - it is run through internal conversion functions, so only basic Lua types should be stored. * If a function is given, it will be called once, when the chooser window is displayed. The results are then cached until this method is called again, or `hs.chooser:refreshChoicesCallback()` is called. | 
#### [delete](#delete)
| Signature   | hs.chooser:delete()  |
| Type        | Method |
| Description | Deletes a chooser |
| Parameters |  * None | | Returns |  * None | 
#### [fgColor](#fgColor)
| Signature   | hs.chooser:fgColor(color) -> hs.chooser object  |
| Type        | Method |
| Description | Sets the foreground color of the chooser |
| Parameters |  * color - An optional table containing a color specification (see `hs.drawing.color`), or nil to restore the default color. If this parameter is omitted, the existing color will be returned | | Returns |  * The `hs.chooser` object or a color table | 
#### [hide](#hide)
| Signature   | hs.chooser:hide() -> hs.chooser object  |
| Type        | Method |
| Description | Hides the chooser |
| Parameters |  * None | | Returns |  * The `hs.chooser` object | 
#### [isVisible](#isVisible)
| Signature   | hs.chooser:isVisible() -> boolean  |
| Type        | Method |
| Description | Checks if the chooser is currently displayed |
| Parameters |  * None | | Returns |  * A boolean, true if the chooser is displayed on screen, false if not | 
#### [query](#query)
| Signature   | hs.chooser:query([queryString]) -> hs.chooser object or string  |
| Type        | Method |
| Description | Sets/gets the search string |
| Parameters |  * queryString - An optional string to search for, or an explicit nil to clear the query. If omitted, the current contents of the search box are returned | | Returns |  * The `hs.chooser` object or a string | | Notes |  * You can provide an explicit nil or empty string to clear the current query string. | 
#### [queryChangedCallback](#queryChangedCallback)
| Signature   | hs.chooser:queryChangedCallback([fn]) -> hs.chooser object  |
| Type        | Method |
| Description | Sets/clears a callback for when the search query changes |
| Parameters |  * fn - An optional function that will be called whenever the search query changes. If this parameter is omitted, the existing callback will be removed. | | Returns |  * The hs.chooser object | | Notes |  * As the user is typing, the callback function will be called for every keypress. You may wish to do filtering on each call, or you may wish to use a delayed `hs.timer` object to only react when they have finished typing. * The callback function should accept a single argument:  * A string containing the new search query | 
#### [refreshChoicesCallback](#refreshChoicesCallback)
| Signature   | hs.chooser:refreshChoicesCallback() -> hs.chooser object  |
| Type        | Method |
| Description | Refreshes the choices data from a callback |
| Parameters |  * None | | Returns |  * The `hs.chooser` object | | Notes |  * This method will do nothing if you have not set a function with `hs.chooser:choices()` | 
#### [rightClickCallback](#rightClickCallback)
| Signature   | hs.chooser:rightClickCallback([fn]) -> hs.chooser object  |
| Type        | Method |
| Description | Sets/clears a callback for right clicking on choices |
  Paramters:
     * fn - An optional function taht will be called whenever the user right clicks on a choice. If this parameter is omitted, the existing callback will be removed.
| Returns |  * The hs.chosoer object | | Notes |   * The callback may accept one argument, the row the right click occurred in or 0 if there is currently no selectable row where the right click occurred. To determine the location of the mouse pointer at the right click, see `hs.mouse`.  * To display a context menu, see `hs.menubar`, specifically the `:popupMenu()` method | 
#### [rows](#rows)
| Signature   | hs.chooser:rows([numRows]) -> hs.chooser object or number  |
| Type        | Method |
| Description | Gets/Sets the number of rows that will be shown |
| Parameters |  * numRows - An optional number of choices to show (i.e. the vertical height of the chooser window). If this parameter is omitted, the current value will be returned | | Returns |  * The `hs.chooser` object or a number | 
#### [searchSubText](#searchSubText)
| Signature   | hs.chooser:searchSubText([searchSubText]) -> hs.chooser object or boolean  |
| Type        | Method |
| Description | Gets/Sets whether the chooser should search in the sub-text of each item |
| Parameters |  * searchSubText - An optional boolean, true to search sub-text, false to not search sub-text. If this parameter is omitted, the current configuration value will be returned | | Returns |  * The `hs.chooser` object if a value was set, or a boolean if no parameter was passed | | Notes |  * This should be used before a chooser has been displayed | 
#### [select](#select)
| Signature   | hs.chooser:select([row]) -> hs.chooser object  |
| Type        | Method |
| Description | Closes the chooser by selecting the specified row, or the currently selected row if not given |
| Parameters |  * `row` - an optional integer specifying the row to select. | | Returns |  * The `hs.chooser` object | 
#### [selectedRow](#selectedRow)
| Signature   | hs.chooser:selectedRow([row]) -> number  |
| Type        | Method |
| Description | Get or set the currently selected row |
| Parameters |  * `row` - an optional integer specifying the row to select. | | Returns |  * If an argument is provided, returns the hs.chooser object; otherwise returns a number containing the row currently selected (i.e. the one highlighted in the UI) | 
#### [selectedRowContents](#selectedRowContents)
| Signature   | hs.chooser:selectedRowContents([row]) -> table  |
| Type        | Method |
| Description | Returns the contents of the currently selected or specified row |
| Parameters |  * `row` - an optional integer specifying the specific row to return the contents of | | Returns |  * a table containing whatever information was supplied for the row currently selected or an empty table if no row is selected or the specified row does not exist. | 
#### [show](#show)
| Signature   | hs.chooser:show() -> hs.chooser object  |
| Type        | Method |
| Description | Displays the chooser |
| Parameters |  * None | | Returns |  * The hs.chooser object | 
#### [showCallback](#showCallback)
| Signature   | hs.chooser:showCallback([fn]) -> hs.chooser object  |
| Type        | Method |
| Description | Sets/clears a callback for when the chooser window is shown |
| Parameters |  * fn - An optional function that will be called when the chooser window is shown. If this parameter is omitted, the existing callback will be removed. | | Returns |  * The hs.chooser object | 
#### [subTextColor](#subTextColor)
| Signature   | hs.chooser:subTextColor(color) -> hs.chooser object or hs.color object  |
| Type        | Method |
| Description | Sets the sub-text color of the chooser |
| Parameters |  * color - An optional table containing a color specification (see `hs.drawing.color`), or nil to restore the default color. If this parameter is omitted, the existing color will be returned | | Returns |  * The `hs.chooser` object or a color table | 
#### [width](#width)
| Signature   | hs.chooser:width([percent]) -> hs.chooser object or number  |
| Type        | Method |
| Description | Gets/Sets the width of the chooser |
| Parameters |  * percent - An optional number indicating the percentage of the width of the screen that the chooser should occupy. If this parameter is omitted, the current width will be returned | | Returns |  * The `hs.chooser` object or a number | | Notes |  * This should be used before a chooser has been displayed | 