# [docs](index.md) » cp.apple.finalcutpro.axutils
---

Utility functions to support `hs._asm.axuielement`

## API Overview
* Functions - API calls offered directly by the extension
 * [cache](#cache)
 * [childMatching](#childmatching)
 * [childrenMatching](#childrenmatching)
 * [childrenWith](#childrenwith)
 * [childrenWithRole](#childrenwithrole)
 * [childWith](#childwith)
 * [childWithID](#childwithid)
 * [childWithRole](#childwithrole)
 * [isValid](#isvalid)

## API Documentation

### Functions

#### [cache](#cache)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.axutils.cache(source, key, finderFn, verifyFn) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the cached value at the `source[key]` is a valid axuielement. If not                                                                                         |
| **Parameters**                                       | <ul><li>source	- the table containing the cache</li><li>key		- the key the value is cached under</li><li>finderFn	- the function which will return the element if not found.</li><li>verifyFn	- (optional) a function which will check the cached element to verify it is still valid.</li></ul> |
| **Returns**                                          | <ul><li>The valid cached value.</li></ul>          |

#### [childMatching](#childmatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.axutils.childMatching(element, matcherFn) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for the first child of the specified element for which the provided function returns `true`.                                                                                         |
| **Parameters**                                       | <ul><li>element		- the axuielement</li><li>matcherFn	- the function which checks if the child matches the requirements.</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or nil if none was found</li></ul>          |

#### [childrenMatching](#childrenmatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.axutils.childrenMatching(element, matcherFn) -> { axuielement }` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for all children of the specified element for which the provided                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>matcherFn	- the function which checks if the child matches the requirements.</li></ul> |
| **Returns**                                          | <ul><li>All matching children, or `nil` if none was found</li></ul>          |

#### [childrenWith](#childrenwith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.axutils.childrenWith(element, name, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for all children of the specified element which has an attribute with the matching name and value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>name		- the name of the attribute</li><li>value	- the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>All matching children, or `nil` if none was found</li></ul>          |

#### [childrenWithRole](#childrenwithrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.axutils.childrenWithRole(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for all children of the specified element which has an `AXRole` attribute with the matching value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>value	- the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>All matching children, or `nil` if none was found</li></ul>          |

#### [childWith](#childwith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.axutils.childWith(element, name, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for the first child of the specified element which has an attribute with the matching name and value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>name		- the name of the attribute</li><li>value	- the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or nil if none was found</li></ul>          |

#### [childWithID](#childwithid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.axutils.childWithID(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for the first child of the specified element which has `AXIdentifier` with the specified value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>value	- the value</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or `nil` if none was found</li></ul>          |

#### [childWithRole](#childwithrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.axutils.childWithRole(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for the first child of the specified element which has `AXRole` with the specified value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>value	- the value</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or `nil` if none was found</li></ul>          |

#### [isValid](#isvalid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.axutils.isValid(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the axuilelement is still valid - that is, still active in the UI.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li></ul> |
| **Returns**                                          | <ul><li>`true` if the element is valid.</li></ul>          |

