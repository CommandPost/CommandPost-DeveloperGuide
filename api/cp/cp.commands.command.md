# [docs](index.md) » cp.commands.command
---

Commands Module.

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isActive](#isactive)
 * [isEnabled](#isenabled)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activated](#activated)
 * [activatedBy](#activatedby)
 * [addShortcut](#addshortcut)
 * [deleteShortcuts](#deleteshortcuts)
 * [disable](#disable)
 * [enable](#enable)
 * [getFirstShortcut](#getfirstshortcut)
 * [getGroup](#getgroup)
 * [getShortcuts](#getshortcuts)
 * [getSubtitle](#getsubtitle)
 * [getTitle](#gettitle)
 * [groupedBy](#groupedby)
 * [id](#id)
 * [new](#new)
 * [parent](#parent)
 * [pressed](#pressed)
 * [released](#released)
 * [repeated](#repeated)
 * [setShortcuts](#setshortcuts)
 * [subtitled](#subtitled)
 * [titled](#titled)
 * [whenActivated](#whenactivated)
 * [whenPressed](#whenpressed)
 * [whenReleased](#whenreleased)
 * [whenRepeated](#whenrepeated)

## API Documentation

### Fields

#### [isActive](#isactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command.isActive <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Indicates if the command is active. To be active, both the command and the group it belongs to must be enabled.                                                                                         |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command.isEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | If set to `true`, the command is enabled.                                                                                         |

### Methods

#### [activated](#activated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:activated(repeats) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'pressed', then 'repeated', then 'released' functions, if present.                                                                                         |
| **Parameters**                                       |  * `repeats`	- the number of times to repeat the 'repeated' function. Defaults to 1.                                       |
| **Returns**                                          |  * the last 'truthy' result (non-nil/false).                                                |

#### [activatedBy](#activatedby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:activatedBy([modifiers,] [keyCode]) -> command/modifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies that the command is activated by pressing a key combination.                                                                                         |
| **Parameters**                                       |  * `modifiers`	- (optional) The table containing names of required modifiers. * `keyCode`	- (optional) The key code that will activate the command, with no modifiers.                                       |
| **Returns**                                          |  * `command` if a `keyCode` was provided, or `modifier` if not.                                                |

#### [addShortcut](#addshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:addShortcut(newShortcut) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified shortcut to the command.                                                                                         |
| **Parameters**                                       |  * `newShortcut`	- the shortcut to add.                                       |
| **Returns**                                          |  * `self`                                                |

#### [deleteShortcuts](#deleteshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:deleteShortcuts() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is pressed.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * command - The current command                                                |

#### [disable](#disable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:disable() -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the command.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `cp.commands.command` instance.                                                |

#### [enable](#enable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:enable() -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the command.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `cp.commands.command` instance.                                                |

#### [getFirstShortcut](#getfirstshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getFirstShortcut() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the first shortcut, or `nil` if none have been registered.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The first shortcut, or `nil`.                                                |

#### [getGroup](#getgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getGroup() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the group ID for the command.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The group ID.                                                |

#### [getShortcuts](#getshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getShortcuts() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the set of shortcuts assigned to this command.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The associated shortcuts.                                                |

#### [getSubtitle](#getsubtitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getSubtitle() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current subtitle, based on either the set subtitle, or the "<ID>_subtitle" value in the I18N files.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The subtitle value or `nil`.                                                |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getTitle() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the command title in the current language, if availalbe. If not, the ID is returned.                                                                                         |
| **Parameters**                                       | * None                                       |

#### [groupedBy](#groupedby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:groupedBy(group) -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies that the command is grouped by a specific value.                                                                                         |
| **Parameters**                                       | * `group`	- The group ID.                                       |
| **Returns**                                          | * The `cp.commands.command` instance.                                                |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ID for this command.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The ID.                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command.new() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new command, which can have keyboard shortcuts assigned to it.                                                                                         |
| **Parameters**                                       |  * `id`		- the unique identifier for the command. E.g. 'cpCustomCommand' * `parent`	- The parent group.                                       |
| **Returns**                                          |  * command - The command that was created.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:parent() -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent command group.                                                                                         |
| **Parameters**                                       | * None                                       |

#### [pressed](#pressed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:pressed() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'pressed' function, if present.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the result of the function, or `nil` if none is present.                                                |

#### [released](#released)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:released() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'released' function, if present.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * the result of the function, or `nil` if none is present.                                                |

#### [repeated](#repeated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:repeated(repeats) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'repeated' function, if present.                                                                                         |
| **Parameters**                                       |  * `repeats`	- the number of times to repeat. Defaults to 1.                                       |
| **Returns**                                          |  * the last result.                                                |

#### [setShortcuts](#setshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:setShortcuts(shortcuts) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deletes any existing shortcuts and applies the new set of shortcuts in the table.                                                                                         |
| **Parameters**                                       | * shortcuts		- The set of `cp.commands.shortcuts` to apply to this command.                                       |
| **Returns**                                          | * The `cp.commands.command` instance.                                                |

#### [subtitled](#subtitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:subtitled(subtitle) -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the specified subtitle and returns the `cp.commands.command` instance.                                                                                         |
| **Parameters**                                       | * `subtitle`	- The new subtitle.                                       |

#### [titled](#titled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:titled(title) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies the provided human-readable title to the command.                                                                                         |
| **Parameters**                                       |  * `id`	= the unique identifier for the command. E.g. 'FCPXHacksCustomCommand'                                       |
| **Returns**                                          |  * command - The command that was created.                                                |

#### [whenActivated](#whenactivated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenActivated(activatedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command is activated.                                                                                         |
| **Parameters**                                       |  * `activatedFn`	- the function to call when activated.                                       |
| **Returns**                                          |  * command - The current command                                                |

#### [whenPressed](#whenpressed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenPressed(pressedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is pressed.                                                                                         |
| **Parameters**                                       |  * `pressedFn`	- the function to call when pressed.                                       |
| **Returns**                                          |  * command - The current command                                                |

#### [whenReleased](#whenreleased)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenReleased(releasedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is released.                                                                                         |
| **Parameters**                                       |  * `releasedFn`	- the function to call when released.                                       |
| **Returns**                                          |  * command - The current command                                                |

#### [whenRepeated](#whenrepeated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenRepeated(repeatedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is repeated.                                                                                         |
| **Parameters**                                       |  * `repeatedFn`	- the function to call when repeated.                                       |
| **Returns**                                          |  * command - The current command                                                |

