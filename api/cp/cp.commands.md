# [docs](index.md) » cp.commands
---

Commands Module.

## Submodules
 * [cp.commands.command](cp.commands.command.md)
 * [cp.commands.englishKeyCodes](cp.commands.englishKeyCodes.md)
 * [cp.commands.shortcut](cp.commands.shortcut.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [group](#group)
 * [groupIds](#groupids)
 * [groups](#groups)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)
 * [isEditable](#iseditable)
* Methods - API calls which can only be made on an object returned by a constructor
 * [new](#new)

## API Documentation

### Functions

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.group(id) -> cp.command or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a collection of commands. These commands can be enabled or disabled as a group.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`		- The ID to retrieve</li></ul> |
| **Returns**                                          | <ul><li>`cp.commands` - The command group with the specified ID, or `nil` if none exists.</li></ul>          |

#### [groupIds](#groupids)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.groupIds() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an array of IDs of command groups which have been created.                                                                                         |
| **Parameters**                                       | <ul><li>* N/A</li></ul> |
| **Returns**                                          | <ul><li>`table` - The array of group IDs.</li></ul>          |

#### [groups](#groups)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.groups() -> table of cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table with the set of commands.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`		- The ID to retrieve</li></ul> |
| **Returns**                                          | <ul><li>`cp.commands` - The command group with the specified ID, or `nil` if none exists.</li></ul>          |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | If enabled, the commands in the group will be active as well.                                                                                         |

#### [isEditable](#iseditable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.isEditable <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | If set to `false`, the command group is not user-editable.                                                                                         |

### Methods

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:new(id) -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a collection of commands. These commands can be enabled or disabled as a group.                                                                                         |
| **Parameters**                                       | <ul><li>`id`		- The unique ID for this command group.</li></ul> |
| **Returns**                                          | <ul><li>cp.commands - The commands group that was created.</li></ul>          |

