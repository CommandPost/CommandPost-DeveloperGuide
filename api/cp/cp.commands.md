# [docs](index.md) » cp.commands
---

Commands Module.

## Submodules
 * [cp.commands.command](cp.commands.command.md)
 * [cp.commands.englishKeyCodes](cp.commands.englishKeyCodes.md)
 * [cp.commands.shortcut](cp.commands.shortcut.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_EXTENSION](#default_extension)
* Functions - API calls offered directly by the extension
 * [getShortcutsPath](#getshortcutspath)
 * [group](#group)
 * [groupIds](#groupids)
 * [groups](#groups)
 * [loadFromFile](#loadfromfile)
 * [new](#new)
 * [saveToFile](#savetofile)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)
 * [isEditable](#iseditable)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activate](#activate)
 * [add](#add)
 * [clear](#clear)
 * [deleteShortcuts](#deleteshortcuts)
 * [disable](#disable)
 * [enable](#enable)
 * [get](#get)
 * [getAll](#getall)
 * [id](#id)
 * [loadShortcuts](#loadshortcuts)
 * [saveShortcuts](#saveshortcuts)
 * [watch](#watch)

## API Documentation

### Constants

#### [DEFAULT_EXTENSION](#default_extension)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.DEFAULT_EXTENSION -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The menubar position priority.                                                                                         |

### Functions

#### [getShortcutsPath](#getshortcutspath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.getShortcutsPath(name) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the path to the named shortcut set.                                                                                         |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.group(id) -> cp.command or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a collection of commands. These commands can be enabled or disabled as a group.                                                                                         |
| **Parameters**                                       | <ul><li><code>id</code>      - The ID to retrieve</li></ul>   |
| **Returns**                                          | <ul><li><code>cp.commands</code> - The command group with the specified ID, or <code>nil</code> if none exists.</li></ul>            |

#### [groupIds](#groupids)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.groupIds() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns an array of IDs of command groups which have been created.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>table</code> - The array of group IDs.</li></ul>            |

#### [groups](#groups)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.groups() -> table of cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table with the set of commands.                                                                                         |
| **Parameters**                                       | <ul><li><code>id</code>      - The ID to retrieve</li></ul>   |
| **Returns**                                          | <ul><li><code>cp.commands</code> - The command group with the specified ID, or <code>nil</code> if none exists.</li></ul>            |

#### [loadFromFile](#loadfromfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.loadFromFile(name) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Loads a shortcut set from the standard location with the specified name.                                                                                         |
| **Parameters**                                       | <ul><li>name      - The name of the shortcut set. E.g. "My Custom Shortcuts"</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if the file was found and loaded successfully.</li></ul>            |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.new(id) -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a collection of commands. These commands can be enabled or disabled as a group.                                                                                         |
| **Parameters**                                       | <ul><li><code>id</code>     - The unique ID for this command group.</li></ul>   |
| **Returns**                                          | <ul><li>cp.commands - The command group that was created.</li></ul>            |

#### [saveToFile](#savetofile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.saveToFile(name) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves the current shortcuts for all groups to a file in the standard location with the provided name.                                                                                         |
| **Parameters**                                       | <ul><li>name      - The name of the command set. E.g. "My Custom Commands"</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if the shortcuts were saved successfully.</li></ul>            |

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

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:activate(successFn, failureFn) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Will trigger an 'activate' event, and then execute either the `successFn` or `failureFn` if the                                                                                         |
| **Parameters**                                       | <ul><li>successFn     - the function to call if successfully activated.</li></ul><ul><li>failureFn     - the function to call if not activated after 5 seconds.</li></ul>   |
| **Returns**                                          | <ul><li>Nothing.</li></ul>            |

#### [add](#add)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:add(commandId) -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a new command with the specified ID to this group. Additional configuration                                                                                         |
| **Parameters**                                       | <ul><li><code>commandId</code>   - The unique ID for the new command.</li></ul>   |
| **Returns**                                          | <ul><li>The new <code>cp.commands.command</code> instance.</li></ul>            |

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:clear() -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Clears all commands and their shortcuts.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The command group instance.</li></ul>            |

#### [deleteShortcuts](#deleteshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:deleteShortcuts() -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Clears all shortcuts associated with commands in this command group.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The command group instance.</li></ul>            |

#### [disable](#disable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:disable() -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the command group.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The command group instance.</li></ul>            |

#### [enable](#enable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:enable() -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the command group.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The command group instance.</li></ul>            |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:get(commandId) -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the command with the specified ID, or `nil` if none exists.                                                                                         |
| **Parameters**                                       | <ul><li><code>commandId</code>   - The command ID to retrieve.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.commands.command</code>, or <code>nil</code>.</li></ul>            |

#### [getAll](#getall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:getAll() -> table of cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the table of commands, with the key being the ID and the value being the command instance. Eg:                                                                                         |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the unique ID of the command group.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The command group ID string.</li></ul>            |

#### [loadShortcuts](#loadshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:loadShortcuts(data) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads the shortcut details in the data table and applies them to the commands in this group.                                                                                         |
| **Parameters**                                       | <ul><li>data      - The data table containing shortcuts.</li></ul>   |
| **Returns**                                          | <ul><li>Nothing</li></ul>            |

#### [saveShortcuts](#saveshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:saveShortcuts() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table that is approprate to be saved to file that contains the shortuct                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The table of shortcuts for commands.</li></ul>            |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands:watch(events) -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an event watcher to the command group.                                                                                         |
| **Parameters**                                       | <ul><li>events    - The table of events to watch for (see Notes).</li></ul>   |
| **Returns**                                          | <ul><li>The command group instance.</li></ul>            |
| **Notes**                                            | <ul><li>The table can have properties with the following functions, which will be called for the specific event:</li></ul><p>** <code>add(command)</code>:      Called after the provided <code>cp.commands.command</code> instance has been added.</p><p>** <code>activate()</code>         Called when the command group is activated.</p><p>** <code>enable()</code>:          Called when the command group is enabled.</p><p>** <code>disable()</code>:         Called when the command group is disabled.</p>                 |

