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
 * [get](#get)
 * [is](#is)
 * [prop](#prop)
 * [set](#set)
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
| **Parameters**                                       |  * prefs     - the `prefs` object to query                                       |
| **Returns**                                          |  * The Bundle ID string, or `nil` if it's not a `cp.app.prefs`.                                                |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.get(prefs, key[, defaultValue])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieves the specifed `key` from the provided `prefs`.                                                                                         |
| **Parameters**                                       | * prefs         - The `prefs` instance.* key           - The key to retrieve.* defaultValue  - The value to return if none is currentl set.                                       |
| **Returns**                                          | * The current value, or `defaultValue` if not set.                                                |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `thing` is a `cp.app.prefs` instance.                                                                                         |
| **Parameters**                                       |  * thing     - The value to check                                       |
| **Returns**                                          |  * `true` if if's a `prefs`, otherwise `false`.                                                |

#### [prop](#prop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.prop(prefs, key[, defaultValue]) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieves the `cp.prop` for the specified key. It can be `watched` for changes.                                                                                         |
| **Parameters**                                       | * prefs         - The `prefs` instance.* key           - The key to get/set.* defaultValue  - The value if no default values is currently set.                                       |
| **Returns**                                          | * The `cp.prop` for the key.                                                |

#### [set](#set)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.set(prefs, key, value) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the key/value for the specified `prefs` instance.                                                                                         |
| **Parameters**                                       | * prefs     - The `prefs` instance.* key       - The key to set.* value     - the new value.                                       |
| **Returns**                                          | * Nothing.                                                |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.watch(prefs, watchFn) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a watch function which will be notified when the preferences change.                                                                                         |
| **Parameters**                                       |  * prefs     - The `prefs` instance to watch. * watchFn   - The function that will get called.                                       |
| **Returns**                                          |  * Nothing                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.new(bundleID) -> cp.app.prefs` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `cp.app.prefs` instance, pointing at the specified `bundleID`.                                                                                         |
| **Parameters**                                       |  * bundleID      The Bundle ID to access preferences for.                                       |
| **Returns**                                          |  * A new `cp.app.prefs` with read/write access to the application's preferences.                                                |

