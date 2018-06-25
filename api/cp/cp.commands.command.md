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
| **Parameters**                                       | <ul><br /><li><code>repeats</code>    - the number of times to repeat the 'repeated' function. Defaults to 1.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the last 'truthy' result (non-nil/false).</li><br /></ul>                                           |

#### [activatedBy](#activatedby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:activatedBy([modifiers,] [keyCode]) -> command/modifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies that the command is activated by pressing a key combination.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>modifiers</code>  - (optional) The table containing names of required modifiers. * <code>keyCode</code>  - (optional) The key code that will activate the command, with no modifiers.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>command</code> if a <code>keyCode</code> was provided, or <code>modifier</code> if not.</li><br /></ul>                                           |

#### [addShortcut](#addshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:addShortcut(newShortcut) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the specified shortcut to the command.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>newShortcut</code>    - the shortcut to add.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>self</code></li><br /></ul>                                           |

#### [deleteShortcuts](#deleteshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:deleteShortcuts() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is pressed.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>command - The current command</li><br /></ul>                                           |

#### [disable](#disable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:disable() -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the command.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>cp.commands.command</code> instance.</li><br /></ul>                                           |

#### [enable](#enable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:enable() -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the command.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>cp.commands.command</code> instance.</li><br /></ul>                                           |

#### [getFirstShortcut](#getfirstshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getFirstShortcut() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the first shortcut, or `nil` if none have been registered.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The first shortcut, or <code>nil</code>.</li><br /></ul>                                           |

#### [getGroup](#getgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getGroup() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the group ID for the command.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The group ID.</li><br /></ul>                                           |

#### [getShortcuts](#getshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getShortcuts() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the set of shortcuts assigned to this command.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The associated shortcuts.</li><br /></ul>                                           |

#### [getSubtitle](#getsubtitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getSubtitle() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current subtitle, based on either the set subtitle, or the "<ID>_subtitle" value in the I18N files.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The subtitle value or <code>nil</code>.</li><br /></ul>                                           |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getTitle() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the command title in the current language, if availalbe. If not, the ID is returned.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |

#### [groupedBy](#groupedby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:groupedBy(group) -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies that the command is grouped by a specific value.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>group</code>   - The group ID.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>cp.commands.command</code> instance.</li><br /></ul>                                           |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ID for this command.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The ID.</li><br /></ul>                                           |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command.new() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new command, which can have keyboard shortcuts assigned to it.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>     - the unique identifier for the command. E.g. 'cpCustomCommand' * <code>parent</code>  - The parent group.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>command - The command that was created.</li><br /></ul>                                           |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:parent() -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent command group.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |

#### [pressed](#pressed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:pressed() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'pressed' function, if present.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the result of the function, or <code>nil</code> if none is present.</li><br /></ul>                                           |

#### [released](#released)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:released() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'released' function, if present.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the result of the function, or <code>nil</code> if none is present.</li><br /></ul>                                           |

#### [repeated](#repeated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:repeated(repeats) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the 'repeated' function, if present.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>repeats</code>    - the number of times to repeat. Defaults to 1.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the last result.</li><br /></ul>                                           |

#### [setShortcuts](#setshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:setShortcuts(shortcuts) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deletes any existing shortcuts and applies the new set of shortcuts in the table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>shortcuts     - The set of <code>cp.commands.shortcuts</code> to apply to this command.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>cp.commands.command</code> instance.</li><br /></ul>                                           |

#### [subtitled](#subtitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:subtitled(subtitle) -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the specified subtitle and returns the `cp.commands.command` instance.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>subtitle</code>    - The new subtitle.</li><br /></ul>                                        |

#### [titled](#titled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:titled(title) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies the provided human-readable title to the command.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code> = the unique identifier for the command. E.g. 'FCPXHacksCustomCommand'</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>command - The command that was created.</li><br /></ul>                                           |

#### [whenActivated](#whenactivated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenActivated(activatedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command is activated.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>activatedFn</code>    - the function to call when activated.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>command - The current command</li><br /></ul>                                           |

#### [whenPressed](#whenpressed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenPressed(pressedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is pressed.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>pressedFn</code>  - the function to call when pressed.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>command - The current command</li><br /></ul>                                           |

#### [whenReleased](#whenreleased)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenReleased(releasedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is released.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>releasedFn</code> - the function to call when released.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>command - The current command</li><br /></ul>                                           |

#### [whenRepeated](#whenrepeated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenRepeated(repeatedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the command key combo is repeated.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>repeatedFn</code> - the function to call when repeated.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>command - The current command</li><br /></ul>                                           |

