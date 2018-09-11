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
 * [MMC_COMMAND_TYPE](#mmc_command_type)
 * [MMC_TIMECODE_TYPE](#mmc_timecode_type)
 * [MTC_COMMAND_TYPE](#mtc_command_type)
 * [MTC_MESSAGE_TYPE](#mtc_message_type)
 * [MTC_TIMECODE_TYPE](#mtc_timecode_type)
* Variables - Configurable values
 * [learningMode](#learningmode)
 * [maxItems](#maxitems)
 * [numberOfSubGroups](#numberofsubgroups)
* Functions - API calls offered directly by the extension
 * [activeGroup](#activegroup)
 * [activeSubGroup](#activesubgroup)
 * [clear](#clear)
 * [devices](#devices)
 * [forcefullyWatchMIDIDevices](#forcefullywatchmididevices)
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
 * [processMMC](#processmmc)
 * [processMTC](#processmtc)
 * [registerCallback](#registercallback)
 * [registerListenMMCFunction](#registerlistenmmcfunction)
 * [registerListenMTCFunction](#registerlistenmtcfunction)
 * [sendMMC](#sendmmc)
 * [setItem](#setitem)
 * [start](#start)
 * [update](#update)
 * [updateAction](#updateaction)
 * [virtualDevices](#virtualdevices)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [buttons](#buttons)
 * [enabled](#enabled)
 * [listenMMC](#listenmmc)
 * [listenMMCDevice](#listenmmcdevice)
 * [listenMTC](#listenmtc)
 * [listenMTCDevice](#listenmtcdevice)
 * [transmitMMC](#transmitmmc)
 * [transmitMMCDevice](#transmitmmcdevice)
 * [transmitMTC](#transmitmtc)
 * [transmitMTCDevice](#transmitmtcdevice)

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

#### [MMC_COMMAND_TYPE](#mmc_command_type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.MMC_COMMAND_TYPE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | MMC Command Types |

#### [MMC_TIMECODE_TYPE](#mmc_timecode_type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.MMC_TIMECODE_TYPE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | MMC Timecode Type |

#### [MTC_COMMAND_TYPE](#mtc_command_type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.MTC_COMMAND_TYPE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | MTC Command Type |

#### [MTC_MESSAGE_TYPE](#mtc_message_type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.MTC_MESSAGE_TYPE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | MTC Message Types |

#### [MTC_TIMECODE_TYPE](#mtc_timecode_type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.MTC_TIMECODE_TYPE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | MTC Timecode Type |

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

#### [forcefullyWatchMIDIDevices](#forcefullywatchmididevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.forcefullyWatchMIDIDevices(devices) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Forces CommandPost to watch a table of MIDI devices. |
| **Parameters**                                       | <ul><li>devices - A table containing all the device names you want to always watch.</li></ul> |
| **Returns**                                          | <ul><li>A table of Virtual MIDI Source Names.</li></ul> |

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

#### [processMMC](#processmmc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.processMMC(sysexData) -> string, ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Process MMC Data |
| **Parameters**                                       | <ul><li>sysexData - Sysex Data as Hex String</li></ul> |
| **Returns**                                          | <ul><li>A string with the MMC command, and any additional parameters as per below notes.</li></ul> |
| **Notes**                                            | <ul><li>The possible MMC commands are:</li><li>STOP</li><li>PLAY</li><li>DEFERRED_PLAY</li><li>FAST_FORWARD</li><li>REWIND</li><li>RECORD_STROBE</li><li>RECORD_EXIT</li><li>RECORD_PAUSE</li><li>PAUSE</li><li>EJECT</li><li>CHASE</li><li>MMC_RESET</li><li>WRITE</li><li>GOTO<ul><li>timecode - Timecode as string, in the following format: "hh:mm:ss:fr" (i.e. "12:03:03:13").</li><li>frameRate - Frame Rate as string, possible options include: "24", "25", "30 DF" or "30 NDF".</li><li>subframe - Subframe as string.</li></ul></li><li>ERROR</li><li>SHUTTLE</li></ul> |

#### [processMTC](#processmtc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.processMTC(mtcData) -> string, ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Process MTC Data |
| **Parameters**                                       | <ul><li>mtcData - MTC Data as Hex String</li></ul> |
| **Returns**                                          | <ul><li>A string with the MTC command, and any additional parameters.</li></ul> |

#### [registerCallback](#registercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.registerCallback(id, fn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Registers a MIDI Callback. |
| **Parameters**                                       | <ul><li>id - The ID as a string.</li><li>fn - The function you want to trigger.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [registerListenMMCFunction](#registerlistenmmcfunction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.registerListenMMCFunction(id, fn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Registers a MMC Listening Function |
| **Parameters**                                       | <ul><li>id - The group ID as a string.</li><li>fn - The function you want to trigger.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [registerListenMTCFunction](#registerlistenmtcfunction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.registerListenMTCFunction(id, fn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Registers a MTC Listening Function |
| **Parameters**                                       | <ul><li>id - The group ID as a string.</li><li>fn - The function you want to trigger.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [sendMMC](#sendmmc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.sendMMC(deviceName, virtual, commandType, parameters) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends MMC Data to a MIDI Device. |
| **Parameters**                                       | <ul><li>deviceName - The MIDI Device name.</li><li>virtual - Is this MIDI Device virtual as boolean?</li><li>channelNumber - "00" to "7F", where "7F" is all devices.</li><li>commandType - Command Type as string (see possible options in Notes below)</li><li>parameters - Optional parameters in a table.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully sent otherwise <code>false</code>.</li></ul> |
| **Notes**                                            | <ul><li>The possible MMC commands are:</li><li>STOP</li><li>PLAY</li><li>DEFERRED_PLAY</li><li>FAST_FORWARD</li><li>REWIND</li><li>RECORD_STROBE</li><li>RECORD_EXIT</li><li>RECORD_PAUSE</li><li>PAUSE</li><li>EJECT</li><li>CHASE</li><li>MMC_RESET</li><li>WRITE</li><li>GOTO<ul><li>timecode - Timecode as string, in the following format: "hh:mm:ss:fr" (i.e. "12:03:03:13").</li><li>frameRate - Frame Rate as string, possible options include: "24", "25", "30 DF" or "30 NDF".</li><li>subFrame - Subframe as string.</li></ul></li><li>ERROR</li><li>SHUTTLE</li><li>Example Usage:  <code>lua    _plugins("core.midi.manager").sendMMC("CommandPost", false, "7F", "GOTO", {timecode="01:02:03:04", frameRate="25", subFrame="00"})</code></li></ul> |

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

#### [buttons](#buttons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.buttons <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains all the saved MIDI items |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable MIDI Support. |

#### [listenMMC](#listenmmc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.listenMMC <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable Listen MMC Support. |

#### [listenMMCDevice](#listenmmcdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.listenMMCDevice <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | MIDI Device |

#### [listenMTC](#listenmtc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.listenMTC <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable Listen MTC Support. |

#### [listenMTCDevice](#listenmtcdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.listenMTCDevice <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | MIDI Device |

#### [transmitMMC](#transmitmmc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.transmitMMC <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable Transmit MMC Support. |

#### [transmitMMCDevice](#transmitmmcdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.transmitMMCDevice <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | MIDI Device |

#### [transmitMTC](#transmitmtc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.transmitMTC <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable Transmit MTC Support. |

#### [transmitMTCDevice](#transmitmtcdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.transmitMTCDevice <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | MIDI Device |

