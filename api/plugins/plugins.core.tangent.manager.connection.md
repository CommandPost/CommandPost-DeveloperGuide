# [docs](index.md) » plugins.core.tangent.manager.connection
---

Represents a Tangent Connection.

## API Overview
* Variables - Configurable values
 * [connections](#connections)
* Constructors - API calls which return an object, typically one that offers API methods
 * [connection](#connection)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addMode](#addmode)
 * [applicationName](#applicationname)
 * [device](#device)
 * [displayName](#displayname)
 * [getControlsXML](#getcontrolsxml)
 * [getMode](#getmode)
 * [pluginPath](#pluginpath)
 * [setupTangentConnection](#setuptangentconnection)
 * [systemPath](#systempath)
 * [task](#task)
 * [update](#update)
 * [updateControls](#updatecontrols)
 * [updateFavourites](#updatefavourites)
 * [userPath](#userpath)
 * [writeControlsXML](#writecontrolsxml)

## API Documentation

### Variables

#### [connections](#connections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connections -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A table containing all the Tangent connections. |

### Constructors

#### [connection](#connection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection(bundleID, manager) -> Connection object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Connection` object. |
| **Parameters**                                       | <ul><li>applicationName - The application name as a string. This is what appears in Tangent Mapper.</li><li>displayName - The application display name as a string. This is what appears in CommandPost.</li><li>systemPath - A string containing the absolute path of the directory that contains the Controls and Default Map XML files.</li><li>userPath - An optional string containing the absolute path of the directory that contains the User’s Default Map XML files.</li><li>task - An optional string containing the name of the task associated with the application.          This is used to assist with automatic switching of panels when your application gains mouse focus on the GUI.          This parameter should only be required if the string passed in appStr does not match the Task name that the OS          identifies as your application. Typically, this is only usually required for Plugins which run within a parent          Host application. Under these circumstances it is the name of the Host Application’s Task which should be passed.</li><li>pluginPath - A string containing the absolute path of the directory that contains the built-in Default Map XML files.</li><li>addDefaultModes - A boolean which indicates whether or not CommandPost should add any default modes.</li><li>setupFn - Setup function.</li><li>transportFn - Transport function.</li><li>manager - The Tangent Manager module</li></ul> |
| **Returns**                                          | <ul><li>A new Connection object.</li></ul> |

### Methods

#### [addMode](#addmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:addMode(id, name) -> plugins.core.tangent.manager.mode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a new `mode` with the specified details and returns it. |
| **Parameters**                                       | <ul><li>id            - The id number of the Mode.</li><li>name          - The name of the Mode.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>mode</code></li></ul> |

#### [applicationName](#applicationname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:applicationName() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the application name. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application name as a string.</li></ul> |

#### [device](#device)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:device() -> hs.tangent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the `hs.tangent` object for the connnection. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs.tangent</code> object</li></ul> |

#### [displayName](#displayname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:displayName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the display name for the connnection. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [getControlsXML](#getcontrolsxml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:getControlsXML() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the controls XML. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The XML controls</li></ul> |

#### [getMode](#getmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:getMode(id) -> plugins.core.tangent.manager.mode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `mode` with the specified ID, or `nil`. |
| **Parameters**                                       | <ul><li>id    - The ID to find.</li></ul> |
| **Returns**                                          | <ul><li>The <code>mode</code>, or <code>nil</code>.</li></ul> |

#### [pluginPath](#pluginpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:pluginPath() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the plugin path. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The plugin path as a string.</li></ul> |

#### [setupTangentConnection](#setuptangentconnection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:setupTangentConnection() -> hs.tangent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets up a new Tangent Connection. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs.tangent</code> object.</li></ul> |

#### [systemPath](#systempath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:systemPath() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the system path. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The system path as a string.</li></ul> |

#### [task](#task)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:task() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the task. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The task as a string.</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Updates the Tangent GUIs. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateControls](#updatecontrols)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:updateControls() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Update Controls. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateFavourites](#updatefavourites)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:updateFavourites() -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Updates the Favourites. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [userPath](#userpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:userPath() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the user path. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The user path as a string.</li></ul> |

#### [writeControlsXML](#writecontrolsxml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.connection:writeControlsXML() -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Writes the Tangent controls.xml File to the User's Application Support folder. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully created otherwise <code>false</code> if an error occurred.</li><li>If an error occurs an error message will also be returned as a string.</li></ul> |

