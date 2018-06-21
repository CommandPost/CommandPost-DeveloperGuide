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
| **Parameters**                                       | <ul><li>modifier - (optional) The modifier that was added.</li></ul><ul><li>keyCode  - (optional) The key code being modified.</li></ul>   |
| **Returns**                                          | <ul><li><code>self</code> if no <code>keyCode</code> is provided, or the original <code>command</code>.</li></ul>            |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.shortcut.builder.new([receiverFn]) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new shortcut builder. If provided, the receiver function                                                                                         |
| **Parameters**                                       | <ul><li><code>receiverFn</code> - The function which will be called with the new shortcut, when built.</li></ul>   |
| **Returns**                                          | <ul><li>The builder instance</li></ul>            |

