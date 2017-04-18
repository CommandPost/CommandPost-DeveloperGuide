# [docs](index.md) » cp.commands.command
---

Commands Module.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [activated](#activated)
 * [activatedBy](#activatedBy)
 * [addShortcut](#addShortcut)
 * [deleteShortcuts](#deleteShortcuts)
 * [getShortcuts](#getShortcuts)
 * [new](#new)
 * [pressed](#pressed)
 * [released](#released)
 * [repeated](#repeated)
 * [titled](#titled)
 * [whenActivated](#whenActivated)
 * [whenPressed](#whenPressed)
 * [whenReleased](#whenReleased)
 * [whenRepeated](#whenRepeated)

## API Documentation

### Methods

#### [activated](#activated)
| **Signature**                               | `cp.commands.command:activated(repeats) -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Executes the 'pressed', then 'repeated', then 'released' functions, if present.                                                                     |
| **Parameters**                              | <ul><li>`repeats`	- the number of times to repeat the 'repeated' function. Defaults to 1.</li></ul> |
| **Returns**                                 | <ul><li>the last 'truthy' result (non-nil/false).</li></ul>          |

#### [activatedBy](#activatedBy)
| **Signature**                               | `cp.commands.command:activatedBy([modifiers,] [keyCode]) -> command/modifier`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Specifies that the command is activated by pressing a key combination.                                                                     |
| **Parameters**                              | <ul><li>`modifiers`	- (optional) The table containing names of required modifiers.</li><li>`keyCode`	- (optional) The key code that will activate the command, with no modifiers.</li></ul> |
| **Returns**                                 | <ul><li>`command` if a `keyCode` was provided, or `modifier` if not.</li></ul>          |

#### [addShortcut](#addShortcut)
| **Signature**                               | `cp.commands.command:addShortcut() -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds the specified shortcut to the command.                                                                     |
| **Parameters**                              | <ul><li>`newShortcut`	- the shortcut</li></ul> |
| **Returns**                                 | <ul><li>`self`</li></ul>          |

#### [deleteShortcuts](#deleteShortcuts)
| **Signature**                               | `cp.commands.command:deleteShortcuts() -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the function that will be called when the command key combo is pressed.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>command - The current command</li></ul>          |

#### [getShortcuts](#getShortcuts)
| **Signature**                               | `cp.commands.command:getShortcuts() -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the set of shortcuts assigned to this command.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>The associated shortcuts.</li></ul>          |

#### [new](#new)
| **Signature**                               | `cp.commands.command:new() -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Creates a new menu command, which can have items and sub-menus added to it.                                                                     |
| **Parameters**                              | <ul><li>`id`	= the unique identifier for the command. E.g. 'FCPXHacksCustomCommand'</li></ul> |
| **Returns**                                 | <ul><li>command - The command that was created.</li></ul>          |

#### [pressed](#pressed)
| **Signature**                               | `cp.commands.command:pressed() -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Executes the 'pressed' function, if present.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the result of the function, or `nil` if none is present.</li></ul>          |

#### [released](#released)
| **Signature**                               | `cp.commands.command:released() -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Executes the 'released' function, if present.                                                                     |
| **Parameters**                              | <ul><li>N/A</li></ul> |
| **Returns**                                 | <ul><li>the result of the function, or `nil` if none is present.</li></ul>          |

#### [repeated](#repeated)
| **Signature**                               | `cp.commands.command:repeated(repeats) -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Executes the 'repeated' function, if present.                                                                     |
| **Parameters**                              | <ul><li>`repeats`	- the number of times to repeat. Defaults to 1.</li></ul> |
| **Returns**                                 | <ul><li>the last result.</li></ul>          |

#### [titled](#titled)
| **Signature**                               | `cp.commands.command:titled(title) -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Applies the provided human-readable title to the command.                                                                     |
| **Parameters**                              | <ul><li>`id`	= the unique identifier for the command. E.g. 'FCPXHacksCustomCommand'</li></ul> |
| **Returns**                                 | <ul><li>command - The command that was created.</li></ul>          |

#### [whenActivated](#whenActivated)
| **Signature**                               | `cp.commands.command:whenActivated(function) -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the function that will be called when the command is activated.                                                                     |
| **Parameters**                              | <ul><li>`activatedFn`	- the function to call when activated.</li></ul> |
| **Returns**                                 | <ul><li>command - The current command</li></ul>          |

#### [whenPressed](#whenPressed)
| **Signature**                               | `cp.commands.command:whenPressed(function) -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the function that will be called when the command key combo is pressed.                                                                     |
| **Parameters**                              | <ul><li>`pressedFn`	- the function to call when pressed.</li></ul> |
| **Returns**                                 | <ul><li>command - The current command</li></ul>          |

#### [whenReleased](#whenReleased)
| **Signature**                               | `cp.commands.command:whenReleased(function) -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the function that will be called when the command key combo is released.                                                                     |
| **Parameters**                              | <ul><li>`releasedFn`	- the function to call when released.</li></ul> |
| **Returns**                                 | <ul><li>command - The current command</li></ul>          |

#### [whenRepeated](#whenRepeated)
| **Signature**                               | `cp.commands.command:whenRepeated(function) -> command`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the function that will be called when the command key combo is repeated.                                                                     |
| **Parameters**                              | <ul><li>`repeatedFn`	- the function to call when repeated.</li></ul> |
| **Returns**                                 | <ul><li>command - The current command</li></ul>          |

