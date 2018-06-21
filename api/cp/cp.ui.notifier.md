# [docs](index.md) » cp.ui.notifier
---

Supports long-lived 'AX' notifiers. Configure the application to watch, the
function that provides the `axuielement` and then register for the type of
notification to watch, along with a function that will get triggered.

For example:

```lua
local notifier = require("cp.ui.notifier")
local function finder() ... end -- returns the axuielement
local o = notifier.new("com.apple.FinalCut", finder)
o:addWatcher("AXValueChanged", function(notifier, element, notification, details) ... end)
o:start()
```

## API Overview
* Functions - API calls offered directly by the extension
 * [notifiersForBundleID](#notifiersforbundleid)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isRunning](#isrunning)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addWatcher](#addwatcher)
 * [app](#app)
 * [bundleID](#bundleid)
 * [currentElement](#currentelement)
 * [pid](#pid)
 * [reset](#reset)
 * [start](#start)
 * [update](#update)

## API Documentation

### Functions

#### [notifiersForBundleID](#notifiersforbundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier.notifiersForBundleID(bundleID) -> table of cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the list of `cp.ui.notifier` instances that have been created for the specified `Bundle ID`.                                                                                         |
| **Parameters**                                       |  * bundleID          - The application Bundle ID being observed. E.g. "com.apple.FinalCut".                                       |
| **Returns**                                          |  * A table of `cp.ui.notifier` instances.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier.new(bundleID, elementFinderFn) -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `cp.ui.notifier` instance with the specified bundle ID and                                                                                         |
| **Parameters**                                       |  * bundleID          - The application Bundle ID being observed. E.g. "com.apple.FinalCut". * elementFinderFn   - The function that will return the `axuielement` to observe.                                       |
| **Returns**                                          |  * A new `cp.ui.notifier` instance.                                                |

### Fields

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier.isRunning <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Indicates if the notifier is currently running.                                                                                         |

### Methods

#### [addWatcher](#addwatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:addWatcher(notification, callbackFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers a function to get called whenever the specified notification type is triggered                                                                                         |
| **Parameters**                                       |  * notification      - The notification type to watch for (e.g. "AXValueChanged"). * callbackFn        - The function to call when the matching notification is happens.                                       |
| **Returns**                                          |  * The `cp.ui.notifier` instance.                                                |
| **Notes**                                            |  * The callback function should expect 3 arguments and return none. The arguments passed to the callback will be as follows: ** the `hs._asm.axuielement` object for the accessibility element which generated the notification. ** a string with the notification type. ** A table containing key-value pairs with more information about the notification, if provided. Commonly this will be an empty table.                                                      |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:app() -> hs.application` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current `hs.application` instance for the app this notifier tracks.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The running `hs.application` for the notifier's `bundleID`, or `nil`.                                                |

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:bundleID()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the application 'bundle ID' that this notifier is tracking.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The application 'bundle ID' string (e.g. "com.apple.FinalCut")                                                |

#### [currentElement](#currentelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:currentElement() -> hs._asm.axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current `axuielement` being observed.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `axuielement`, or `nil` if not available.                                                |

#### [pid](#pid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:pid() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the PID for the application being observed, or `nil` if it's not running.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The PID, or `nil`.                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:reset() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resets the notifier                                                                                         |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:start() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops notifying watchers when events happen.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.ui.notifier` instance.                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:update([force]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Updates any watchers to use the current `axuielement`.                                                                                         |
| **Parameters**                                       |  * force     - If `true`, the notifier will be updated even if the element has not changed since the last update. Defaults to `false`.                                       |
| **Returns**                                          |  * The `cp.ui.notifier` instance.                                                |

