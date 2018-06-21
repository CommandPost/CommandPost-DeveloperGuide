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
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new shortcut builder.                                                                                         |
| **Parameters**                                       |  * `receiverFn`		- (optional) a function which will get passed the shortcut when the build is complete.                                       |
| **Returns**                                          |  * `shortcut.builder` which can be used to create the shortcut.                                                |
| **Notes**                                            | * If provided, the receiver function will be called when the shortcut has been configured, and passed the new  shortcut. The result of that function will be returned to the next stage.  If no `receiverFn` is provided, the shortcut will be returned directly.                                                      |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut.new(modifiers, keyCode) -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new keyboard shortcut, attached to the specified `hs.commands.command`                                                                                         |
| **Parameters**                                       |  * `modifiers` 	- The modifiers. * `keyCode`	- The key code.                                       |
| **Returns**                                          |  * shortcut - The shortcut that was created.                                                |

### Fields

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:isEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | If `true`, the shortcut is enabled.                                                                                         |

### Methods

#### [bind](#bind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:bind(pressedFn, releasedFn, repeatedFn) -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | This function binds the shortcut to a hotkey, with the specified callback functions for `pressedFn`, `releasedFn` and `repeatedFn`.                                                                                         |
| **Parameters**                                       |  * `pressedFn`	- (optional) If present, this is called when the shortcut combo is pressed. * `releasedFn`	- (optional) If present, this is called when the shortcut combo is released. * `repeatedFn`	- (optional) If present, this is called when the shortcut combo is repeated.                                       |
| **Returns**                                          |  * `self`                                                |
| **Notes**                                            |  * If the shortcut is enabled, the hotkey will also be enabled at this point.                                                      |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:delete() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deletes a shortcut.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `self`                                                |

#### [disable](#disable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:disable() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | This disables the shortcut. If a hotkey has been bound, it will be disabled also.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `self`                                                |

#### [enable](#enable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:enable() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | This enables the shortcut. If a hotkey has been bound, it will be enabled also.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `self`                                                |

#### [getKeyCode](#getkeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:getKeyCode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a string containing the keycode of the shortcut.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `string` containing the keycode of the shortcut.                                                |

#### [getModifiers](#getmodifiers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:getModifiers() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table containing the modifiers for a shortcut.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `table` containing the modifiers of the shortcut.                                                |

#### [trigger](#trigger)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:trigger() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | This will trigger the keystroke specified in the shortcut.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `self`                                                |

#### [unbind](#unbind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut:unbind() -> shortcut` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Unbinds a shortcut.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `self`                                                |

