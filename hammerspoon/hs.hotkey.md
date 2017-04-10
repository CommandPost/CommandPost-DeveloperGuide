# [docs](index.md) » hs.hotkey
---

Create and manage global keyboard shortcuts

## Submodules
 * [hs.hotkey.modal](hs.hotkey.modal.md)

## API Overview
* Variables - Configurable values
** [alertDuration](#alertDuration)
* Functions - API calls offered directly by the extension
** [deleteAll](#deleteAll)
** [disableAll](#disableAll)
** [getHotkeys](#getHotkeys)
** [showHotkeys](#showHotkeys)
* Constructors - API calls which return an object, typically one that offers API methods
** [bind](#bind)
** [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
** [delete](#delete)
** [disable](#disable)
** [enable](#enable)

## API Documentation

### Variables

#### [alertDuration](#alertDuration)
| | |
|-|-|
| Signature   | hs.hotkey.alertDuration  |
| Type        | Variable |
| Description | Duration of the alert shown when a hotkey created with a `message` parameter is triggered, in seconds. Default is 1. |
  Usage:
    hs.hotkey.alertDuration = 2.5 -- alert stays on screen a bit longer
    hs.hotkey.alertDuration = 0 -- hotkey alerts are disabled

### Functions

#### [deleteAll](#deleteAll)
| | |
|-|-|
| Signature   | hs.hotkey.deleteAll(mods, key)  |
| Type        | Function |
| Description | Deletes all previously set callbacks for a given keyboard combination |
| Parameters |  * mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:   * "cmd", "command" or "⌘"   * "ctrl", "control" or "⌃"   * "alt", "option" or "⌥"   * "shift" or "⇧" * key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number | | Returns |  * None | 
#### [disableAll](#disableAll)
| | |
|-|-|
| Signature   | hs.hotkey.disableAll(mods, key)  |
| Type        | Function |
| Description | Disables all previously set callbacks for a given keyboard combination |
| Parameters |  * mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:   * "cmd", "command" or "⌘"   * "ctrl", "control" or "⌃"   * "alt", "option" or "⌥"   * "shift" or "⇧" * key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number | | Returns |  * None | 
#### [getHotkeys](#getHotkeys)
| | |
|-|-|
| Signature   | hs.hotkey.getHotkeys() -> table  |
| Type        | Function |
| Description | Returns a list of all currently active hotkeys |
| Parameters |  * None | | Returns |  * A table containing the hotkeys that are active, i.e. enabled and not "shadowed", in the current context   (usually, the global hotkey context, but it could be a modal hotkey context). Every element in the list   is a table with two fields:   * idx - a string describing the keyboard combination for the hotkey   * msg - the hotkey message, if provided when the hotkey was created (prefixed with the keyboard combination) | 
#### [showHotkeys](#showHotkeys)
| | |
|-|-|
| Signature   | hs.hotkey.showHotkeys(mods, key) -> hs.hotkey object  |
| Type        | Function |
| Description | Creates (and enables) a hotkey that shows all currently active hotkeys (i.e. enabled and not "shadowed" |
  in the current context) while pressed
| Parameters |  * mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:   * "cmd", "command" or "⌘"   * "ctrl", "control" or "⌃"   * "alt", "option" or "⌥"   * "shift" or "⇧" * key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number | | Returns |  * The new `hs.hotkey` object | 
### Constructors

#### [bind](#bind)
| | |
|-|-|
| Signature   | hs.hotkey.bind(mods, key, message, pressedfn, releasedfn, repeatfn) -> hs.hotkey object  |
| Type        | Constructor |
| Description | Creates a hotkey and enables it immediately |
| Parameters |  * mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:   * "cmd", "command" or "⌘"   * "ctrl", "control" or "⌃"   * "alt", "option" or "⌥"   * "shift" or "⇧" * key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number * message - A string containing a message to be displayed via `hs.alert()` when the hotkey has been triggered, or nil for no alert * pressedfn - A function that will be called when the hotkey has been pressed, or nil * releasedfn - A function that will be called when the hotkey has been released, or nil * repeatfn - A function that will be called when a pressed hotkey is repeating, or nil | | Returns |  * A new `hs.hotkey` object for method chaining | | Notes |  * This function is just a wrapper that performs `hs.hotkey.new(...):enable()` | 
#### [new](#new)
| | |
|-|-|
| Signature   | hs.hotkey.new(mods, key, [message,] pressedfn, releasedfn, repeatfn) -> hs.hotkey object  |
| Type        | Constructor |
| Description | Creates a new hotkey |
| Parameters |  * mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:   * "cmd", "command" or "⌘"   * "ctrl", "control" or "⌃"   * "alt", "option" or "⌥"   * "shift" or "⇧" * key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number * message - (optional) A string containing a message to be displayed via `hs.alert()` when the hotkey has been   triggered; if omitted, no alert will be shown * pressedfn - A function that will be called when the hotkey has been pressed, or nil * releasedfn - A function that will be called when the hotkey has been released, or nil * repeatfn - A function that will be called when a pressed hotkey is repeating, or nil | | Returns |  * A new `hs.hotkey` object | | Notes |  * You can create multiple `hs.hotkey` objects for the same keyboard combination, but only one can be active   at any given time - see `hs.hotkey:enable()` * If `message` is the empty string `""`, the alert will just show the triggered keyboard combination * If you don't want any alert, you must *actually* omit the `message` parameter; a `nil` in 3rd position   will be interpreted as a missing `pressedfn` * You must pass at least one of `pressedfn`, `releasedfn` or `repeatfn`; to delete a hotkey, use `hs.hotkey:delete()` | 
### Methods

#### [delete](#delete)
| | |
|-|-|
| Signature   | hs.hotkey:delete()  |
| Type        | Method |
| Description | Disables and deletes a hotkey object |
| Parameters |  * None | | Returns |  * None | 
#### [disable](#disable)
| | |
|-|-|
| Signature   | hs.hotkey:disable() -> hs.hotkey object  |
| Type        | Method |
| Description | Disables a hotkey object |
| Parameters |  * None | | Returns |  * The `hs.hotkey` object for method chaining | 
#### [enable](#enable)
| | |
|-|-|
| Signature   | hs.hotkey:enable() -> hs.hotkey object | nil  |
| Type        | Method |
| Description | Enables a hotkey object |
| Parameters |  * None | | Returns |  * The `hs.hotkey` object for method chaining or nil if the hotkey could not be enabled for some reason. | | Notes |  * When you enable a hotkey that uses the same keyboard combination as another previously-enabled hotkey, the old   one will stop working as it's being "shadowed" by the new one. As soon as the new hotkey is disabled or deleted   the old one will trigger again. | 