# [docs](index.md) » cp.finalcutpro.axutils
---

Utility functions to support 'axuielement'

## API Overview
* Functions - API calls offered directly by the extension
 * [cached](#cached)
 * [childWith](#childWith)
 * [childrenMatching](#childrenMatching)
 * [childrenWith](#childrenWith)
 * [isValid](#isValid)

## API Documentation

### Functions

#### [cached](#cached)
| **Signature**                               | `cp.finalcutpro.axutils.cached(table, string, function) -> axuielement`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks if the cached value at the `source[key]` is a valid axuielement. If not                                                                     |
| **Parameters**                              | <ul><li>source	- the table containing the cache</li><li>key		- the key the value is cached under</li><li>finderFn	- the function which will return the element if not found.</li><li>verifyFn  - (optional) a function which will check the cached element to verify it is still valid.</li></ul> |
| **Returns**                                 | <ul><li>The valid cached value.</li></ul>          |

#### [childWith](#childWith)
| **Signature**                               | `cp.finalcutpro.axutils.childWith(element, matcherFn) -> axuielement`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | This searches for the first child of the specified element for which the provided function returns true. The function will receive one parameter - the current child.                                                                     |
| **Parameters**                              | <ul><li>element	- the axuielement</li><li>matcherFn	- the function which checks if the child matches the requirements.</li></ul> |
| **Returns**                                 | <ul><li>The first matching child, or nil if none was found</li></ul>          |

#### [childrenMatching](#childrenMatching)
| **Signature**                               | `cp.finalcutpro.axutils.childrenMatching(axuielement, function) -> {axuielement}`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | This searches for all children of the specified element for which the provided                                                                     |
| **Parameters**                              | <ul><li>element	- the axuielement</li><li>matcherFn	- the function which checks if the child matches the requirements.</li></ul> |
| **Returns**                                 | <ul><li>The first matching child, or nil if none was found</li></ul>          |

#### [childrenWith](#childrenWith)
| **Signature**                               | `cp.finalcutpro.axutils.childrenWith(element, string, value) -> axuielement`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | This searches for all children of the specified element which has an attribute with the matching name and value.                                                                     |
| **Parameters**                              | <ul><li>element	- the axuielement</li><li>name		- the name of the attribute</li><li>value	- the value of the attribute</li></ul> |
| **Returns**                                 | <ul><li>The first matching child, or nil if none was found</li></ul>          |

#### [isValid](#isValid)
| **Signature**                               | `cp.finalcutpro.axutils.isValid(axuielement) -> boolean`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks if the axuilelement is still valid                                                                     |
| **Parameters**                              | <ul><li>element	- the axuielement</li><li>matcherFn	- the function which checks if the child matches the requirements.</li></ul> |
| **Returns**                                 | <ul><li>The first matching child, or nil if none was found</li></ul>          |

