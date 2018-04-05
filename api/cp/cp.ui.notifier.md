# [docs](index.md) » cp.ui.notifier
---

Supports long-lived 'AX' notifiers. Configure the application to watch, the
function that provides the `axuielement` and then register for the type of
notification to watch, along with a function that will get triggered.

For example:

```lua
local observer = require("cp.ui.notifier")
local function finder() ... end -- returns the axuielement
local o = observer.new("com.apple.FinalCut", finder)
o:addWatcher("AXValueChanged", function(observer, element, notification, details) ... end)
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
| **Parameters**                                       | <ul><li>* bundleID          - The application Bundle ID being observed. E.g. "com.apple.FinalCut".</li></ul> |
| **Returns**                                          | <ul><li>* A table of `cp.ui.notifier` instances.</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier.new(bundleID, elementFinderFn) -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `cp.ui.notifier` instance with the specified bundle ID and                                                                                         |
| **Parameters**                                       | <ul><li>* bundleID          - The application Bundle ID being observed. E.g. "com.apple.FinalCut".</li><li>* elementFinderFn   - The function that will return the `axuielement` to observe.</li></ul> |
| **Returns**                                          | <ul><li>* A new `cp.ui.notifier` instance.</li></ul>          |

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
| **Parameters**                                       | <ul><li>* notification      - The notification type to watch for (e.g. "AXValueChanged").</li><li>* callbackFn        - The function to call when the matching notification is happens.</li></ul> |
| **Returns**                                          | <ul><li>* The `cp.ui.notifier` instance.</li></ul>          |
| **Notes**                                            | <ul><li>* The callback function should expect 3 arguments and return none. The arguments passed to the callback will be as follows:</li><li>** the `hs._asm.axuielement` object for the accessibility element which generated the notification.</li><li>** a string with the notification type.</li><li>** A table containing key-value pairs with more information about the notification, if provided. Commonly this will be an empty table.</li></ul>                |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:app() -> hs.application` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current `hs.application` instance for the app this notifier tracks.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The running `hs.application` for the notifier's `bundleID`, or `nil`.</li></ul>          |

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:bundleID()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the application 'bundle ID' that this notifier is tracking.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The application 'bundle ID' string (e.g. "com.apple.FinalCut")</li></ul>          |

#### [currentElement](#currentelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:currentElement() -> hs._asm.axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the current `axuielement` being observed.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `axuielement`, or `nil` if not available.</li></ul>          |

#### [pid](#pid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:pid() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the PID for the application being observed, or `nil` if it's not running.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The PID, or `nil`.</li></ul>          |

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
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `cp.ui.notifier` instance.</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:update([force]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Updates any watchers to use the current `axuielement`.                                                                                         |
| **Parameters**                                       | <ul><li>* force     - If `true`, the notifier will be updated even if the element has not changed since the last update. Defaults to `false`.</li></ul> |
| **Returns**                                          | <ul><li>* The `cp.ui.notifier` instance.</li></ul>          |

