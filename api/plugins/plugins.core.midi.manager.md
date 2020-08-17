# [docs](index.md) » plugins.core.midi.manager
---

MIDI Manager Plugin.

## Submodules
 * [plugins.core.midi.manager.controls](plugins.core.midi.manager.controls.md)

## API Overview
* Variables - Configurable values
 * [defaultLayout](#defaultlayout)
 * [defaultLoupedeckLayout](#defaultloupedecklayout)
 * [defaultLoupedeckPlusLayout](#defaultloupedeckpluslayout)
 * [lastActiveBundleID](#lastactivebundleid)
 * [learningMode](#learningmode)
 * [maxItems](#maxitems)
* Functions - API calls offered directly by the extension
 * [devices](#devices)
 * [getDevice](#getdevice)
 * [getItem](#getitem)
 * [start](#start)
 * [stop](#stop)
 * [update](#update)
 * [virtualDevices](#virtualdevices)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activeBanks](#activebanks)
 * [activeLoupedeckBanks](#activeloupedeckbanks)
 * [activeLoupedeckPlusBanks](#activeloupedeckplusbanks)
 * [displayMessageWhenChangingBanks](#displaymessagewhenchangingbanks)
 * [enabled](#enabled)
 * [enabledLoupedeck](#enabledloupedeck)
 * [enabledLoupedeckPlus](#enabledloupedeckplus)
 * [numberOfMidiDevices](#numberofmididevices)

## API Documentation

### Variables

#### [defaultLayout](#defaultlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.defaultLayout -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Default MIDI Layout |

#### [defaultLoupedeckLayout](#defaultloupedecklayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.defaultLoupedeckLayout -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Default Loupedeck Layout |

#### [defaultLoupedeckPlusLayout](#defaultloupedeckpluslayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.defaultLoupedeckPlusLayout -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Default Loupedeck+ Layout |

#### [lastActiveBundleID](#lastactivebundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.lastActiveBundleID -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The last Active Bundle ID. Used for AudioSwift workaround. |

#### [learningMode](#learningmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.learningMode -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Whether or not the MIDI Manager is in learning mode. |

#### [maxItems](#maxitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.maxItems -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The maximum number of MIDI items per bank. |

### Functions

#### [devices](#devices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.devices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a table of Physical MIDI Device Names. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of Physical MIDI Device Names.</li></ul> |

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

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.start() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Starts the MIDI Plugin |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.stop() -> boolean` </span>                                                          |
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

#### [virtualDevices](#virtualdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.virtualDevices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a table of Virtual MIDI Source Names. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of Virtual MIDI Source Names.</li></ul> |

### Fields

#### [activeBanks](#activebanks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.activeBanks <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Table of active banks for each application. |

#### [activeLoupedeckBanks](#activeloupedeckbanks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.activeLoupedeckBanks <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Table of active banks for each application. |

#### [activeLoupedeckPlusBanks](#activeloupedeckplusbanks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.activeLoupedeckPlusBanks <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Table of active banks for each application. |

#### [displayMessageWhenChangingBanks](#displaymessagewhenchangingbanks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.displayMessageWhenChangingBanks <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Display message when changing banks? |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable MIDI Support. |

#### [enabledLoupedeck](#enabledloupedeck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.enabledLoupedeck <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable MIDI Loupedeck Support. |

#### [enabledLoupedeckPlus](#enabledloupedeckplus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.enabledLoupedeckPlus <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable MIDI Loupedeck+ Support. |

#### [numberOfMidiDevices](#numberofmididevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.numberOfMidiDevices -> <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Total number of MIDI Devices detected (including both physical and virtual). |

