# [docs](index.md) » plugins.core.midi.manager.controls
---

MIDI Manager Controls.

## API Overview
* Variables - Configurable values
 * [controls](#controls)
* Functions - API calls offered directly by the extension
 * [allGroups](#allgroups)
* Methods - API calls which can only be made on an object returned by a constructor
 * [get](#get)
 * [getAll](#getall)
 * [id](#id)
 * [new](#new)
 * [params](#params)

## API Documentation

### Variables

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Controls |

### Functions

#### [allGroups](#allgroups)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls.allGroups() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing all of the control groups. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table</li></ul> |

### Methods

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:get(id) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets a MIDI control. |
| **Parameters**                                       | <ul><li><code>id</code>      - The unique ID for the widget you want to return.</li></ul> |
| **Returns**                                          | <ul><li>table containing the widget</li></ul> |

#### [getAll](#getall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:getAll() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns all of the created controls. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>table containing all of the created callbacks</li></ul> |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the ID of the control. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The ID of the widget as a <code>string</code></li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:new(id, params) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new MIDI control. |
| **Parameters**                                       | <ul><li>id       - The unique ID for this widget.</li><li>params   - A table of parameters for the MIDI control.</li></ul> |
| **Returns**                                          | <ul><li>table that has been created</li></ul> |
| **Notes**                                            | <ul><li>The parameters table should include:</li><li>group      - The group as a string (i.e. "fcpx")</li><li>text       - The name of the control as it will appear in the Console</li><li>subText    - The subtext of the control as it will appear in the Console</li><li>fn         - The callback function. This functions should accept one parameter                  which contains all the MIDI callback metadata.</li></ul> |

#### [params](#params)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:params() -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the paramaters of the control. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The paramaters of the widget</li></ul> |

