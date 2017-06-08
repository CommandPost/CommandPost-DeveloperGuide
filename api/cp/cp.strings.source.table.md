# [docs](index.md) » cp.strings.source.table
---

Loads strings from provided tables, allowing for a given language variation. Eg:

```lua
local src = require("cp.strings.source.table").new():add("en", {foo = "bar"}):add("en", {foo = "baz"})
local valueEn = src:find("en", "foo") -- "bar"
local valueEs = src:find("en", "foo") -- "baz"
```

This will load the file for the specified language (replacing `${language}` with `"en"` in the path) and return the value.
Note: This will load the file on each request. To have values cached, use the `cp.strings` module and specify a `plist` as a source.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [find](#find)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.table.new(language) -> source` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `cp.strings` source that loads strings from a plist file.                                                                                         |
| **Parameters**                                       | <ul><li>`pathPattern`	- The path to load from. May contain a special `${language}` marker which will be replace with the provided langauge when searching.</li><li>`cacheSeconds`	- (optional) How long in seconds to keep the loaded values cached in memory. Defaults to [defaultCacheSeconds](#defaultCacheSeconds)</li></ul> |
| **Returns**                                          | <ul><li>The new plist `source` instance.</li></ul>          |

### Methods

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.table:find(language) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the specified `key` value in the plist file for the specified `language`, if the plist can be found, and contains matching key value.                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to look for (e.g. `"en"`, or `"fr"`).</li><li>`key`		- The key to retrieve from the file.</li></ul> |
| **Returns**                                          | <ul><li>The value of the key, or `nil` if not found.</li></ul>          |

