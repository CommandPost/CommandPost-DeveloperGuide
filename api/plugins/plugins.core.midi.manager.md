# [docs](index.md) » plugins.core.midi.manager
---

MIDI Manager Plugin.

## Submodules
 * [plugins.core.midi.manager.controls](plugins.core.midi.manager.controls.md)
 * [plugins.core.midi.manager.default](plugins.core.midi.manager.default.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_GROUP](#default_group)
 * [DEFAULT_MIDI_CONTROLS](#default_midi_controls)
 * [FILE_NAME](#file_name)
 * [FOLDER_NAME](#folder_name)
* Variables - Configurable values
 * [learningMode](#learningmode)
 * [maxItems](#maxitems)
 * [numberOfSubGroups](#numberofsubgroups)
* Functions - API calls offered directly by the extension
 * [activeGroup](#activegroup)
 * [activeSubGroup](#activesubgroup)
 * [clear](#clear)
 * [devices](#devices)
 * [forceGroupChange](#forcegroupchange)
 * [getDevice](#getdevice)
 * [getItem](#getitem)
 * [getItems](#getitems)
 * [gotoSubGroup](#gotosubgroup)
 * [groupStatus](#groupstatus)
 * [init](#init)
 * [midiCallback](#midicallback)
 * [nextSubGroup](#nextsubgroup)
 * [previousSubGroup](#previoussubgroup)
 * [setItem](#setitem)
 * [start](#start)
 * [update](#update)
 * [updateAction](#updateaction)
 * [virtualDevices](#virtualdevices)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)
 * [numberOfMidiDevices](#numberofmididevices)

## API Documentation

### Constants

#### [DEFAULT_GROUP](#default_group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.DEFAULT_GROUP -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The default group. |

#### [DEFAULT_MIDI_CONTROLS](#default_midi_controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.DEFAULT_MIDI_CONTROLS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The default MIDI controls, so that the user has a starting point. |

#### [FILE_NAME](#file_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.FILE_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | File name of settings file. |

#### [FOLDER_NAME](#folder_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.FOLDER_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Folder Name where settings file is contained. |

### Variables

#### [learningMode](#learningmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.learningMode -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Whether or not the MIDI Manager is in learning mode. |

#### [maxItems](#maxitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.maxItems -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The maximum number of MIDI items per group. |

#### [numberOfSubGroups](#numberofsubgroups)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.numberOfSubGroups -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The number of Sub Groups per Touch Bar Group. |

### Functions

#### [activeGroup](#activegroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.activeGroup() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the active group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns the active group or <code>manager.defaultGroup</code> as a string.</li></ul> |

#### [activeSubGroup](#activesubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.activeSubGroup() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the active sub-group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns the active sub group as string</li></ul> |

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.clear() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Clears the MIDI items. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [devices](#devices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.devices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a table of Physical MIDI Device Names. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of Physical MIDI Device Names.</li></ul> |

#### [forceGroupChange](#forcegroupchange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.forceGroupChange(combinedGroupAndSubGroupID) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Loads a specific sub-group. |
| **Parameters**                                       | <ul><li>combinedGroupAndSubGroupID - The group and subgroup as a single string.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getDevice](#getdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.getDevice(deviceName, virtual) -> hs.midi object | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a MIDI Device. |
| **Parameters**                                       | <ul><li>deviceName - The device name.</li><li>virtual - A boolean that defines whether or not the device is virtual.</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs.midi</code> object or nil if no MIDI device by that name exists.</li></ul> |

#### [getItem](#getitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.getItem(item, button, group) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a MIDI item from Preferences. |
| **Parameters**                                       | <ul><li>item - The item you want to get.</li><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>A table otherwise <code>nil</code></li></ul> |

#### [getItems](#getitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.getItems() -> tables` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets all the MIDI items in a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [gotoSubGroup](#gotosubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.gotoSubGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Loads a specific sub-group. |
| **Parameters**                                       | <ul><li>id - The ID of the sub-group.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [groupStatus](#groupstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.groupStatus(groupID, status) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates a group's visibility status. |
| **Parameters**                                       | <ul><li>groupID - the group you want to update as a string.</li><li>status - the status of the group as a boolean.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.init(deps, env) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the MIDI Plugin |
| **Parameters**                                       | <ul><li>deps - Dependencies Table</li><li>env - Environment Table</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [midiCallback](#midicallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.midiCallback(object, deviceName, commandType, description, metadata) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | MIDI Callback |
| **Parameters**                                       | <ul><li>object - The <code>hs.midi</code> userdata object</li><li>deviceName - Device name as string</li><li>commandType - Command Type as string</li><li>description - Description as string</li><li>metadata - A table containing metadata for the MIDI command</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [nextSubGroup](#nextsubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.nextSubGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Goes to the next sub-group for the active group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [previousSubGroup](#previoussubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.previousSubGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Goes to the previous sub-group for the active group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setItem](#setitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.setItem(item, button, group, value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stores a MIDI item in Preferences. |
| **Parameters**                                       | <ul><li>item - The item you want to set.</li><li>button - Button ID as string</li><li>group - Group ID as string</li><li>value - The value of the item you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.start() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stops the MIDI Plugin |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the MIDI Watchers. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateAction](#updateaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.updateAction(button, group, actionTitle, handlerID, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates a MIDI action. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li><li>actionTitle - Action Title as string</li><li>handlerID - Handler ID as string</li><li>action - Action in a table</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [virtualDevices](#virtualdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.virtualDevices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a table of Virtual MIDI Source Names. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of Virtual MIDI Source Names.</li></ul> |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable MIDI Support. |

#### [numberOfMidiDevices](#numberofmididevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.numberOfMidiDevices -> <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Total number of MIDI Devices detected (including both physical and virtual). |

