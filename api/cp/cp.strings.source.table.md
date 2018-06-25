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
 * [add](#add)
 * [context](#context)
 * [find](#find)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.table.new(context) -> source` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `cp.strings` source that loads strings from a plist file. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The new plist <code>source</code> instance.</li></ul> |

### Methods

#### [add](#add)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.table:add(keyValues) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds the specified table of key values in the specified language code. |
| **Parameters**                                       | <ul><li><code>keyValues</code>  - The table of key/value pairs to define.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.string.source</code>.</li></ul> |

#### [context](#context)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.table:context([context]) -> table | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets a context to be set for the source. This typically includes a `language`, which |
| **Parameters**                                       | <ul><li>context   - A table with values which may be used by the source.</li></ul> |
| **Returns**                                          | <ul><li>If a new context is provided, the <code>cp.string.source</code> is returned, otherwise the current context table is returned.</li></ul> |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.strings.source.table:find(key) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the specified `key` value in the plist file for the specified optional `context`, |
| **Parameters**                                       | <ul><li><code>key</code>        - The key to retrieve the value for. * <code>context</code>    - An optional table with additional context.</li></ul> |
| **Returns**                                          | <ul><li>The value of the key, or <code>nil</code> if not found.</li></ul> |

