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
 * [context](#context)
 * [find](#find)
 * [findInSources](#findinsources)
 * [findKeys](#findkeys)
 * [findKeysInSources](#findkeysinsources)
 * [from](#from)
 * [fromPlist](#fromplist)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.new(context) -> cp.strings` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `strings` instance. You should add sources with the [from](#from) or [fromPlist](#fromPlist) methods. |
| **Parameters**                                       | <ul><li>context      - The initial context.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>cp.strings</code></li></ul> |

### Methods

#### [context](#context)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:context([context]) -> table | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets a context to be set for the strings. This typically includes a `language`, which |
| **Parameters**                                       | <ul><li>context   - A table with values which may be used by the source.</li></ul> |
| **Returns**                                          | <ul><li>If a new context is provided, the <code>cp.string.source</code> is returned, otherwise the current context table is returned.</li></ul> |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:find(key[, context[, quiet]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Searches for the specified key, caching the result when found. |
| **Parameters**                                       | <ul><li><code>key</code>        - The key to retrieve from the file.</li><li><code>context</code>    - Optional table with additional/alternate context.</li><li><code>quiet</code>      - Optional boolean, defaults to <code>false</code>. If <code>true</code>, no warnings are logged for missing keys.</li></ul> |
| **Returns**                                          | <ul><li>The value of the key, or <code>nil</code> if not found.</li></ul> |

#### [findInSources](#findinsources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:findInSources(key[, context[, quiet]]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Searches directly in the sources for the specified key. |
| **Parameters**                                       | <ul><li><code>key</code>        - The key to retrieve from the file.</li><li><code>context</code>    - Optional table with additional/alternate context.</li><li><code>quiet</code>      - Optional boolean, defaults to <code>false</code>. If <code>true</code>, no warnings are logged for missing keys.</li></ul> |
| **Returns**                                          | <ul><li>The value of the key, or <code>nil</code> if not found.</li></ul> |

#### [findKeys](#findkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:findKeys(value[, context]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Searches for the list of keys with a matching value, in the specified language. |
| **Parameters**                                       | <ul><li><code>value</code>      - The value to search for.</li><li><code>context</code>    - The language code to look for (e.g. <code>"en"</code>, or <code>"fr"</code>).</li></ul> |
| **Returns**                                          | <ul><li>The array of keys, or <code>{}</code> if not found.</li></ul> |

#### [findKeysInSources](#findkeysinsources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:findKeysInSources(value[, context]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Searches directly in the sources for the specified key value pattern. |
| **Parameters**                                       | <ul><li><code>value</code>      - The value to search for.</li><li><code>context</code>    - Optional additional context for the request.</li></ul> |
| **Returns**                                          | <ul><li>The array of keys, or <code>{}</code> if not found.</li></ul> |

#### [from](#from)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:from(source) -> cp.strings` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds the source to the strings sources. |
| **Parameters**                                       | <ul><li><code>source</code>     - The source to add.</li></ul> |
| **Returns**                                          | <ul><li>The current <code>cp.strings</code> instance.</li></ul> |

#### [fromPlist](#fromplist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings:fromPlist(pathPattern) -> cp.strings` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Convenience method for adding a `plist` source to the strings instance. |
| **Parameters**                                       | <ul><li><code>pathPattern</code>    - The path to load from. May contain a special <code>${language}</code> marker which will be replace with the provided langauge when searching.</li></ul> |
| **Returns**                                          | <ul><li>The current <code>cp.strings</code> instance.</li></ul> |

