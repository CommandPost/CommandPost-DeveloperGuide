# [docs](index.md) » cp.apple.compressor
---

Represents the Compressor application, providing functions that allow different tasks to be accomplished.

## API Overview
* Constants - Useful values which cannot be changed
 * [BUNDLE_ID](#bundle_id)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isFrontmost](#isfrontmost)
 * [isInstalled](#isinstalled)
 * [isRunning](#isrunning)
 * [isShowing](#isshowing)
* Methods - API calls which can only be made on an object returned by a constructor
 * [application](#application)
 * [getBundleID](#getbundleid)
 * [getVersion](#getversion)
 * [hide](#hide)
 * [launch](#launch)
 * [path](#path)
 * [quit](#quit)
 * [restart](#restart)
 * [show](#show)

## API Documentation

### Constants

#### [BUNDLE_ID](#bundle_id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.BUNDLE_ID` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Compressor's Bundle ID                                                                                         |

### Fields

#### [isFrontmost](#isfrontmost)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.isFrontmost <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is Compressor Frontmost?                                                                                         |

#### [isInstalled](#isinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.isInstalled <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is a supported version of Compressor Installed?                                                                                         |

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.isRunning <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the app is running?                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is Compressor Showing?                                                                                         |

### Methods

#### [application](#application)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:application() -> hs.application` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the hs.application for Compressor.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The hs.application, or nil if the application is not installed.</li></ul>          |

#### [getBundleID](#getbundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:getBundleID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Compressor Bundle ID                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string of the Compressor Bundle ID</li></ul>          |

#### [getVersion](#getversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:getVersion() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Version of Compressor                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Version as string or nil if an error occurred</li></ul>          |
| **Notes**                                            | <ul><li>If Compressor is running it will get the version of the active Compressor application, otherwise, it will use hs.application.infoForBundleID() to find the version.</li></ul>                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:hide() -> cp.apple.compressor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides Compressor                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `cp.apple.compressor` object otherwise `nil`</li></ul>          |

#### [launch](#launch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:launch() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Launches Compressor, or brings it to the front if it was already running.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if Compressor was either launched or focused, otherwise false (e.g. if Compressor doesn't exist)</li></ul>          |

#### [path](#path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:path() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Path to Compressor Application                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing Compressor's filesystem path, or `nil` if the bundle identifier could not be located</li></ul>          |

#### [quit](#quit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:quit() -> cp.apple.compressor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Quits Compressor                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `cp.apple.compressor` object otherwise `nil`</li></ul>          |

#### [restart](#restart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:restart() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Restart the application.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if the application was running and restarted successfully.</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:show() -> cp.apple.compressor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Activate Compressor                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `cp.apple.compressor` object otherwise `nil`</li></ul>          |

