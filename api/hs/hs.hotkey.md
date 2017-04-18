# [docs](index.md) » hs.hotkey
---

Create and manage global keyboard shortcuts

## Submodules
 * [hs.hotkey.modal](hs.hotkey.modal.md)

## API Overview
* Variables - Configurable values
 * [alertDuration](#alertduration)
* Functions - API calls offered directly by the extension
 * [deleteAll](#deleteall)
 * [disableAll](#disableall)
 * [getHotkeys](#gethotkeys)
 * [showHotkeys](#showhotkeys)
* Constructors - API calls which return an object, typically one that offers API methods
 * [bind](#bind)
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [delete](#delete)
 * [disable](#disable)
 * [enable](#enable)

## API Documentation

### Variables

#### [alertDuration](#alertduration)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey.alertDuration` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Duration of the alert shown when a hotkey created with a `message` parameter is triggered, in seconds. Default is 1.                                                                                         |

### Functions

#### [deleteAll](#deleteall)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey.deleteAll(mods, key)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Deletes all previously set callbacks for a given keyboard combination                                                                                         |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,</li><li>   which should be zero or more of the following:</li><li>  "cmd", "command" or "⌘"</li><li>  "ctrl", "control" or "⌃"</li><li>  "alt", "option" or "⌥"</li><li>  "shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [disableAll](#disableall)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey.disableAll(mods, key)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disables all previously set callbacks for a given keyboard combination                                                                                         |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,</li><li>   which should be zero or more of the following:</li><li>  "cmd", "command" or "⌘"</li><li>  "ctrl", "control" or "⌃"</li><li>  "alt", "option" or "⌥"</li><li>  "shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [getHotkeys](#gethotkeys)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey.getHotkeys() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of all currently active hotkeys                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the hotkeys that are active, i.e. enabled and not "shadowed", in the current context</li><li>   (usually, the global hotkey context, but it could be a modal hotkey context). Every element in the list</li><li>   is a table with two fields:</li><li>  idx - a string describing the keyboard combination for the hotkey</li><li>  msg - the hotkey message, if provided when the hotkey was created (prefixed with the keyboard combination)</li></ul>          |

#### [showHotkeys](#showhotkeys)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey.showHotkeys(mods, key) -> hs.hotkey object` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates (and enables) a hotkey that shows all currently active hotkeys (i.e. enabled and not "shadowed"                                                                                         |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,</li><li>   which should be zero or more of the following:</li><li>  "cmd", "command" or "⌘"</li><li>  "ctrl", "control" or "⌃"</li><li>  "alt", "option" or "⌥"</li><li>  "shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number</li></ul> |
| **Returns**                                          | <ul><li>The new `hs.hotkey` object</li></ul>          |

### Constructors

#### [bind](#bind)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey.bind(mods, key, message, pressedfn, releasedfn, repeatfn) -> hs.hotkey object` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a hotkey and enables it immediately                                                                                         |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,</li><li>   which should be zero or more of the following:</li><li>  "cmd", "command" or "⌘"</li><li>  "ctrl", "control" or "⌃"</li><li>  "alt", "option" or "⌥"</li><li>  "shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number</li><li>message - A string containing a message to be displayed via `hs.alert()` when the hotkey has been triggered, or nil for no alert</li><li>pressedfn - A function that will be called when the hotkey has been pressed, or nil</li><li>releasedfn - A function that will be called when the hotkey has been released, or nil</li><li>repeatfn - A function that will be called when a pressed hotkey is repeating, or nil</li></ul> |
| **Returns**                                          | <ul><li>A new `hs.hotkey` object for method chaining</li></ul>          |
| **Notes**                                            | <ul><li>This function is just a wrapper that performs `hs.hotkey.new(...):enable()`</li></ul>                |

#### [new](#new)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey.new(mods, key, [message,] pressedfn, releasedfn, repeatfn) -> hs.hotkey object` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new hotkey                                                                                         |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,</li><li>   which should be zero or more of the following:</li><li>  "cmd", "command" or "⌘"</li><li>  "ctrl", "control" or "⌃"</li><li>  "alt", "option" or "⌥"</li><li>  "shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in [hs.keycodes.map](hs.keycodes.html#map) ), or a raw keycode number</li><li>message - (optional) A string containing a message to be displayed via `hs.alert()` when the hotkey has been</li><li>   triggered; if omitted, no alert will be shown</li><li>pressedfn - A function that will be called when the hotkey has been pressed, or nil</li><li>releasedfn - A function that will be called when the hotkey has been released, or nil</li><li>repeatfn - A function that will be called when a pressed hotkey is repeating, or nil</li></ul> |
| **Returns**                                          | <ul><li>A new `hs.hotkey` object</li></ul>          |
| **Notes**                                            | <ul><li>You can create multiple `hs.hotkey` objects for the same keyboard combination, but only one can be active</li><li>   at any given time - see `hs.hotkey:enable()`</li><li>If `message` is the empty string `""`, the alert will just show the triggered keyboard combination</li><li>If you don't want any alert, you must *actually* omit the `message` parameter; a `nil` in 3rd position</li><li>   will be interpreted as a missing `pressedfn`</li><li>You must pass at least one of `pressedfn`, `releasedfn` or `repeatfn`; to delete a hotkey, use `hs.hotkey:delete()`</li></ul>                |

### Methods

#### [delete](#delete)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey:delete()` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables and deletes a hotkey object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [disable](#disable)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey:disable() -> hs.hotkey object` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables a hotkey object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `hs.hotkey` object for method chaining</li></ul>          |

#### [enable](#enable)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.hotkey:enable() -> hs.hotkey object | nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables a hotkey object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `hs.hotkey` object for method chaining or nil if the hotkey could not be enabled for some reason.</li></ul>          |
| **Notes**                                            | <ul><li>When you enable a hotkey that uses the same keyboard combination as another previously-enabled hotkey, the old</li><li>   one will stop working as it's being "shadowed" by the new one. As soon as the new hotkey is disabled or deleted</li><li>   the old one will trigger again.</li></ul>                |

