# [docs](index.md) » cp.commands.shortcut.builder
---

Shortcut Commands Builder Module.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [add](#add)
 * [new](#new)

## API Documentation

### Methods

#### [add](#add)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut.builder:add(modifier, [keyCode]) -> shortcut/command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified modifier to the set. If a `keyCode` is provided,                                                                                         |
| **Parameters**                                       |  * modifier - (optional) The modifier that was added. * keyCode	- (optional) The key code being modified.                                       |
| **Returns**                                          |  * `self` if no `keyCode` is provided, or the original `command`.                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut.builder.new([receiverFn]) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new shortcut builder. If provided, the receiver function                                                                                         |
| **Parameters**                                       |  * `receiverFn`	- The function which will be called with the new shortcut, when built.                                       |
| **Returns**                                          |  * The builder instance                                                |

