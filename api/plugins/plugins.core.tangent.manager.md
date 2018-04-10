# [docs](index.md) » plugins.core.tangent.manager
---

Tangent Control Surface Manager

This plugin allows CommandPost to communicate with Tangent's range of
panels (Element, Virtual Element Apps, Wave, Ripple and any future panels).

Download the Tangent Developer Support Pack & Tangent Hub Installer for Mac
here: http://www.tangentwave.co.uk/developer-support

## Submodules
 * [plugins.core.tangent.manager.action](plugins.core.tangent.manager.action.md)
 * [plugins.core.tangent.manager.binding](plugins.core.tangent.manager.binding.md)
 * [plugins.core.tangent.manager.controls](plugins.core.tangent.manager.controls.md)
 * [plugins.core.tangent.manager.group](plugins.core.tangent.manager.group.md)
 * [plugins.core.tangent.manager.menu](plugins.core.tangent.manager.menu.md)
 * [plugins.core.tangent.manager.mode](plugins.core.tangent.manager.mode.md)
 * [plugins.core.tangent.manager.named](plugins.core.tangent.manager.named.md)
 * [plugins.core.tangent.manager.parameter](plugins.core.tangent.manager.parameter.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [activeMode](#activemode)
 * [FCP_KEYPRESS_APPS_PATH](#fcp_keypress_apps_path)
 * [HIDE_FILE_PATH](#hide_file_path)
 * [TANGENT_MAPPER_BUNDLE_ID](#tangent_mapper_bundle_id)
* Variables - Configurable values
 * [connectable](#connectable)
 * [connected](#connected)
 * [enabled](#enabled)
 * [interrupted](#interrupted)
 * [requiresConnection](#requiresconnection)
 * [requiresDisconnection](#requiresdisconnection)
 * [tangentHubInstalled](#tangenthubinstalled)
 * [tangentMapperInstalled](#tangentmapperinstalled)
 * [tangentMapperRunning](#tangentmapperrunning)
* Functions - API calls offered directly by the extension
 * [addMode](#addmode)
 * [areMappingsInstalled](#aremappingsinstalled)
 * [disableFinalCutProInTangentHub](#disablefinalcutprointangenthub)
 * [getMode](#getmode)
 * [interruptWhen](#interruptwhen)
 * [launchTangentMapper](#launchtangentmapper)
 * [update](#update)
 * [updateControls](#updatecontrols)
 * [writeControlsXML](#writecontrolsxml)

## API Documentation

### Constants

#### [activeMode](#activemode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.activeMode <cp.prop: mode>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Represents the currently active `mode`.                                                                                         |

#### [FCP_KEYPRESS_APPS_PATH](#fcp_keypress_apps_path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.FCP_KEYPRESS_APPS_PATH -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Final Cut Pro Keypress Apps Path for Tangent Mapper.                                                                                         |

#### [HIDE_FILE_PATH](#hide_file_path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.HIDE_FILE_PATH -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Tangent Mapper Hide File Path.                                                                                         |

#### [TANGENT_MAPPER_BUNDLE_ID](#tangent_mapper_bundle_id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.TANGENT_MAPPER_BUNDLE_ID -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Tangent Mapper Bundle ID.                                                                                         |

### Variables

#### [connectable](#connectable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connectable <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is the Tangent Enabled, Not Interrupted, and the Tangent Hub Installed?                                                                                         |

#### [connected](#connected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connected <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | A `cp.prop` that tracks the connection status to the Tangent Hub.                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Enable or disables the Tangent Manager.                                                                                         |

#### [interrupted](#interrupted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.interrupted <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | If this property is `true` it will temporarily interrupt the Tangent connection, if it is enabled.                                                                                         |

#### [requiresConnection](#requiresconnection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.requiresConnection <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is `true` when the Tangent Manager is both `enabled` but not `connected`.                                                                                         |

#### [requiresDisconnection](#requiresdisconnection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.requiresDisconnection <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is `true` when the Tangent Manager is both not `enabled` but is `connected`.                                                                                         |

#### [tangentHubInstalled](#tangenthubinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.tangentHubInstalled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is Tangent Hub Installed?                                                                                         |

#### [tangentMapperInstalled](#tangentmapperinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.tangentMapperInstalled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is Tangent Mapper Installed?                                                                                         |

#### [tangentMapperRunning](#tangentmapperrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.tangentMapperRunning <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is Tangent Mapper Running?                                                                                         |

### Functions

#### [addMode](#addmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.addMode(id, name) -> plugins.core.tangent.manager.mode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a new `mode` with the specified details and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>* id            - The id number of the Mode.</li><li>* name          - The name of the Mode.</li></ul> |
| **Returns**                                          | <ul><li>* The new `mode`</li></ul>          |

#### [areMappingsInstalled](#aremappingsinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.areMappingsInstalled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Are mapping files installed?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if mapping files are installed otherwise `false`</li></ul>          |

#### [disableFinalCutProInTangentHub](#disablefinalcutprointangenthub)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.disableFinalCutProInTangentHub() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disables the Final Cut Pro preset in the Tangent Hub Application.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [getMode](#getmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.getMode(id) -> plugins.core.tangent.manager.mode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the `mode` with the specified ID, or `nil`.                                                                                         |
| **Parameters**                                       | <ul><li>* id    - The ID to find.</li></ul> |
| **Returns**                                          | <ul><li>* The `mode`, or `nil`.</li></ul>          |

#### [interruptWhen](#interruptwhen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.interruptWhen(aProp) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a `cp.prop` that will cause an interruption to the Tangent connection when it is `true`.                                                                                         |
| **Parameters**                                       | <ul><li>* aProp     - The `cp.prop` that may interrupt the connection.</li></ul> |
| **Returns**                                          | <ul><li>* Nothing.</li></ul>          |

#### [launchTangentMapper](#launchtangentmapper)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.launchTangentMapper() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Launches the Tangent Mapper.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Tangent GUIs.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [updateControls](#updatecontrols)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.updateControls() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Update Controls.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [writeControlsXML](#writecontrolsxml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.writeControlsXML() -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Writes the Tangent controls.xml File to the User's Application Support folder.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li> `true` if successfully created otherwise `false` if an error occurred.</li><li> If an error occurs an error message will also be returned as a string.</li></ul>          |

