# [docs](index.md) » cp.strings.source.plist
---

Loads strings from a `plist` with allowing for a given language variation. Eg:

```lua
local plistSource = require("cp.strings.source.plist").new("/Path/To/Resources/${language}.lproj/MYLocalization.strings")
local value = plistSource:find("en", "AKey")
```

This will load the file for the specified language (replacing `${language}` with `"en"` in the path) and return the value.
Note: This will load the file on each request. To have values cached, use the `cp.strings` module and specify a `plist` as a source.

## API Overview
* Constants - Useful values which cannot be changed
 * [defaultCacheSeconds](#defaultcacheseconds)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [context](#context)
 * [find](#find)
 * [findKeys](#findkeys)
 * [loadFile](#loadfile)
 * [pathToAbsolute](#pathtoabsolute)
 * [reset](#reset)

## API Documentation

### Constants

#### [defaultCacheSeconds](#defaultcacheseconds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist.defaultCacheSeconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The default number of seconds to cache results. |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist.new(pathPattern[, cacheSeconds]) -> source` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `cp.strings` source that loads strings from a plist file. |
| **Parameters**                                       | <ul><li><code>pathPattern</code>    - The path to load from. May contain a special <code>${language}</code> marker which will be replace with the provided langauge when searching. * <code>cacheSeconds</code>   - (optional) How long in seconds to keep the loaded values cached in memory. Defaults to <a href="#defaultCacheSeconds">defaultCacheSeconds</a></li></ul> |
| **Returns**                                          | <ul><li>The new plist <code>source</code> instance.</li></ul> |

### Methods

#### [context](#context)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:context([context]) -> table | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets a context to be set for the source. This typically includes a `language`, which |
| **Parameters**                                       | <ul><li>context   - A table with values which may be used by the source.</li></ul> |
| **Returns**                                          | <ul><li>If a new context is provided, the <code>cp.string.source</code> is returned, otherwise the current context table is returned.</li></ul> |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:find(key[, context]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the specified `key` value in the plist, if the plist can be found, and contains matching key value. |
| **Parameters**                                       | <ul><li><code>key</code>        - The key to retrieve from the file. * <code>context</code>    - Optional table with additional/alternate context. It will be added to the current context temporarily.</li></ul> |
| **Returns**                                          | <ul><li>The value of the key, or <code>nil</code> if not found.</li></ul> |

#### [findKeys](#findkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:findKeys(pattern) -> {string}` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the array of keys who's value matches the pattern in this table. It will check that the pattern matches the beginning of the value. |
| **Parameters**                                       | <ul><li><code>pattern     - The string pattern to match. *</code>context`  - An optional additional context for the source.</li></ul> |
| **Returns**                                          | <ul><li>The array of keys, or <code>{}</code> if none were fround</li></ul> |

#### [loadFile](#loadfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:loadFile([context]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads the plist file for the specified context, returning the value as a table. |
| **Parameters**                                       | <ul><li><code>context</code>    - The context to determine the absolute path with. This will be added to any values provided in the default <a href="#context">context</a>.</li></ul> |
| **Returns**                                          | <ul><li>The table for the specified language, or <code>nil</code> if the file doesn't exist.</li></ul> |

#### [pathToAbsolute](#pathtoabsolute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:pathToAbsolute([context]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the abolute path to the `plist` represented by this source for the specified langauge, or `nil` if it does not exist. |
| **Parameters**                                       | <ul><li><code>context</code>    - The context to determine the absolute path with. This will be added to any values provided in the default <a href="#context">context</a>.</li></ul> |
| **Returns**                                          | <ul><li>The path to the file, or <code>nil</code> if not found.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:reset() -> cp.strings` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Clears any stored key values. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The current <code>cp.strings</code> instance.</li></ul> |

