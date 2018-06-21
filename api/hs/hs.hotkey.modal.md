# [docs](index.md) » hs.hotkey.modal
---

Create/manage modal keyboard shortcut environments

Usage:
k = hs.hotkey.modal.new('cmd-shift', 'd')
function k:entered() hs.alert'Entered mode' end
function k:exited()  hs.alert'Exited mode'  end
k:bind('', 'escape', function() k:exit() end)
k:bind('', 'J', 'Pressed J',function() print'let the record show that J was pressed' end)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [bind](#bind)
 * [delete](#delete)
 * [enter](#enter)
 * [entered](#entered)
 * [exit](#exit)
 * [exited](#exited)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.modal.new(mods, key, message) -> hs.hotkey.modal object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new modal state, optionally with a global keyboard combination to trigger it                                                                                         |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,</li></ul><p>which should be zero or more of the following:</p><ul><li>"cmd", "command" or "⌘"</li></ul><ul><li>"ctrl", "control" or "⌃"</li></ul><ul><li>"alt", "option" or "⌥"</li></ul><ul><li>"shift" or "⇧"</li></ul><ul><li>key - A string containing the name of a keyboard key (as found in <a href="hs.keycodes.html#map">hs.keycodes.map</a> ), or a raw keycode number</li></ul><ul><li>message - A string containing a message to be displayed via <code>hs.alert()</code> when the hotkey has been triggered, or nil for no alert</li></ul>   |
| **Returns**                                          | <ul><li>A new <code>hs.hotkey.modal</code> object</li></ul>            |
| **Notes**                                            | <ul><li>If <code>key</code> is nil, no global hotkey will be registered (all other parameters will be ignored)</li></ul>                 |

### Methods

#### [bind](#bind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.modal:bind(mods, key, message, pressedfn, releasedfn, repeatfn) -> hs.hotkey.modal object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a hotkey that is enabled/disabled as the modal is entered/exited                                                                                         |
| **Parameters**                                       | <ul><li>mods - A table or a string containing (as elements, or as substrings with any separator) the keyboard modifiers required,</li></ul><p>which should be zero or more of the following:</p><ul><li>"cmd", "command" or "⌘"</li></ul><ul><li>"ctrl", "control" or "⌃"</li></ul><ul><li>"alt", "option" or "⌥"</li></ul><ul><li>"shift" or "⇧"</li></ul><ul><li>key - A string containing the name of a keyboard key (as found in <a href="hs.keycodes.html#map">hs.keycodes.map</a> ), or a raw keycode number</li></ul><ul><li>message - A string containing a message to be displayed via <code>hs.alert()</code> when the hotkey has been triggered, or nil for no alert</li></ul><ul><li>pressedfn - A function that will be called when the hotkey has been pressed, or nil</li></ul><ul><li>releasedfn - A function that will be called when the hotkey has been released, or nil</li></ul><ul><li>repeatfn - A function that will be called when a pressed hotkey is repeating, or nil</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.hotkey.modal</code> object for method chaining</li></ul>            |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.modal:delete()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deletes a modal hotkey object without calling :exited()                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [enter](#enter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.modal:enter() -> hs.hotkey.modal object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enters a modal state                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.hotkey.modal</code> object for method chaining</li></ul>            |
| **Notes**                                            | <ul><li>This method will enable all of the hotkeys defined in the modal state via <code>hs.hotkey.modal:bind()</code>,</li></ul><p>and disable the hotkey that entered the modal state (if one was defined)</p><ul><li>If the modal state was created with a keyboard combination, this method will be called automatically</li></ul>                 |

#### [entered](#entered)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.modal:entered()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Optional callback for when a modal is entered                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>This is a pre-existing function that you should override if you need to use it; the default implementation does nothing.</li></ul>                 |

#### [exit](#exit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.modal:exit() -> hs.hotkey.modal object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Exits a modal state                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.hotkey.modal</code> object for method chaining</li></ul>            |
| **Notes**                                            | <ul><li>This method will disable all of the hotkeys defined in the modal state, and enable the hotkey for entering the modal state (if one was defined)</li></ul>                 |

#### [exited](#exited)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hotkey.modal:exited()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Optional callback for when a modal is exited                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>This is a pre-existing function that you should override if you need to use it; the default implementation does nothing.</li></ul>                 |

