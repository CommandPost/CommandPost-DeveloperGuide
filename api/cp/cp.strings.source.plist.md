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
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default number of seconds to cache results.                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist.new(language) -> source` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `cp.strings` source that loads strings from a plist file.                                                                                         |
| **Parameters**                                       | <ul><li>`pathPattern`	- The path to load from. May contain a special `${language}` marker which will be replace with the provided langauge when searching.</li><li>`cacheSeconds`	- (optional) How long in seconds to keep the loaded values cached in memory. Defaults to [defaultCacheSeconds](#defaultCacheSeconds)</li></ul> |
| **Returns**                                          | <ul><li>The new plist `source` instance.</li></ul>          |

### Methods

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:find(language, key) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the specified `key` value in the plist file for the specified `language`, if the plist can be found, and contains matching key value.                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to look for (e.g. `"en"`, or `"fr"`).</li><li>`key`		- The key to retrieve from the file.</li></ul> |
| **Returns**                                          | <ul><li>The value of the key, or `nil` if not found.</li></ul>          |

#### [findKeys](#findkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:findKeys(language, pattern) -> {string}` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the array of keys who's value matches the pattern in this table. It will check that the pattern matches the beginning of the value.                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to look for (e.g. `"en"`, or `"fr"`).</li><li>`pattern		- The string pattern to match.</li></ul> |
| **Returns**                                          | <ul><li>The array of keys, or `{}` if none were fround</li></ul>          |

#### [loadFile](#loadfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:loadFile(language) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads the plist file for the specified language, returning the value as a table.                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to look for (e.g. `"en"`, or `"fr"`).</li></ul> |
| **Returns**                                          | <ul><li>The table for the specified language, or `nil` if the file doesn't exist.</li></ul>          |

#### [pathToAbsolute](#pathtoabsolute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:pathToAbsolute(language) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the abolute path to the `plist` represented by this source for the specified langauge, or `nil` if it does not exist.                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to look for (e.g. `"en"`, or `"fr"`).</li></ul> |
| **Returns**                                          | <ul><li>The path to the file, or `nil` if not found.</li></ul>          |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.plist:reset() -> cp.strings` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Clears any stored key values.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The current `cp.strings` instance.</li></ul>          |

