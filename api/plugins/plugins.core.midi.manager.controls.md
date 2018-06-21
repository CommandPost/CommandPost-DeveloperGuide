# [docs](index.md) » plugins.core.midi.manager.controls
---

MIDI Manager Controls.

## API Overview
* Functions - API calls offered directly by the extension
 * [allGroups](#allgroups)
* Methods - API calls which can only be made on an object returned by a constructor
 * [get](#get)
 * [getAll](#getall)
 * [id](#id)
 * [new](#new)
 * [params](#params)

## API Documentation

### Functions

#### [allGroups](#allgroups)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls.allGroups() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table containing all of the control groups.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * Table                                                |

### Methods

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:get(id) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a MIDI control.                                                                                         |
| **Parameters**                                       | * `id`      - The unique ID for the widget you want to return.                                       |
| **Returns**                                          |  * table containing the widget                                                |

#### [getAll](#getall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:getAll() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns all of the created controls.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * table containing all of the created callbacks                                                |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ID of the control.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * The ID of the widget as a `string`                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:new(id, params) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new MIDI control.                                                                                         |
| **Parameters**                                       | * `id`      - The unique ID for this widget.                                       |
| **Returns**                                          |  * table that has been created                                                |

#### [params](#params)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.midi.manager.controls:params() -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the paramaters of the control.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          |  * The paramaters of the widget                                                |

