# [docs](index.md) » cp.app.prefs
---

Provides access to application preferences, typically stored via `NSUserDefaults` or `CFProperties`.
To access the preferences, simply pass in the Bundle ID (eg. "com.apple.Preview") and it will return
a table whose keys can be accessed or updated, or iterated via `ipairs`.

For example:

```lua
local previewPrefs = require("cp.app.prefs").new("com.apple.Preview")
previewPrefs.MyCustomPreference = "Hello world"
print(previewPrefs.MyCustomPreference) --> "Hello world"

for k,v in pairs(previewPrefs) do
    print(k .. " = " .. tostring(v))
end
```

## API Overview
* Functions - API calls offered directly by the extension
 * [bundleID](#bundleid)
 * [is](#is)
 * [watch](#watch)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)

## API Documentation

### Functions

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.bundleID(prefs) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieves the `bundleID` associated with the `cp.app.prefs` instance.                                                                                         |
| **Parameters**                                       | <ul><li>prefs     - the `prefs` object to query</li></ul> |
| **Returns**                                          | <ul><li>The Bundle ID string, or `nil` if it's not a `cp.app.prefs`.</li></ul>          |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `thing` is a `cp.app.prefs` instance.                                                                                         |
| **Parameters**                                       | <ul><li>thing     - The value to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if if's a `prefs`, otherwise `false`.</li></ul>          |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.watch(prefs, watchFn) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a watch function which will be notified when the preferences change.                                                                                         |
| **Parameters**                                       | <ul><li>prefs     - The `prefs` instance to watch.</li><li>watchFn   - The function that will get called.</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.new(bundleID) -> cp.app.prefs` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `cp.app.prefs` instance, pointing at the specified `bundleID`.                                                                                         |
| **Parameters**                                       | <ul><li>bundleID      The Bundle ID to access preferences for.</li></ul> |
| **Returns**                                          | <ul><li>A new `cp.app.prefs` with read/write access to the application's preferences.</li></ul>          |

