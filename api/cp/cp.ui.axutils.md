# [docs](index.md) » cp.ui.axutils
---

Utility functions to support `hs._asm.axuielement`.

## API Overview
* Functions - API calls offered directly by the extension
 * [cache](#cache)
 * [childAtIndex](#childatindex)
 * [childFromBottom](#childfrombottom)
 * [childFromLeft](#childfromleft)
 * [childFromRight](#childfromright)
 * [childFromTop](#childfromtop)
 * [childMatching](#childmatching)
 * [children](#children)
 * [childrenMatching](#childrenmatching)
 * [childrenWith](#childrenwith)
 * [childrenWithRole](#childrenwithrole)
 * [childWith](#childwith)
 * [childWithDescription](#childwithdescription)
 * [childWithID](#childwithid)
 * [childWithRole](#childwithrole)
 * [compareBottomToTop](#comparebottomtotop)
 * [compareLeftToRight](#comparelefttoright)
 * [compareRightToLeft](#comparerighttoleft)
 * [compareTopToBottom](#comparetoptobottom)
 * [hasAttributeValue](#hasattributevalue)
 * [isValid](#isvalid)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [cache](#cache)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.cache(source, key, finderFn, [verifyFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the cached value at the `source[key]` is a valid axuielement. If not                                                                                         |
| **Parameters**                                       | <ul><li>source		- the table containing the cache</li><li>key			- the key the value is cached under</li><li>finderFn		- the function which will return the element if not found.</li><li>[verifyFn]	- an optional function which will check the cached element to verify it is still valid.</li></ul> |
| **Returns**                                          | <ul><li>The valid cached value.</li></ul>          |

#### [childAtIndex](#childatindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childAtIndex(element, index, compareFn[, matcherFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Searches for the child element which is at number `index` when sorted using the `compareFn`.                                                                                         |
| **Parameters**                                       | <ul><li>element		- the axuielement or array of axuielements</li><li>index		- the index number of the child to find.</li><li>compareFn	- a function to compare the elements.</li><li>matcherFn    - an optional function which is passed each child and returns `true` if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or `nil` if the index is larger than the number of children.</li></ul>          |

#### [childFromBottom](#childfrombottom)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childFromBottom(element, index) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Searches for the child element which is at number `index` when sorted bottom-to-top.                                                                                         |
| **Parameters**                                       | <ul><li>element		- the axuielement or array of axuielements</li><li>index		- the index number of the child to find.</li><li>matcherFn    - an optional function which is passed each child and returns `true` if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or `nil` if the index is larger than the number of children.</li></ul>          |

#### [childFromLeft](#childfromleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childFromLeft(element, index[, matcherFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Searches for the child element which is at number `index` when sorted left-to-right.                                                                                         |
| **Parameters**                                       | <ul><li>element		- the axuielement or array of axuielements</li><li>index		- the index number of the child to find.</li><li>matcherFn    - an optional function which is passed each child and returns `true` if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or `nil` if the index is larger than the number of children.</li></ul>          |

#### [childFromRight](#childfromright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childFromRight(element, index[, matcherFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Searches for the child element which is at number `index` when sorted right-to-left.                                                                                         |
| **Parameters**                                       | <ul><li>element		- the axuielement or array of axuielements</li><li>index		- the index number of the child to find.</li><li>matcherFn    - an optional function which is passed each child and returns `true` if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or `nil` if the index is larger than the number of children.</li></ul>          |

#### [childFromTop](#childfromtop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childFromTop(element, index[, matcherFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Searches for the child element which is at number `index` when sorted top-to-bottom.                                                                                         |
| **Parameters**                                       | <ul><li>element		- the axuielement or array of axuielements</li><li>index		- the index number of the child to find.</li><li>matcherFn    - an optional function which is passed each child and returns `true` if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or `nil` if the index is larger than the number of children.</li></ul>          |

#### [childMatching](#childmatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childMatching(element, matcherFn[, index]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for the first child of the specified element for which the provided function returns `true`.                                                                                         |
| **Parameters**                                       | <ul><li>element		- the axuielement</li><li>matcherFn	- the function which checks if the child matches the requirements.</li><li>index		- the number of matching child to return. Defaults to `1`.</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or nil if none was found</li></ul>          |

#### [children](#children)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.children(element) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Finds the children for the element. If it is an `hs._asm.axuielement`, it will                                                                                         |
| **Parameters**                                       | <ul><li>element   - The element to retrieve the children of.</li></ul> |
| **Returns**                                          | <ul><li>the children table, or `nil`.</li></ul>          |

#### [childrenMatching](#childrenmatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenMatching(element, matcherFn) -> { axuielement }` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for all children of the specified element for which the provided                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>matcherFn	- the function which checks if the child matches the requirements.</li></ul> |
| **Returns**                                          | <ul><li>All matching children, or `nil` if none was found</li></ul>          |

#### [childrenWith](#childrenwith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenWith(element, name, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for all children of the specified element which has an attribute with the matching name and value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>name		- the name of the attribute</li><li>value	- the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>All matching children, or `nil` if none was found</li></ul>          |

#### [childrenWithRole](#childrenwithrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenWithRole(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for all children of the specified element which has an `AXRole` attribute with the matching value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>value	- the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>All matching children, or `nil` if none was found</li></ul>          |

#### [childWith](#childwith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childWith(element, name, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for the first child of the specified element which has an attribute with the matching name and value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>name		- the name of the attribute</li><li>value	- the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or nil if none was found</li></ul>          |

#### [childWithDescription](#childwithdescription)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childWithDescription(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for the first child of the specified element which has `AXDescription` with the specified value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>value	- the value</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or `nil` if none was found</li></ul>          |

#### [childWithID](#childwithid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childWithID(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for the first child of the specified element which has `AXIdentifier` with the specified value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>value	- the value</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or `nil` if none was found</li></ul>          |

#### [childWithRole](#childwithrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childWithRole(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This searches for the first child of the specified element which has `AXRole` with the specified value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li><li>value	- the value</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or `nil` if none was found</li></ul>          |

#### [compareBottomToTop](#comparebottomtotop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.compareBottomToTop(a, b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns `true` if element `a` is below element `b`. May be used with `table.sort`.                                                                                         |
| **Returns**                                          | <ul><li>`true` if `a` is below `b`.</li></ul>          |

#### [compareLeftToRight](#comparelefttoright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.compareLeftToRight(a, b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns `true` if element `a` is left of element `b`. May be used with `table.sort`.                                                                                         |
| **Returns**                                          | <ul><li>`true` if `a` is left of `b`.</li></ul>          |

#### [compareRightToLeft](#comparerighttoleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.compareRightToLeft(a, b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns `true` if element `a` is right of element `b`. May be used with `table.sort`.                                                                                         |
| **Returns**                                          | <ul><li>`true` if `a` is right of `b`.</li></ul>          |

#### [compareTopToBottom](#comparetoptobottom)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.compareTopToBottom(a, b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns `true` if element `a` is above element `b`. May be used with `table.sort`.                                                                                         |
| **Returns**                                          | <ul><li>`true` if `a` is above `b`.</li></ul>          |

#### [hasAttributeValue](#hasattributevalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.hasAttributeValue(element, name, value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element has a specific value.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the `axuielement`</li><li>name		- the name of the attribute</li><li>value	- the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>`true` if the `element` has the supplied attribute value, otherwise `false`.</li></ul>          |

#### [isValid](#isvalid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.isValid(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the axuilelement is still valid - that is, still active in the UI.                                                                                         |
| **Parameters**                                       | <ul><li>element	- the axuielement</li></ul> |
| **Returns**                                          | <ul><li>`true` if the element is valid.</li></ul>          |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.snapshot(element, [filename]) -> hs.image` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Takes a snapshot of the specified `axuielement` and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>element		- The `axuielement` to snap.</li><li>filename		- (optional) The path to save the image as a PNG file.</li></ul> |
| **Returns**                                          | <ul><li>An `hs.image` file, or `nil` if the element could not be snapped.</li></ul>          |

