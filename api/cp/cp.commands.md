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
* Methods - API calls which can only be made on an object returned by a constructor
 * [new](#new)

## API Documentation

### Functions

#### [group](#group)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.group(id) -> cp.command or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a collection of commands. These commands can be enabled or disabled as a group.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`		- The ID to retrieve</li></ul> |
| **Returns**                                          | <ul><li>`cp.commands` - The command group with the specified ID, or `nil` if none exists.</li></ul>          |

#### [groupIds](#groupids)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.groupIds() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an array of IDs of command groups which have been created.                                                                                         |
| **Parameters**                                       | <ul><li>* N/A</li></ul> |
| **Returns**                                          | <ul><li>`table` - The array of group IDs.</li></ul>          |

### Methods

#### [new](#new)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands:new(id) -> cp.commands` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a collection of commands. These commands can be enabled or disabled as a group.                                                                                         |
| **Parameters**                                       | <ul><li>`id`		- The unique ID for this command group.</li></ul> |
| **Returns**                                          | <ul><li>cp.commands - The commands group that was created.</li></ul>          |

