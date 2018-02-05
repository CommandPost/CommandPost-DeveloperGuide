# [docs](index.md) » plugins.core.midi.manager
---

MIDI Manager Plugin.

## Submodules
 * [plugins.core.midi.manager.controls](plugins.core.midi.manager.controls.md)

## API Overview
* Variables - Configurable values
 * [defaultGroup](#defaultgroup)
 * [maxItems](#maxitems)
* Functions - API calls offered directly by the extension
 * [activeGroup](#activegroup)
 * [clear](#clear)
 * [devices](#devices)
 * [getItem](#getitem)
 * [getItems](#getitems)
 * [groupStatus](#groupstatus)
 * [init](#init)
 * [midiCallback](#midicallback)
 * [setItem](#setitem)
 * [start](#start)
 * [update](#update)
 * [updateAction](#updateaction)
 * [virtualDevices](#virtualdevices)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [buttons](#buttons)
 * [enabled](#enabled)

## API Documentation

### Variables

#### [defaultGroup](#defaultgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.defaultGroup -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The default group.                                                                                         |

#### [maxItems](#maxitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.maxItems -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The maximum number of MIDI items per group.                                                                                         |

### Functions

#### [activeGroup](#activegroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.activeGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the active group.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns the active group or `manager.defaultGroup` as a string.</li></ul>          |

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.clear() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Clears the MIDI items.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [devices](#devices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.devices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a table of Physical MIDI Device Names.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of Physical MIDI Device Names.</li></ul>          |

#### [getItem](#getitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.getItem(item, button, group) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a MIDI item from Preferences.                                                                                         |
| **Parameters**                                       | <ul><li>item - The item you want to get.</li><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>A table otherwise `nil`</li></ul>          |

#### [getItems](#getitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.getItems() -> tables` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all the MIDI items in a table.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul>          |

#### [groupStatus](#groupstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.groupStatus(groupID, status) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a group's visibility status.                                                                                         |
| **Parameters**                                       | <ul><li>groupID - the group you want to update as a string.</li><li>status - the status of the group as a boolean.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.init(deps, env) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the MIDI Plugin                                                                                         |
| **Parameters**                                       | <ul><li>deps - Dependencies Table</li><li>env - Environment Table</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [midiCallback](#midicallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.midiCallback(object, deviceName, commandType, description, metadata) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | MIDI Callback                                                                                         |
| **Parameters**                                       | <ul><li>object - The `hs.midi` userdata object</li><li>deviceName - Device name as string</li><li>commandType - Command Type as string</li><li>description - Description as string</li><li>metadata - A table containing metadata for the MIDI command</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setItem](#setitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.setItem(item, button, group, value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stores a MIDI item in Preferences.                                                                                         |
| **Parameters**                                       | <ul><li>item - The item you want to set.</li><li>button - Button ID as string</li><li>group - Group ID as string</li><li>value - The value of the item you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.start() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the MIDI Plugin                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the MIDI Watchers.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [updateAction](#updateaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.updateAction(button, group, actionTitle, handlerID, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a MIDI action.                                                                                         |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li><li>actionTitle - Action Title as string</li><li>handlerID - Handler ID as string</li><li>action - Action in a table</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [virtualDevices](#virtualdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.virtualDevices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a table of Virtual MIDI Source Names.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of Virtual MIDI Source Names.</li></ul>          |

### Fields

#### [buttons](#buttons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.buttons <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Contains all the saved MIDI items                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Enable or disable MIDI Support.                                                                                         |

