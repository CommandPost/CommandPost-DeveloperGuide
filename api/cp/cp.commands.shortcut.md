# [docs](index.md) » cp.commands.shortcut
---

Shortcut Commands

## Submodules
 * [cp.commands.shortcut.builder](cp.commands.shortcut.builder.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [build](#build)
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isEnabled](#isenabled)
* Methods - API calls which can only be made on an object returned by a constructor
 * [bind](#bind)
 * [delete](#delete)
 * [disable](#disable)
 * [enable](#enable)
 * [getKeyCode](#getkeycode)
 * [getModifiers](#getmodifiers)
 * [trigger](#trigger)
 * [unbind](#unbind)

## API Documentation

### Functions

#### [build](#build)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut.build(receiverFn) -> cp.commands.shortcut.builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new shortcut builder. |
| **Parameters**                                       | <ul><li><code>receiverFn</code>     - (optional) a function which will get passed the shortcut when the build is complete.</li></ul> |
| **Returns**                                          | <ul><li><code>shortcut.builder</code> which can be used to create the shortcut.</li></ul> |
| **Notes**                                            | <ul><li>If provided, the receiver function will be called when the shortcut has been configured, and passed the new  shortcut. The result of that function will be returned to the next stage.  If no <code>receiverFn</code> is provided, the shortcut will be returned directly.</li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut.new(modifiers, keyCode) -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new keyboard shortcut, attached to the specified `hs.commands.command` |
| **Parameters**                                       | <ul><li><code>modifiers</code>  - The modifiers.</li><li><code>keyCode</code>    - The key code.</li></ul> |
| **Returns**                                          | <ul><li>shortcut - The shortcut that was created.</li></ul> |

### Fields

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:isEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | If `true`, the shortcut is enabled. |

### Methods

#### [bind](#bind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:bind(pressedFn, releasedFn, repeatedFn) -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | This function binds the shortcut to a hotkey, with the specified callback functions for `pressedFn`, `releasedFn` and `repeatedFn`. |
| **Parameters**                                       | <ul><li><code>pressedFn</code>  - (optional) If present, this is called when the shortcut combo is pressed.</li><li><code>releasedFn</code> - (optional) If present, this is called when the shortcut combo is released.</li><li><code>repeatedFn</code> - (optional) If present, this is called when the shortcut combo is repeated.</li></ul> |
| **Returns**                                          | <ul><li><code>self</code></li></ul> |
| **Notes**                                            | <ul><li>If the shortcut is enabled, the hotkey will also be enabled at this point.</li></ul> |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:delete() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Deletes a shortcut. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>self</code></li></ul> |

#### [disable](#disable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:disable() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | This disables the shortcut. If a hotkey has been bound, it will be disabled also. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>self</code></li></ul> |

#### [enable](#enable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:enable() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | This enables the shortcut. If a hotkey has been bound, it will be enabled also. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>self</code></li></ul> |

#### [getKeyCode](#getkeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:getKeyCode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a string containing the keycode of the shortcut. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>string</code> containing the keycode of the shortcut.</li></ul> |

#### [getModifiers](#getmodifiers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:getModifiers() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table containing the modifiers for a shortcut. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>table</code> containing the modifiers of the shortcut.</li></ul> |

#### [trigger](#trigger)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:trigger() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | This will trigger the keystroke specified in the shortcut. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>self</code></li></ul> |

#### [unbind](#unbind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:unbind() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Unbinds a shortcut. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>self</code></li></ul> |

