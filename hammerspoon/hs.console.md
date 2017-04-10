# [docs](index.md) » hs.console
---

Some functions for manipulating the Hammerspoon console.

These functions allow altering the behavior and display of the Hammerspoon console.  They should be considered experimental, but have worked well for me.

## API Overview
* Deprecateds - API features which will be removed in an future release
* [asHSDrawing](#asHSDrawing)
* [asHSWindow](#asHSWindow)
* Functions - API calls offered directly by the extension
* [alpha](#alpha)
* [behaviorAsLabels](#behaviorAsLabels)
* [clearConsole](#clearConsole)
* [getConsole](#getConsole)
* [getHistory](#getHistory)
* [hswindow](#hswindow)
* [inputBackgroundColor](#inputBackgroundColor)
* [level](#level)
* [outputBackgroundColor](#outputBackgroundColor)
* [printStyledtext](#printStyledtext)
* [setConsole](#setConsole)
* [setHistory](#setHistory)
* [smartInsertDeleteEnabled](#smartInsertDeleteEnabled)
* [titleVisibility](#titleVisibility)
* [windowBackgroundColor](#windowBackgroundColor)
* Methods - API calls which can only be made on an object returned by a constructor
* [behavior](#behavior)
* [toolbar](#toolbar)

## API Documentation

### Deprecateds

#### [asHSDrawing](#asHSDrawing)
| Signature   | hs.console.asHSDrawing() -> hs.drawing object  |
| Type        | Deprecated |
| Description | Because use of this function can easily lead to a crash, useful methods from `hs.drawing` have been added to the `hs.console` module itself.  If you believe that a useful method has been overlooked, please submit an issue. |
| Parameters |  * None | | Returns |  * a placeholder object | 
#### [asHSWindow](#asHSWindow)
| Signature   | hs.console.asHSWindow() -> hs.window object  |
| Type        | Deprecated |
| Description | Returns an hs.window object for the console so that you can use hs.window methods on it. |
  This function is identical to [hs.console.hswindow](#hswindow).  It is included for reasons of backwards compatibility, but use of the new name is recommended for clarity.

### Functions

#### [alpha](#alpha)
| Signature   | hs.console.alpha([alpha]) -> currentValue  |
| Type        | Function |
| Description | Get or set the alpha level of the console window. |
| Parameters |  * `alpha` - an optional number between 0.0 and 1.0 specifying the new alpha level for the Hammerspoon console. | | Returns |  * the current, possibly new, value. | 
#### [behaviorAsLabels](#behaviorAsLabels)
| Signature   | hs.console.behaviorAsLabels(behaviorTable) -> currentValue  |
| Type        | Function |
| Description | Get or set the window behavior settings for the console using labels defined in `hs.drawing.windowBehaviors`. |
| Parameters |  * behaviorTable - an optional table of strings and/or numbers specifying the desired window behavior for the Hammerspoon console. | | Returns |  * the current (possibly new) value. | | Notes |  * Window behaviors determine how the console is handled by Spaces and Exposé. See `hs.drawing.windowBehaviors` for more information. | 
#### [clearConsole](#clearConsole)
| Signature   | hs.console.clearConsole() -> nil  |
| Type        | Function |
| Description | Clear the Hammerspoon console output window. |
| Parameters |  * None | | Returns |  * None | | Notes |  * This is equivalent to `hs.console.setConsole()` | 
#### [getConsole](#getConsole)
| Signature   | hs.console.getConsole([styled]) -> text | styledText  |
| Type        | Function |
| Description | Get the text of the Hammerspoon console output window. |
| Parameters |  * styled - an optional boolean indicating whether the console text is returned as a string or a styledText object.  Defaults to false. | | Returns |  * The text currently in the Hammerspoon console output window as either a string or an `hs.styledtext` object. | | Notes |  * If the text of the console is retrieved as a string, no color or style information in the console output is retrieved - only the raw text. | 
#### [getHistory](#getHistory)
| Signature   | hs.console.getHistory() -> array  |
| Type        | Function |
| Description | Get the Hammerspoon console history as an array. |
| Parameters |  * None | | Returns |  * an array containing the history of commands entered into the Hammerspoon console. | 
#### [hswindow](#hswindow)
| Signature   | hs.console.hswindow() -> hs.window object  |
| Type        | Function |
| Description | Get an hs.window object which represents the Hammerspoon console window |
| Parameters |  * None | | Returns |  * an hs.window object | 
#### [inputBackgroundColor](#inputBackgroundColor)
| Signature   | hs.console.inputBackgroundColor([color]) -> color  |
| Type        | Function |
| Description | Get or set the color for the background of the Hammerspoon Console's input field. |
| Parameters | * color - an optional table containing color keys as described in `hs.drawing.color` | | Returns | * the current color setting as a table | | Notes |  * See the `hs.drawing.color` entry in the Dash documentation, or type `help.hs.drawing.color` in the Hammerspoon console to get more information on how to specify a color. | 
#### [level](#level)
| Signature   | hs.console.level([theLevel]) -> currentValue  |
| Type        | Function |
| Description | Get or set the console window level |
| Parameters |  * `theLevel` - an optional parameter specifying the desired level as an integer, which can be obtained from `hs.drawing.windowLevels`. | | Returns |  * the current, possibly new, value | | Notes |  * see the notes for `hs.drawing.windowLevels` | 
#### [outputBackgroundColor](#outputBackgroundColor)
| Signature   | hs.console.outputBackgroundColor([color]) -> color  |
| Type        | Function |
| Description | Get or set the color for the background of the Hammerspoon Console's output view. |
| Parameters | * color - an optional table containing color keys as described in `hs.drawing.color` | | Returns | * the current color setting as a table | | Notes |  * See the `hs.drawing.color` entry in the Dash documentation, or type `help.hs.drawing.color` in the Hammerspoon console to get more information on how to specify a color. | 
#### [printStyledtext](#printStyledtext)
| Signature   | hs.console.printStyledtext(...) -> none  |
| Type        | Function |
| Description | A print function which recognizes `hs.styledtext` objects and renders them as such in the Hammerspoon console. |
  ~~~
       print = function(...)
           hs.rawprint(...)
           hs.console.printStyledtext(...)
       end
    ~~~
| Parameters |  * Any number of arguments can be specified, just like the builtin Lua `print` command.  If an argument matches the userdata type of `hs.styledtext`, the text is rendered as defined by its style attributes in the Hammerspoon console; otherwise it is rendered as it would be via the traditional `print` command within Hammerspoon. | | Returns |  * None | | Notes |  * This has been made as close to the Lua `print` command as possible.  You can replace the existing print command with this by adding the following to your `init.lua` file: | 
#### [setConsole](#setConsole)
| Signature   | hs.console.setConsole([styledText]) -> none  |
| Type        | Function |
| Description | Clear the Hammerspoon console output window. |
| Parameters |  * styledText - an optional `hs.styledtext` object containing the text you wish to replace the Hammerspoon console output with.  If you do not provide an argument, the console is cleared of all content. | | Returns |  * None | | Notes |  * You can specify the console content as a string or as an `hs.styledtext` object in either userdata or table format. | 
#### [setHistory](#setHistory)
| Signature   | hs.console.setHistory(array) -> nil  |
| Type        | Function |
| Description | Set the Hammerspoon console history to the items specified in the given array. |
| Parameters |  * array - the list of commands to set the Hammerspoon console history to. | | Returns |  * None | | Notes |  * You can clear the console history by using an empty array (e.g. `hs.console.setHistory({})` | 
#### [smartInsertDeleteEnabled](#smartInsertDeleteEnabled)
| Signature   | hs.console.smartInsertDeleteEnabled([flag]) -> bool  |
| Type        | Function |
| Description | Determine whether or not objects copied from the console window insert or delete space around selected words to preserve proper spacing and punctuation. |
| Parameters |  * flag - an optional boolean value indicating whether or not "smart" space behavior is enabled when copying from the Hammerspoon console. | | Returns |  * the current value | | Notes |  * this only applies to future copy operations from the Hammerspoon console -- anything already in the clipboard is not affected. | 
#### [titleVisibility](#titleVisibility)
| Signature   | hs.console.titleVisibility([state]) -> current value  |
| Type        | Function |
| Description | Get or set whether or not the "Hammerspoon Console" text appears in the Hammerspoon console titlebar. |
| Parameters |  * state - an optional string containing the text "visible" or "hidden", specifying whether or not the console window's title text appears. | | Returns |  * a string of "visible" or "hidden" specifying the current (possibly changed) state of the window title's visibility. | | Notes |  * When a toolbar is attached to the Hammerspoon console (see the `hs.webview.toolbar` module documentation), this function can be used to specify whether the Toolbar appears underneath the console window's title ("visible") or in the window's title bar itself, as seen in applications like Safari ("hidden"). | 
#### [windowBackgroundColor](#windowBackgroundColor)
| Signature   | hs.console.windowBackgroundColor([color]) -> color  |
| Type        | Function |
| Description | Get or set the color for the background of the Hammerspoon Console's window. |
| Parameters | * color - an optional table containing color keys as described in `hs.drawing.color` | | Returns | * the current color setting as a table | | Notes |  * See the `hs.drawing.color` entry in the Dash documentation, or type `help.hs.drawing.color` in the Hammerspoon console to get more information on how to specify a color. | 
### Methods

#### [behavior](#behavior)
| Signature   | hs.console.behavior([behavior]) -> currentValue  |
| Type        | Method |
| Description | Get or set the window behavior settings for the console. |
| Parameters |  * `behavior` - an optional number representing the desired window behaviors for the Hammerspoon console. | | Returns |  * the current, possibly new, value. | | Notes |  * Window behaviors determine how the webview object is handled by Spaces and Exposé. See `hs.drawing.windowBehaviors` for more information. | 
#### [toolbar](#toolbar)
| Signature   | hs.console.toolbar([toolbar | nil]) -> toolbarObject | currentValue  |
| Type        | Method |
| Description | Get or attach/detach a toolbar to/from the Hammerspoon console. |
   * If the toolbar is currently attached to another window when this function is called, it will be detached from the original window and attached to the console.
| Parameters |  * `toolbar` - if an `hs.webview.toolbar` object is specified, it will be attached to the Hammerspoon console.  If an explicit nil is specified, the current toolbar will be removed from the console. | | Returns |  * if a toolbarObject or explicit nil is specified, returns the toolbarObject; otherwise returns the current toolbarObject or nil, if no toolbar is attached to the console. | | Notes |  * this method is a convenience wrapper for the `hs.webview.toolbar.attachToolbar` function. | 