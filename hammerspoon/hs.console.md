# [docs](/hammerspoon/index.md) » hs.console
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

| [asHSDrawing](#asHSDrawing)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.asHSDrawing() -> hs.drawing object`                                                                    |
| **Type**                                    | Deprecated                                                                     |
| **Description**                             | Because use of this function can easily lead to a crash, useful methods from `hs.drawing` have been added to the `hs.console` module itself.  If you believe that a useful method has been overlooked, please submit an issue.                                                                     |
| **Parameters**                              | <ul><li> * None</li></ul> |
| **Returns**                                 | <ul><li> * a placeholder object</li></ul>          |

| [asHSWindow](#asHSWindow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.asHSWindow() -> hs.window object`                                                                    |
| **Type**                                    | Deprecated                                                                     |
| **Description**                             | Returns an hs.window object for the console so that you can use hs.window methods on it.                                                                     |

### Functions

| [alpha](#alpha)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.alpha([alpha]) -> currentValue`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get or set the alpha level of the console window.                                                                     |
| **Parameters**                              | <ul><li> * `alpha` - an optional number between 0.0 and 1.0 specifying the new alpha level for the Hammerspoon console.</li></ul> |
| **Returns**                                 | <ul><li> * the current, possibly new, value.</li></ul>          |

| [behaviorAsLabels](#behaviorAsLabels)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.behaviorAsLabels(behaviorTable) -> currentValue`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get or set the window behavior settings for the console using labels defined in `hs.drawing.windowBehaviors`.                                                                     |
| **Parameters**                              | <ul><li> * behaviorTable - an optional table of strings and/or numbers specifying the desired window behavior for the Hammerspoon console.</li></ul> |
| **Returns**                                 | <ul><li> * the current (possibly new) value.</li></ul>          |
| **Notes**                                   | <ul><li> * Window behaviors determine how the console is handled by Spaces and Exposé. See `hs.drawing.windowBehaviors` for more information.</li></ul>                |

| [clearConsole](#clearConsole)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.clearConsole() -> nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Clear the Hammerspoon console output window.                                                                     |
| **Parameters**                              | <ul><li> * None</li></ul> |
| **Returns**                                 | <ul><li> * None</li></ul>          |
| **Notes**                                   | <ul><li> * This is equivalent to `hs.console.setConsole()`</li></ul>                |

| [getConsole](#getConsole)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.getConsole([styled]) -> text | styledText`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get the text of the Hammerspoon console output window.                                                                     |
| **Parameters**                              | <ul><li> * styled - an optional boolean indicating whether the console text is returned as a string or a styledText object.  Defaults to false.</li></ul> |
| **Returns**                                 | <ul><li> * The text currently in the Hammerspoon console output window as either a string or an `hs.styledtext` object.</li></ul>          |
| **Notes**                                   | <ul><li> * If the text of the console is retrieved as a string, no color or style information in the console output is retrieved - only the raw text.</li></ul>                |

| [getHistory](#getHistory)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.getHistory() -> array`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get the Hammerspoon console history as an array.                                                                     |
| **Parameters**                              | <ul><li> * None</li></ul> |
| **Returns**                                 | <ul><li> * an array containing the history of commands entered into the Hammerspoon console.</li></ul>          |

| [hswindow](#hswindow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.hswindow() -> hs.window object`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get an hs.window object which represents the Hammerspoon console window                                                                     |
| **Parameters**                              | <ul><li> * None</li></ul> |
| **Returns**                                 | <ul><li> * an hs.window object</li></ul>          |

| [inputBackgroundColor](#inputBackgroundColor)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.inputBackgroundColor([color]) -> color`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get or set the color for the background of the Hammerspoon Console's input field.                                                                     |
| **Parameters**                              | <ul><li>* color - an optional table containing color keys as described in `hs.drawing.color`</li></ul> |
| **Returns**                                 | <ul><li>* the current color setting as a table</li></ul>          |
| **Notes**                                   | <ul><li> * See the `hs.drawing.color` entry in the Dash documentation, or type `help.hs.drawing.color` in the Hammerspoon console to get more information on how to specify a color.</li></ul>                |

| [level](#level)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.level([theLevel]) -> currentValue`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get or set the console window level                                                                     |
| **Parameters**                              | <ul><li> * `theLevel` - an optional parameter specifying the desired level as an integer, which can be obtained from `hs.drawing.windowLevels`.</li></ul> |
| **Returns**                                 | <ul><li> * the current, possibly new, value</li></ul>          |
| **Notes**                                   | <ul><li> * see the notes for `hs.drawing.windowLevels`</li></ul>                |

| [outputBackgroundColor](#outputBackgroundColor)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.outputBackgroundColor([color]) -> color`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get or set the color for the background of the Hammerspoon Console's output view.                                                                     |
| **Parameters**                              | <ul><li>* color - an optional table containing color keys as described in `hs.drawing.color`</li></ul> |
| **Returns**                                 | <ul><li>* the current color setting as a table</li></ul>          |
| **Notes**                                   | <ul><li> * See the `hs.drawing.color` entry in the Dash documentation, or type `help.hs.drawing.color` in the Hammerspoon console to get more information on how to specify a color.</li></ul>                |

| [printStyledtext](#printStyledtext)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.printStyledtext(...) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | A print function which recognizes `hs.styledtext` objects and renders them as such in the Hammerspoon console.                                                                     |
| **Parameters**                              | <ul><li> * Any number of arguments can be specified, just like the builtin Lua `print` command.  If an argument matches the userdata type of `hs.styledtext`, the text is rendered as defined by its style attributes in the Hammerspoon console; otherwise it is rendered as it would be via the traditional `print` command within Hammerspoon.</li></ul> |
| **Returns**                                 | <ul><li> * None</li></ul>          |
| **Notes**                                   | <ul><li> * This has been made as close to the Lua `print` command as possible.  You can replace the existing print command with this by adding the following to your `init.lua` file:</li></ul>                |

| [setConsole](#setConsole)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.setConsole([styledText]) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Clear the Hammerspoon console output window.                                                                     |
| **Parameters**                              | <ul><li> * styledText - an optional `hs.styledtext` object containing the text you wish to replace the Hammerspoon console output with.  If you do not provide an argument, the console is cleared of all content.</li></ul> |
| **Returns**                                 | <ul><li> * None</li></ul>          |
| **Notes**                                   | <ul><li> * You can specify the console content as a string or as an `hs.styledtext` object in either userdata or table format.</li></ul>                |

| [setHistory](#setHistory)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.setHistory(array) -> nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Set the Hammerspoon console history to the items specified in the given array.                                                                     |
| **Parameters**                              | <ul><li> * array - the list of commands to set the Hammerspoon console history to.</li></ul> |
| **Returns**                                 | <ul><li> * None</li></ul>          |
| **Notes**                                   | <ul><li> * You can clear the console history by using an empty array (e.g. `hs.console.setHistory({})`</li></ul>                |

| [smartInsertDeleteEnabled](#smartInsertDeleteEnabled)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.smartInsertDeleteEnabled([flag]) -> bool`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Determine whether or not objects copied from the console window insert or delete space around selected words to preserve proper spacing and punctuation.                                                                     |
| **Parameters**                              | <ul><li> * flag - an optional boolean value indicating whether or not "smart" space behavior is enabled when copying from the Hammerspoon console.</li></ul> |
| **Returns**                                 | <ul><li> * the current value</li></ul>          |
| **Notes**                                   | <ul><li> * this only applies to future copy operations from the Hammerspoon console -- anything already in the clipboard is not affected.</li></ul>                |

| [titleVisibility](#titleVisibility)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.titleVisibility([state]) -> current value`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get or set whether or not the "Hammerspoon Console" text appears in the Hammerspoon console titlebar.                                                                     |
| **Parameters**                              | <ul><li> * state - an optional string containing the text "visible" or "hidden", specifying whether or not the console window's title text appears.</li></ul> |
| **Returns**                                 | <ul><li> * a string of "visible" or "hidden" specifying the current (possibly changed) state of the window title's visibility.</li></ul>          |
| **Notes**                                   | <ul><li> * When a toolbar is attached to the Hammerspoon console (see the `hs.webview.toolbar` module documentation), this function can be used to specify whether the Toolbar appears underneath the console window's title ("visible") or in the window's title bar itself, as seen in applications like Safari ("hidden").</li></ul>                |

| [windowBackgroundColor](#windowBackgroundColor)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.windowBackgroundColor([color]) -> color`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get or set the color for the background of the Hammerspoon Console's window.                                                                     |
| **Parameters**                              | <ul><li>* color - an optional table containing color keys as described in `hs.drawing.color`</li></ul> |
| **Returns**                                 | <ul><li>* the current color setting as a table</li></ul>          |
| **Notes**                                   | <ul><li> * See the `hs.drawing.color` entry in the Dash documentation, or type `help.hs.drawing.color` in the Hammerspoon console to get more information on how to specify a color.</li></ul>                |

### Methods

| [behavior](#behavior)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.behavior([behavior]) -> currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the window behavior settings for the console.                                                                     |
| **Parameters**                              | <ul><li> * `behavior` - an optional number representing the desired window behaviors for the Hammerspoon console.</li></ul> |
| **Returns**                                 | <ul><li> * the current, possibly new, value.</li></ul>          |
| **Notes**                                   | <ul><li> * Window behaviors determine how the webview object is handled by Spaces and Exposé. See `hs.drawing.windowBehaviors` for more information.</li></ul>                |

| [toolbar](#toolbar)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.console.toolbar([toolbar | nil]) -> toolbarObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or attach/detach a toolbar to/from the Hammerspoon console.                                                                     |
| **Parameters**                              | <ul><li> * `toolbar` - if an `hs.webview.toolbar` object is specified, it will be attached to the Hammerspoon console.  If an explicit nil is specified, the current toolbar will be removed from the console.</li></ul> |
| **Returns**                                 | <ul><li> * if a toolbarObject or explicit nil is specified, returns the toolbarObject; otherwise returns the current toolbarObject or nil, if no toolbar is attached to the console.</li></ul>          |
| **Notes**                                   | <ul><li> * this method is a convenience wrapper for the `hs.webview.toolbar.attachToolbar` function.</li></ul>                |

