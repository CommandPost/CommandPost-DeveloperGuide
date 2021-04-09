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
 * [plugins.core.tangent.manager.connection](plugins.core.tangent.manager.connection.md)
 * [plugins.core.tangent.manager.controls](plugins.core.tangent.manager.controls.md)
 * [plugins.core.tangent.manager.group](plugins.core.tangent.manager.group.md)
 * [plugins.core.tangent.manager.menu](plugins.core.tangent.manager.menu.md)
 * [plugins.core.tangent.manager.mode](plugins.core.tangent.manager.mode.md)
 * [plugins.core.tangent.manager.named](plugins.core.tangent.manager.named.md)
 * [plugins.core.tangent.manager.parameter](plugins.core.tangent.manager.parameter.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [APPLICATION_NAME_SUFFIX](#application_name_suffix)
 * [MAXIMUM_CONNECTIONS](#maximum_connections)
 * [NUMBER_OF_FAVOURITES](#number_of_favourites)
 * [USER_CONTROL_MAPS_FOLDER](#user_control_maps_folder)
* Variables - Configurable values
 * [customApplications](#customapplications)
 * [enabled](#enabled)
 * [tangentHubInstalled](#tangenthubinstalled)
 * [tangentMapperInstalled](#tangentmapperinstalled)
* Functions - API calls offered directly by the extension
 * [applicationNames](#applicationnames)
 * [getConnection](#getconnection)
 * [launchTangentMapper](#launchtangentmapper)
 * [newConnection](#newconnection)
 * [registerCustomApplication](#registercustomapplication)
 * [removeCustomApplication](#removecustomapplication)
 * [setupCustomApplications](#setupcustomapplications)

## API Documentation

### Constants

#### [APPLICATION_NAME_SUFFIX](#application_name_suffix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.APPLICATION_NAME_SUFFIX -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A suffix applied to the end of Application Names as they appear in Tangent Mapper |

#### [MAXIMUM_CONNECTIONS](#maximum_connections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.MAXIMUM_CONNECTIONS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Maximum number of socket connections to Tangent Hub. |

#### [NUMBER_OF_FAVOURITES](#number_of_favourites)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.NUMBER_OF_FAVOURITES -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Maximum number of favourites. |

#### [USER_CONTROL_MAPS_FOLDER](#user_control_maps_folder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.USER_CONTROL_MAPS_FOLDER -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The full name for storing User Control Maps |

### Variables

#### [customApplications](#customapplications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.customApplications <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table of Custom Applications |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Enable or disables the Tangent Manager. |

#### [tangentHubInstalled](#tangenthubinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.tangentHubInstalled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Is Tangent Hub Installed? |

#### [tangentMapperInstalled](#tangentmapperinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.tangentMapperInstalled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Is Tangent Mapper Installed? |

### Functions

#### [applicationNames](#applicationnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.applicationNames() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a table listing all the connections application names. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the names of all the registered connections.</li></ul> |

#### [getConnection](#getconnection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.getConnection(applicationName) -> connection` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a Tangent connection object. |
| **Parameters**                                       | <ul><li>applicationName - Your application name as a string</li></ul> |
| **Returns**                                          | <ul><li>The connection object</li></ul> |

#### [launchTangentMapper](#launchtangentmapper)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.launchTangentMapper() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Launches the Tangent Mapper. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [newConnection](#newconnection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.newConnection(applicationName, systemPath, userPath, task, pluginPath, addDefaultModes, setupFn, transportFn) -> connection` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new Tangent Connection |
| **Parameters**                                       | <ul><li>applicationName - The application name as a string. This is what appears in CommandPost Preferences.</li><li>systemPath - A string containing the absolute path of the directory that contains the Controls and Default Map XML files.</li><li>userPath - An optional string containing the absolute path of the directory that contains the User’s Default Map XML files.</li><li>task - An optional string containing the name of the task associated with the application.          This is used to assist with automatic switching of panels when your application gains mouse focus on the GUI.          This parameter should only be required if the string passed in appStr does not match the Task name that the OS          identifies as your application. Typically, this is only usually required for Plugins which run within a parent          Host application. Under these circumstances it is the name of the Host Application’s Task which should be passed.</li><li>pluginPath - A string containing the absolute path of the directory that contains the built-in Default Map XML files.</li><li>addDefaultModes - A boolean which indicates whether or not CommandPost should add any default modes.</li><li>setupFn - Setup function.</li><li>transportFn - Transport function.</li></ul> |
| **Returns**                                          | <ul><li>The connection object</li></ul> |

#### [registerCustomApplication](#registercustomapplication)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.registerCustomApplication(applicationName, bundleExecutable) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Registers a new Custom Application |
| **Parameters**                                       | <ul><li>applicationName - The display name of the custom application</li><li>bundleExecutable - The bundle executable identifier of the custom application</li></ul> |
| **Returns**                                          | <ul><li>A table where the application name is the key, and display name is the value.</li></ul> |

#### [removeCustomApplication](#removecustomapplication)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.removeCustomApplication(applicationName) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes a Custom Application. |
| **Parameters**                                       | <ul><li>applicationName - The display name of the Custom Application to Remove.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setupCustomApplications](#setupcustomapplications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.setupCustomApplications() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Setup the Custom Applications. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

