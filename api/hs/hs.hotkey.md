# [docs](index.md) » hs.hotkey
---

Create and manage global keyboard shortcuts

## Submodules
 * [hs.hotkey.modal](hs.hotkey.modal.md)

## API Overview
* Variables - Configurable values
 * [alertDuration](#alertduration)
* Functions - API calls offered directly by the extension
 * [assignable](#assignable)
 * [deleteAll](#deleteall)
 * [disableAll](#disableall)
 * [getHotkeys](#gethotkeys)
 * [showHotkeys](#showhotkeys)
 * [systemAssigned](#systemassigned)
* Constructors - API calls which return an object, typically one that offers API methods
 * [bind](#bind)
 * [bindSpec](#bindspec)
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [delete](#delete)
 * [disable](#disable)
 * [enable](#enable)

## API Documentation

### Variables

#### [alertDuration](#alertduration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.alertDuration` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Duration of the alert shown when a hotkey created with a `message` parameter is triggered, in seconds. Default is 1. |

### Functions

#### [assignable](#assignable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.assignable(mods, key) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Determines whether the hotkey combination can be assigned a callback through Hammerspoon. |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:</li><li>"cmd", "command" or "⌘"</li><li>"ctrl", "control" or "⌃"</li><li>"alt", "option" or "⌥"</li><li>"shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in <a href="hs.keycodes.html#map">hs.keycodes.map</a> ), or a raw keycode number</li></ul> |
| **Returns**                                          | <ul><li>a boolean value, true if the hotkey combination can be given an assignment by Hammerspoon or false if it cannot.</li></ul> |
| **Notes**                                            | <ul><li>The most common reason a hotkey combination cannot be given an assignment by Hammerspoon is because it is in use by the Mac operating system -- see the Shortcuts tab of Keyboard in the System Preferences application or <a href="#systemAssigned">hs.hotkey.systemAssigned</a>.</li></ul> |

#### [deleteAll](#deleteall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.deleteAll(mods, key)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Deletes all previously set callbacks for a given keyboard combination |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:</li><li>"cmd", "command" or "⌘"</li><li>"ctrl", "control" or "⌃"</li><li>"alt", "option" or "⌥"</li><li>"shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in <a href="hs.keycodes.html#map">hs.keycodes.map</a> ), or a raw keycode number</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [disableAll](#disableall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.disableAll(mods, key)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Disables all previously set callbacks for a given keyboard combination |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:</li><li>"cmd", "command" or "⌘"</li><li>"ctrl", "control" or "⌃"</li><li>"alt", "option" or "⌥"</li><li>"shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in <a href="hs.keycodes.html#map">hs.keycodes.map</a> ), or a raw keycode number</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getHotkeys](#gethotkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.getHotkeys() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a list of all currently active hotkeys |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the hotkeys that are active, i.e. enabled and not "shadowed", in the current context   (usually, the global hotkey context, but it could be a modal hotkey context). Every element in the list   is a table with two fields:</li><li>idx - a string describing the keyboard combination for the hotkey</li><li>msg - the hotkey message, if provided when the hotkey was created (prefixed with the keyboard combination)</li></ul> |

#### [showHotkeys](#showhotkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.showHotkeys(mods, key) -> hs.hotkey object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates (and enables) a hotkey that shows all currently active hotkeys (i.e. enabled and not "shadowed" |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:</li><li>"cmd", "command" or "⌘"</li><li>"ctrl", "control" or "⌃"</li><li>"alt", "option" or "⌥"</li><li>"shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in <a href="hs.keycodes.html#map">hs.keycodes.map</a> ), or a raw keycode number</li></ul> |
| **Returns**                                          | <ul><li>The new <code>hs.hotkey</code> object</li></ul> |

#### [systemAssigned](#systemassigned)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.systemAssigned(mods, key) -> table | false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Examine whether a potential hotkey is in use by the macOS system such as the Screen Capture, Universal Access, and Keyboard Navigation keys. |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:</li><li>"cmd", "command" or "⌘"</li><li>"ctrl", "control" or "⌃"</li><li>"alt", "option" or "⌥"</li><li>"shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in <a href="hs.keycodes.html#map">hs.keycodes.map</a> ), or a raw keycode number</li></ul> |
| **Returns**                                          | <ul><li>if the hotkey combination is in use by a system function, returns a table containing the following keys:</li><li>keycode - the numberic keycode for the hotkey</li><li>mods    - a numeric representation of the modifier flags for the htokey</li><li>enabled - a boolean indicating whether or not the key is currently enabled</li><li>if the hotkey combination is not in use by the operating system, returns the boolean value <code>false</code></li></ul> |
| **Notes**                                            | <ul><li>this is provided for informational purposes and does not provide a reliable test as to whether or not Hammerspoon can use the combination to create a custom hotkey -- some combinations which return a table can be over-ridden by Hammerspoon while others cannot.  See also <a href="#assignable">hs.hotkey.assignable</a>.</li></ul> |

### Constructors

#### [bind](#bind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.bind(mods, key, message, pressedfn, releasedfn, repeatfn) -> hs.hotkey object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a hotkey and enables it immediately |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:</li><li>"cmd", "command" or "⌘"</li><li>"ctrl", "control" or "⌃"</li><li>"alt", "option" or "⌥"</li><li>"shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in <a href="hs.keycodes.html#map">hs.keycodes.map</a> ), or a raw keycode number</li><li>message - A string containing a message to be displayed via <code>hs.alert()</code> when the hotkey has been triggered, or nil for no alert</li><li>pressedfn - A function that will be called when the hotkey has been pressed, or nil</li><li>releasedfn - A function that will be called when the hotkey has been released, or nil</li><li>repeatfn - A function that will be called when a pressed hotkey is repeating, or nil</li></ul> |
| **Returns**                                          | <ul><li>A new <code>hs.hotkey</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>This function is just a wrapper that performs <code>hs.hotkey.new(...):enable()</code></li></ul> |

#### [bindSpec](#bindspec)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.bindSpec(keyspec, ...) -> hs.hotkey object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a hotkey and enables it immediately |
| **Parameters**                                       | <ul><li>keyspec - A table containing two items:</li><li>first, a table containing keyboard modifiers, as specified in <code>hs.hotkey.bind()</code></li><li>second, a string containing the name of a keyboard key, as specified in <code>hs.hotkey.bind()</code></li><li>... - All remaining arguments are as specified in <code>hs.hotkey.bind()</code></li></ul> |
| **Returns**                                          | <ul><li>A new <code>hs.hotkey</code> object for method chaining</li></ul> |
| **Notes**                                            | <ul><li>This function is just a wrapper that performs <code>hs.hotkey.bind(keyspec[1], keyspec[2], ...)</code></li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.new(mods, key, [message,] pressedfn, releasedfn, repeatfn) -> hs.hotkey object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new hotkey |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,   which should be zero or more of the following:</li><li>"cmd", "command" or "⌘"</li><li>"ctrl", "control" or "⌃"</li><li>"alt", "option" or "⌥"</li><li>"shift" or "⇧"</li><li>key - A string containing the name of a keyboard key (as found in <a href="hs.keycodes.html#map">hs.keycodes.map</a> ), or a raw keycode number</li><li>message - (optional) A string containing a message to be displayed via <code>hs.alert()</code> when the hotkey has been   triggered; if omitted, no alert will be shown</li><li>pressedfn - A function that will be called when the hotkey has been pressed, or nil</li><li>releasedfn - A function that will be called when the hotkey has been released, or nil</li><li>repeatfn - A function that will be called when a pressed hotkey is repeating, or nil</li></ul> |
| **Returns**                                          | <ul><li>A new <code>hs.hotkey</code> object or nil if the hotkey could not be enabled</li></ul> |
| **Notes**                                            | <ul><li>You can create multiple <code>hs.hotkey</code> objects for the same keyboard combination, but only one can be active   at any given time - see <code>hs.hotkey:enable()</code></li><li>If <code>message</code> is the empty string <code>""</code>, the alert will just show the triggered keyboard combination</li><li>If you don't want any alert, you must <em>actually</em> omit the <code>message</code> parameter; a <code>nil</code> in 3rd position   will be interpreted as a missing <code>pressedfn</code></li><li>You must pass at least one of <code>pressedfn</code>, <code>releasedfn</code> or <code>repeatfn</code>; to delete a hotkey, use <code>hs.hotkey:delete()</code></li></ul> |

### Methods

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey:delete()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Disables and deletes a hotkey object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [disable](#disable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey:disable() -> hs.hotkey object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Disables a hotkey object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.hotkey</code> object for method chaining</li></ul> |

#### [enable](#enable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey:enable() -> hs.hotkey object | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Enables a hotkey object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.hotkey</code> object for method chaining or nil if the hotkey could not be enabled for some reason.</li></ul> |
| **Notes**                                            | <ul><li>When you enable a hotkey that uses the same keyboard combination as another previously-enabled hotkey, the old   one will stop working as it's being "shadowed" by the new one. As soon as the new hotkey is disabled or deleted   the old one will trigger again.</li></ul> |

