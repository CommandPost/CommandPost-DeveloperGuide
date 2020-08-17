# [docs](index.md) » plugins.core.application.manager
---

Application manager.

## API Overview
* Functions - API calls offered directly by the extension
 * [defaultSearchConsoleToolbar](#defaultsearchconsoletoolbar)
 * [getApplications](#getapplications)
 * [getSearchConsoleToolbar](#getsearchconsoletoolbar)
 * [registerApplication](#registerapplication)

## API Documentation

### Functions

#### [defaultSearchConsoleToolbar](#defaultsearchconsoletoolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.application.manager.defaultSearchConsoleToolbar() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the default search toolbar data. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [getApplications](#getapplications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.application.manager.getApplications() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets all the registered applications. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of all the registered applications.</li></ul> |

#### [getSearchConsoleToolbar](#getsearchconsoletoolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.application.manager.getSearchConsoleToolbar(bundleID) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the Search Console Toolbar data for a specific bundle ID. |
| **Parameters**                                       | <ul><li>bundleID - The bundle ID of the application you want to get.</li></ul> |
| **Returns**                                          | <ul><li>A table of the Search Sonole Toolbar data for the specified application.</li></ul> |

#### [registerApplication](#registerapplication)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.application.manager.registerApplication(data) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Registers a new application. |
| **Parameters**                                       | <ul><li>data - A table containing the information to register.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>The data table should contain:</li><li>displayName - The display name of the application</li><li>bundleID - The bundle ID of the application</li><li>searchConsoleToolbar - A table containing the Search Console Toolbar information</li><li>legacyGroupID - A string containing the legacy group ID (i.e. "fcpx")</li></ul> |

