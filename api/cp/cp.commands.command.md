# [docs](index.md) » cp.commands.command
---

Commands Module.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [activated](#activated)
 * [activatedBy](#activatedby)
 * [addShortcut](#addshortcut)
 * [deleteShortcuts](#deleteshortcuts)
 * [getShortcuts](#getshortcuts)
 * [new](#new)
 * [pressed](#pressed)
 * [released](#released)
 * [repeated](#repeated)
 * [titled](#titled)
 * [whenActivated](#whenactivated)
 * [whenPressed](#whenpressed)
 * [whenReleased](#whenreleased)
 * [whenRepeated](#whenrepeated)

## API Documentation

### Methods

#### [activated](#activated)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:activated(repeats) -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'pressed', then 'repeated', then 'released' functions, if present.                                                                                         |
| **Parameters**                                       | <ul><li>`repeats`	- the number of times to repeat the 'repeated' function. Defaults to 1.</li></ul> |
| **Returns**                                          | <ul><li>the last 'truthy' result (non-nil/false).</li></ul>          |

#### [activatedBy](#activatedby)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:activatedBy([modifiers,] [keyCode]) -> command/modifier` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies that the command is activated by pressing a key combination.                                                                                         |
| **Parameters**                                       | <ul><li>`modifiers`	- (optional) The table containing names of required modifiers.</li><li>`keyCode`	- (optional) The key code that will activate the command, with no modifiers.</li></ul> |
| **Returns**                                          | <ul><li>`command` if a `keyCode` was provided, or `modifier` if not.</li></ul>          |

#### [addShortcut](#addshortcut)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:addShortcut() -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified shortcut to the command.                                                                                         |
| **Parameters**                                       | <ul><li>`newShortcut`	- the shortcut</li></ul> |
| **Returns**                                          | <ul><li>`self`</li></ul>          |

#### [deleteShortcuts](#deleteshortcuts)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:deleteShortcuts() -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is pressed.                                                                                         |
| **Parameters**                                       | <ul><li>N/A</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul>          |

#### [getShortcuts](#getshortcuts)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:getShortcuts() -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the set of shortcuts assigned to this command.                                                                                         |
| **Parameters**                                       | <ul><li>N/A</li></ul> |
| **Returns**                                          | <ul><li>The associated shortcuts.</li></ul>          |

#### [new](#new)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:new() -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new menu command, which can have items and sub-menus added to it.                                                                                         |
| **Parameters**                                       | <ul><li>`id`	= the unique identifier for the command. E.g. 'FCPXHacksCustomCommand'</li></ul> |
| **Returns**                                          | <ul><li>command - The command that was created.</li></ul>          |

#### [pressed](#pressed)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:pressed() -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'pressed' function, if present.                                                                                         |
| **Parameters**                                       | <ul><li>N/A</li></ul> |
| **Returns**                                          | <ul><li>the result of the function, or `nil` if none is present.</li></ul>          |

#### [released](#released)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:released() -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'released' function, if present.                                                                                         |
| **Parameters**                                       | <ul><li>N/A</li></ul> |
| **Returns**                                          | <ul><li>the result of the function, or `nil` if none is present.</li></ul>          |

#### [repeated](#repeated)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:repeated(repeats) -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'repeated' function, if present.                                                                                         |
| **Parameters**                                       | <ul><li>`repeats`	- the number of times to repeat. Defaults to 1.</li></ul> |
| **Returns**                                          | <ul><li>the last result.</li></ul>          |

#### [titled](#titled)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:titled(title) -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies the provided human-readable title to the command.                                                                                         |
| **Parameters**                                       | <ul><li>`id`	= the unique identifier for the command. E.g. 'FCPXHacksCustomCommand'</li></ul> |
| **Returns**                                          | <ul><li>command - The command that was created.</li></ul>          |

#### [whenActivated](#whenactivated)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:whenActivated(function) -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command is activated.                                                                                         |
| **Parameters**                                       | <ul><li>`activatedFn`	- the function to call when activated.</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul>          |

#### [whenPressed](#whenpressed)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:whenPressed(function) -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is pressed.                                                                                         |
| **Parameters**                                       | <ul><li>`pressedFn`	- the function to call when pressed.</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul>          |

#### [whenReleased](#whenreleased)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:whenReleased(function) -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is released.                                                                                         |
| **Parameters**                                       | <ul><li>`releasedFn`	- the function to call when released.</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul>          |

#### [whenRepeated](#whenrepeated)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.commands.command:whenRepeated(function) -> command` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is repeated.                                                                                         |
| **Parameters**                                       | <ul><li>`repeatedFn`	- the function to call when repeated.</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul>          |

