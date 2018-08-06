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
o:watchFor("AXValueChanged", function(notifier, element, notification, details) ... end)
o:start()
```

## API Overview
* Functions - API calls offered directly by the extension
 * [notifiersForBundleID](#notifiersforbundleid)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [bundleID](#bundleid)
 * [currentElement](#currentelement)
 * [debugging](#debugging)
 * [pid](#pid)
 * [reset](#reset)
 * [start](#start)
 * [update](#update)
 * [watchAll](#watchall)
 * [watchFor](#watchfor)

## API Documentation

### Functions

#### [notifiersForBundleID](#notifiersforbundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier.notifiersForBundleID(bundleID) -> table of cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the list of `cp.ui.notifier` instances that have been created for the specified `Bundle ID`. |
| **Parameters**                                       | <ul><li>bundleID          - The application Bundle ID being observed. E.g. "com.apple.FinalCut".</li></ul> |
| **Returns**                                          | <ul><li>A table of <code>cp.ui.notifier</code> instances.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier.new(bundleID, elementFinderFn) -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `cp.ui.notifier` instance with the specified bundle ID and |
| **Parameters**                                       | <ul><li>bundleID          - The application Bundle ID being observed. E.g. "com.apple.FinalCut".</li><li>elementFinderFn   - The function that will return the <code>axuielement</code> to observe.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>cp.ui.notifier</code> instance.</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:app() -> hs.application` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the current `hs.application` instance for the app this notifier tracks. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The running <code>hs.application</code> for the notifier's <code>bundleID</code>, or <code>nil</code>.</li></ul> |

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:bundleID()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the application 'bundle ID' that this notifier is tracking. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application 'bundle ID' string (e.g. "com.apple.FinalCut")</li></ul> |

#### [currentElement](#currentelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:currentElement() -> hs._asm.axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the current `axuielement` being observed. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>axuielement</code>, or <code>nil</code> if not available.</li></ul> |

#### [debugging](#debugging)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:debugging([enabled]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Enables/disables and reports current debugging status. |
| **Parameters**                                       | <ul><li>enabled  - If <code>true</code>, debugging notifications will be emitted. If <code>false</code>, it will be disabled. If not provided, no change is made.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if currently debugging, <code>false</code> otherwise.</li></ul> |

#### [pid](#pid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:pid() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the PID for the application being observed, or `nil` if it's not running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The PID, or <code>nil</code>.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:reset() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resets the notifier |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:start() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops notifying watchers when events happen. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.ui.notifier</code> instance.</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:update([force]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Updates any watchers to use the current `axuielement`. |
| **Parameters**                                       | <ul><li>force     - If <code>true</code>, the notifier will be updated even if the element has not changed since the last update. Defaults to <code>false</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.ui.notifier</code> instance.</li></ul> |

#### [watchAll](#watchall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:watchAll(callbackFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Registers the callback as a watcher for all standard notifications for the current `axuielement`. |
| **Parameters**                                       | <ul><li>callbackFn   - the function to call when the notification happens.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.ui.notifier</code> instance.</li></ul> |
| **Notes**                                            | <ul><li>This should generally just be used for debugging purposes. It's best to use <code>watchFor</code>[#watchFor] in most cases.</li><li>The callback function should expect 3 arguments and return none. The arguments passed to the callback will be as follows:<ul><li>the <code>hs._asm.axuielement</code> object for the accessibility element which generated the notification.</li><li>a string with the notification type.</li><li>A table containing key-value pairs with more information about the notification, if provided. Commonly this will be an empty table.</li></ul></li></ul> |

#### [watchFor](#watchfor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.notifier:watchFor(notification, callbackFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Registers a function to get called whenever the specified notification type is triggered |
| **Parameters**                                       | <ul><li>notifications     - The <code>string</code> or <code>table of strings</code> with the notification type(s) to watch for (e.g. "AXValueChanged").</li><li>callbackFn        - The function to call when the matching notification is happens.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.ui.notifier</code> instance.</li></ul> |
| **Notes**                                            | <ul><li>The callback function should expect 3 arguments and return none. The arguments passed to the callback will be as follows:<ul><li>the <code>hs._asm.axuielement</code> object for the accessibility element which generated the notification.</li><li>a string with the notification type.</li><li>A table containing key-value pairs with more information about the notification, if provided. Commonly this will be an empty table.</li></ul></li></ul> |

