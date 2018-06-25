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
| **Parameters**                                       | <ul><br /><li>prefs     - the <code>prefs</code> object to query</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The Bundle ID string, or <code>nil</code> if it's not a <code>cp.app.prefs</code>.</li><br /></ul>                                           |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.get(prefs, key[, defaultValue])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieves the specifed `key` from the provided `prefs`.                                                                                         |
| **Parameters**                                       | <ul><br /><li>prefs         - The <code>prefs</code> instance.<em> key           - The key to retrieve.</em> defaultValue  - The value to return if none is currentl set.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The current value, or <code>defaultValue</code> if not set.</li><br /></ul>                                           |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `thing` is a `cp.app.prefs` instance.                                                                                         |
| **Parameters**                                       | <ul><br /><li>thing     - The value to check</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if if's a <code>prefs</code>, otherwise <code>false</code>.</li><br /></ul>                                           |

#### [prop](#prop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.prop(prefs, key[, defaultValue]) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Retrieves the `cp.prop` for the specified key. It can be `watched` for changes.                                                                                         |
| **Parameters**                                       | <ul><br /><li>prefs         - The <code>prefs</code> instance.<em> key           - The key to get/set.</em> defaultValue  - The value if no default values is currently set.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>cp.prop</code> for the key.</li><br /></ul>                                           |

#### [set](#set)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.set(prefs, key, value) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the key/value for the specified `prefs` instance.                                                                                         |
| **Parameters**                                       | <ul><br /><li>prefs     - The <code>prefs</code> instance.<em> key       - The key to set.</em> value     - the new value.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Nothing.</li><br /></ul>                                           |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.watch(prefs, watchFn) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a watch function which will be notified when the preferences change.                                                                                         |
| **Parameters**                                       | <ul><br /><li>prefs     - The <code>prefs</code> instance to watch. * watchFn   - The function that will get called.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Nothing</li><br /></ul>                                           |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.prefs.new(bundleID) -> cp.app.prefs` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `cp.app.prefs` instance, pointing at the specified `bundleID`.                                                                                         |
| **Parameters**                                       | <ul><br /><li>bundleID      The Bundle ID to access preferences for.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A new <code>cp.app.prefs</code> with read/write access to the application's preferences.</li><br /></ul>                                           |

