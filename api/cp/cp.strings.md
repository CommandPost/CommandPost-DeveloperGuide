# [docs](index.md) » cp.strings
---

Provides strings from (potentially) multiple sources, with support for loading from multiple languages.

```lua
local strs = require("cp.strings").new():fromPlist("/Path/To/Resources/${language}.lproj/MYLocalization.strings")
local value = strs:find("en", "AKey")
```

This will load the file for the specified language (replacing `${language}` with `"en"` in the path) and return the value.
Note: This will load the file on each request. To have values cached, use the `cp.strings` module and specify a `plist` as a source.

## Submodules
 * [cp.strings.source](cp.strings.source.md)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [find](#find)
 * [findInSources](#findinsources)
 * [findKeysIn](#findkeysin)
 * [findKeysInSources](#findkeysinsources)
 * [from](#from)
 * [fromPlist](#fromplist)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.new() -> cp.strings` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `strings` instance. You should add sources with the [from](#from) or [fromPlist](#fromPlist) methods.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The new `cp.strings`</li></ul>          |

### Methods

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:find(language, key[, quiet]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Searches for the specified key in the specified language, caching the result when found.                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to look for (e.g. `"en"`, or `"fr"`).</li><li>`key`		- The key to retrieve from the file.</li><li>`quiet`		- Optional boolean, defaults to `false`. If `true`, no warnings are logged for missing keys.</li></ul> |
| **Returns**                                          | <ul><li>The value of the key, or `nil` if not found.</li></ul>          |

#### [findInSources](#findinsources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:findInSources(language, key[, quiet]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Searches directly in the sources for the specified language/key combination.                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to look for (e.g. `"en"`, or `"fr"`).</li><li>`key`		- The key to retrieve from the file.</li><li>`quiet`		- Optional boolean, defaults to `false`. If `true`, no warnings are logged for missing keys.</li></ul> |
| **Returns**                                          | <ul><li>The value of the key, or `nil` if not found.</li></ul>          |

#### [findKeysIn](#findkeysin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:findKeysIn(language, value) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Searches for the list of keys with a matching value, in the specified language.                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to look for (e.g. `"en"`, or `"fr"`).</li><li>`value`		- The value to search for.</li></ul> |
| **Returns**                                          | <ul><li>The array of keys, or `{}` if not found.</li></ul>          |

#### [findKeysInSources](#findkeysinsources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:findKeysInSources(language, value) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Searches directly in the sources for the specified language/value combination.                                                                                         |
| **Parameters**                                       | <ul><li>`language`	- The language code to look for (e.g. `"en"`, or `"fr"`).</li><li>`value`		- The value to search for.</li></ul> |
| **Returns**                                          | <ul><li>The array of keys, or `{}` if not found.</li></ul>          |

#### [from](#from)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:from(source) -> cp.strings` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the source to the strings sources.                                                                                         |
| **Parameters**                                       | <ul><li>`source`		- The source to add.</li></ul> |
| **Returns**                                          | <ul><li>The current `cp.strings` instance.</li></ul>          |

#### [fromPlist](#fromplist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:fromPlist(pathPattern) -> cp.strings` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Convenience method for addedn a `plist` source to the strings instance.                                                                                         |
| **Parameters**                                       | <ul><li>`pathPattern`	- The path to load from. May contain a special `${language}` marker which will be replace with the provided langauge when searching.</li></ul> |
| **Returns**                                          | <ul><li>The current `cp.strings` instance.</li></ul>          |

