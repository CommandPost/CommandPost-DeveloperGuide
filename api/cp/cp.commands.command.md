# [docs](index.md) » cp.commands.command
---

Commands Module.

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isActive](#isactive)
 * [isEnabled](#isenabled)
* Methods - API calls which can only be made on an object returned by a constructor
 * [action](#action)
 * [activated](#activated)
 * [activatedBy](#activatedby)
 * [addShortcut](#addshortcut)
 * [deleteShortcuts](#deleteshortcuts)
 * [disable](#disable)
 * [enable](#enable)
 * [getAction](#getaction)
 * [getFirstShortcut](#getfirstshortcut)
 * [getGroup](#getgroup)
 * [getImage](#getimage)
 * [getShortcuts](#getshortcuts)
 * [getSubtitle](#getsubtitle)
 * [getTitle](#gettitle)
 * [groupedBy](#groupedby)
 * [hasAction](#hasaction)
 * [id](#id)
 * [image](#image)
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
| **Type**                                             | Field |
| **Description**                                      | Indicates if the command is active. To be active, both the command and the group it belongs to must be enabled. |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command.isEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | If set to `true`, the command is enabled. |

### Methods

#### [action](#action)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:action(getFn, setFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the action get and set callbacks for a specific command. |
| **Parameters**                                       | <ul><li>getFn - The function that gets the action.</li><li>setFn - The function that sets the action.</li></ul> |
| **Returns**                                          | <ul><li>command - The command that was created.</li></ul> |
| **Notes**                                            | <ul><li>The <code>getFn</code> function should have no arguments.</li><li>The <code>setFn</code> function can have two optional arguments:</li><li><code>clear</code> - A boolean that defines whether or not the value should be cleared.</li><li><code>completionFn</code> - An optional completion function callback.</li></ul> |

#### [activated](#activated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:activated(repeats) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the 'pressed', then 'repeated', then 'released' functions, if present. |
| **Parameters**                                       | <ul><li><code>repeats</code>    - the number of times to repeat the 'repeated' function. Defaults to 1.</li></ul> |
| **Returns**                                          | <ul><li>the last 'truthy' result (non-nil/false).</li></ul> |

#### [activatedBy](#activatedby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:activatedBy([modifiers,] [keyCode]) -> command/modifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies that the command is activated by pressing a key combination. |
| **Parameters**                                       | <ul><li><code>modifiers</code>  - (optional) The table containing names of required modifiers.</li><li><code>keyCode</code>    - (optional) The key code that will activate the command, with no modifiers.</li></ul> |
| **Returns**                                          | <ul><li><code>command</code> if a <code>keyCode</code> was provided, or <code>modifier</code> if not.</li></ul> |

#### [addShortcut](#addshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:addShortcut(newShortcut) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds the specified shortcut to the command. |
| **Parameters**                                       | <ul><li><code>newShortcut</code>    - the shortcut to add.</li></ul> |
| **Returns**                                          | <ul><li><code>self</code></li></ul> |

#### [deleteShortcuts](#deleteshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:deleteShortcuts() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the command key combo is pressed. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul> |

#### [disable](#disable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:disable() -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Disables the command. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.commands.command</code> instance.</li></ul> |

#### [enable](#enable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:enable() -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Enables the command. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.commands.command</code> instance.</li></ul> |

#### [getAction](#getaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getAction() -> function, function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the action get and set callbacks for a specific command. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>getFn - The function that gets the action.</li><li>setFn - The function that sets the action.</li></ul> |

#### [getFirstShortcut](#getfirstshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getFirstShortcut() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the first shortcut, or `nil` if none have been registered. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The first shortcut, or <code>nil</code>.</li></ul> |

#### [getGroup](#getgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getGroup() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the group ID for the command. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The group ID.</li></ul> |

#### [getImage](#getimage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getImage() -> hs.image object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the current image. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A hs.image object or <code>nil</code> if not is specified.</li></ul> |

#### [getShortcuts](#getshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getShortcuts() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the set of shortcuts assigned to this command. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The associated shortcuts.</li></ul> |

#### [getSubtitle](#getsubtitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getSubtitle() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the current subtitle, based on either the set subtitle, or the "<ID>_subtitle" value in the I18N files. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The subtitle value or <code>nil</code>.</li></ul> |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:getTitle() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the command title in the current language, if availalbe. If not, the ID is returned. |
| **Parameters**                                       | <ul><li>None</li></ul> |

#### [groupedBy](#groupedby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:groupedBy(group) -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies that the command is grouped by a specific value. |
| **Parameters**                                       | <ul><li><code>group</code>  - The group ID.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.commands.command</code> instance.</li></ul> |

#### [hasAction](#hasaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:hasAction() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets whether or not any action callbacks have been assigned. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if action callbacks have been assigned, otherwise <code>false</code>.</li></ul> |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the ID for this command. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The ID.</li></ul> |

#### [image](#image)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:image(img) -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the specified image and returns the `cp.commands.command` instance. |
| **Parameters**                                       | <ul><li><code>img</code> - The <code>hs.image</code> to use.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.commands.command</code> instance.</li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command.new() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new command, which can have keyboard shortcuts assigned to it. |
| **Parameters**                                       | <ul><li><code>id</code>     - the unique identifier for the command. E.g. 'cpCustomCommand'</li><li><code>parent</code> - The parent group.</li></ul> |
| **Returns**                                          | <ul><li>command - The command that was created.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:parent() -> cp.commands` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the parent command group. |
| **Parameters**                                       | <ul><li>None</li></ul> |

#### [pressed](#pressed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:pressed() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the 'pressed' function, if present. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the result of the function, or <code>nil</code> if none is present.</li></ul> |

#### [released](#released)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:released() -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the 'released' function, if present. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the result of the function, or <code>nil</code> if none is present.</li></ul> |

#### [repeated](#repeated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:repeated(repeats) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the 'repeated' function, if present. |
| **Parameters**                                       | <ul><li><code>repeats</code>    - the number of times to repeat. Defaults to 1.</li></ul> |
| **Returns**                                          | <ul><li>the last result.</li></ul> |

#### [setShortcuts](#setshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:setShortcuts(shortcuts) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Deletes any existing shortcuts and applies the new set of shortcuts in the table. |
| **Parameters**                                       | <ul><li>shortcuts        - The set of <code>cp.commands.shortcuts</code> to apply to this command.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.commands.command</code> instance.</li></ul> |

#### [subtitled](#subtitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:subtitled(subtitle) -> cp.commands.command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the specified subtitle and returns the `cp.commands.command` instance. |
| **Parameters**                                       | <ul><li><code>subtitle</code>   - The new subtitle.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.commands.command</code> instance.</li></ul> |

#### [titled](#titled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:titled(title) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Applies the provided human-readable title to the command. |
| **Parameters**                                       | <ul><li>id - the unique identifier for the command (i.e. 'CPCustomCommand').</li></ul> |
| **Returns**                                          | <ul><li>command - The command that was created.</li></ul> |

#### [whenActivated](#whenactivated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenActivated(activatedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the command is activated. |
| **Parameters**                                       | <ul><li><code>activatedFn</code>    - the function to call when activated.</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul> |

#### [whenPressed](#whenpressed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenPressed(pressedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the command key combo is pressed. |
| **Parameters**                                       | <ul><li><code>pressedFn</code>  - the function to call when pressed.</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul> |

#### [whenReleased](#whenreleased)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenReleased(releasedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the command key combo is released. |
| **Parameters**                                       | <ul><li><code>releasedFn</code> - the function to call when released.</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul> |

#### [whenRepeated](#whenrepeated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.commands.command:whenRepeated(repeatedFn) -> command` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the command key combo is repeated. |
| **Parameters**                                       | <ul><li><code>repeatedFn</code> - the function to call when repeated.</li></ul> |
| **Returns**                                          | <ul><li>command - The current command</li></ul> |

