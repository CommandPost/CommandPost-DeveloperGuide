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
 * [childInColumn](#childincolumn)
 * [childIndex](#childindex)
 * [childMatching](#childmatching)
 * [children](#children)
 * [childrenAbove](#childrenabove)
 * [childrenBelow](#childrenbelow)
 * [childrenInColumn](#childrenincolumn)
 * [childrenInLine](#childreninline)
 * [childrenInNextLine](#childreninnextline)
 * [childrenMatching](#childrenmatching)
 * [childrenWith](#childrenwith)
 * [childrenWithRole](#childrenwithrole)
 * [childWith](#childwith)
 * [childWithDescription](#childwithdescription)
 * [childWithID](#childwithid)
 * [childWithRole](#childwithrole)
 * [childWithTitle](#childwithtitle)
 * [compareBottomToTop](#comparebottomtotop)
 * [compareLeftToRight](#comparelefttoright)
 * [compareRightToLeft](#comparerighttoleft)
 * [compareTopToBottom](#comparetoptobottom)
 * [hasAttributeValue](#hasattributevalue)
 * [hasChild](#haschild)
 * [isValid](#isvalid)
 * [prop](#prop)
 * [role](#role)
 * [snapshot](#snapshot)
 * [valueOf](#valueof)
 * [withAttributeValue](#withattributevalue)
 * [withRole](#withrole)
 * [withTitle](#withtitle)
 * [withValue](#withvalue)

## API Documentation

### Functions

#### [cache](#cache)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.cache(source, key, finderFn[, verifyFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the cached value at the `source[key]` is a valid axuielement. If not |
| **Parameters**                                       | <ul><li>source       - the table containing the cache</li><li>key          - the key the value is cached under</li><li>finderFn     - the function which will return the element if not found.</li><li>[verifyFn]   - an optional function which will check the cached element to verify it is still valid.</li></ul> |
| **Returns**                                          | <ul><li>The valid cached value.</li></ul> |

#### [childAtIndex](#childatindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childAtIndex(element, index, compareFn[, matcherFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Searches for the child element which is at number `index` when sorted using the `compareFn`. |
| **Parameters**                                       | <ul><li>element      - the axuielement or array of axuielements</li><li>index        - the index number of the child to find.</li><li>compareFn    - a function to compare the elements.</li><li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or <code>nil</code> if the index is larger than the number of children.</li></ul> |

#### [childFromBottom](#childfrombottom)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childFromBottom(element, index) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Searches for the child element which is at number `index` when sorted bottom-to-top. |
| **Parameters**                                       | <ul><li>element      - the axuielement or array of axuielements</li><li>index        - the index number of the child to find.</li><li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or <code>nil</code> if the index is larger than the number of children.</li></ul> |

#### [childFromLeft](#childfromleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childFromLeft(element, index[, matcherFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Searches for the child element which is at number `index` when sorted left-to-right. |
| **Parameters**                                       | <ul><li>element      - the axuielement or array of axuielements</li><li>index        - the index number of the child to find.</li><li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or <code>nil</code> if the index is larger than the number of children.</li></ul> |

#### [childFromRight](#childfromright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childFromRight(element, index[, matcherFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Searches for the child element which is at number `index` when sorted right-to-left. |
| **Parameters**                                       | <ul><li>element      - the axuielement or array of axuielements</li><li>index        - the index number of the child to find.</li><li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or <code>nil</code> if the index is larger than the number of children.</li></ul> |

#### [childFromTop](#childfromtop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childFromTop(element, index[, matcherFn]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Searches for the child element which is at number `index` when sorted top-to-bottom. |
| **Parameters**                                       | <ul><li>element      - the axuielement or array of axuielements</li><li>index        - the index number of the child to find.</li><li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li></ul> |
| **Returns**                                          | <ul><li>The child, or <code>nil</code> if the index is larger than the number of children.</li></ul> |

#### [childInColumn](#childincolumn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childInColumn(element, role, startIndex, childIndex) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Finds the children for an element, then checks to see if they match the supplied |
| **Parameters**                                       | <ul><li>element     - The element to retrieve the children from.</li><li>role        - The required role as a string.</li><li>startIndex  - A number which defines the index of the first element to use.</li><li>childIndex  - A number which defines the index of the element to return.</li></ul> |
| **Returns**                                          | <ul><li>The <code>axuielement</code> if it matches, otherwise <code>nil</code>.</li></ul> |

#### [childIndex](#childindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childIndex(element) -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Finds the index of the specified child element, if it is present. If not, `nil` is returned. |
| **Parameters**                                       | <ul><li>element - The <code>axuielement</code> to find the index of.</li></ul> |
| **Returns**                                          | <ul><li>The index (<code>1</code> or higher) of the <code>element</code>, or <code>nil</code> if it was not found.</li></ul> |

#### [childMatching](#childmatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childMatching(element, matcherFn[, index]) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This searches for the first child of the specified element for which the provided function returns `true`. |
| **Parameters**                                       | <ul><li>element      - the axuielement</li><li>matcherFn    - the function which checks if the child matches the requirements.</li><li>index        - the number of matching child to return. Defaults to <code>1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or nil if none was found</li></ul> |

#### [children](#children)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.children(element[, compareFn]) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Finds the children for the element. If it is an `hs._asm.axuielement`, it will |
| **Parameters**                                       | <ul><li>element      - The element to retrieve the children of.</li><li>compareFn    - Optional function to use to sort the order of the returned children.</li></ul> |
| **Returns**                                          | <ul><li>the children table, or <code>nil</code>.</li></ul> |

#### [childrenAbove](#childrenabove)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenAbove(element, bottomElement) -> table of axuielement or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Finds the list of `axuielement` children from the `element` which are above the specified `bottomElement`. |
| **Parameters**                                       | <ul><li>element - The <code>axuielement</code> to find the children of.</li><li>topElement - The <code>axuielement</code> that the other children must be above.</li></ul> |
| **Returns**                                          | <ul><li>The table of <code>axuielements</code> that are above, or <code>nil</code> if the element is not available.</li></ul> |

#### [childrenBelow](#childrenbelow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenBelow(element, topElement) -> table of axuielement or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Finds the list of `axuielement` children from the `element` which are below the specified `topElement`. |
| **Parameters**                                       | <ul><li>element - The <code>axuielement</code> to find the children of.</li><li>topElement - The <code>axuielement</code> that the other children must be below.</li></ul> |
| **Returns**                                          | <ul><li>The table of <code>axuielements</code> that are below, or <code>nil</code> if the element is not available.</li></ul> |

#### [childrenInColumn](#childrenincolumn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenInColumn(element, role, startIndex) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Finds the children for an element, then checks to see if they match the supplied |
| **Parameters**                                       | <ul><li>element     - The element to retrieve the children from.</li><li>role        - The required role as a string.</li><li>startIndex  - A number which defines the index of the first element to use.</li></ul> |
| **Returns**                                          | <ul><li>The table of <code>axuielement</code> objects, otherwise <code>nil</code>.</li></ul> |

#### [childrenInLine](#childreninline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenInLine(element) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a table of children that are all in the same family and line as the |
| **Parameters**                                       | <ul><li>element     - The base element.</li></ul> |
| **Returns**                                          | <ul><li>The table of <code>axuielement</code> objects, otherwise <code>nil</code>.</li></ul> |

#### [childrenInNextLine](#childreninnextline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenInNextLine(element) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a table of children that are in the next line in relation to the supplied |
| **Parameters**                                       | <ul><li>element - The base element.</li></ul> |
| **Returns**                                          | <ul><li>The table of <code>axuielement</code> objects, otherwise <code>nil</code>.</li></ul> |

#### [childrenMatching](#childrenmatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenMatching(element, matcherFn) -> { axuielement }` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This searches for all children of the specified element for which the provided |
| **Parameters**                                       | <ul><li>element  - the axuielement</li><li>matcherFn    - the function which checks if the child matches the requirements.</li></ul> |
| **Returns**                                          | <ul><li>All matching children, or <code>nil</code> if none was found</li></ul> |

#### [childrenWith](#childrenwith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenWith(element, name, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This searches for all children of the specified element which has an attribute with the matching name and value. |
| **Parameters**                                       | <ul><li>element  - the axuielement</li><li>name     - the name of the attribute</li><li>value    - the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>All matching children, or <code>nil</code> if none was found</li></ul> |

#### [childrenWithRole](#childrenwithrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childrenWithRole(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This searches for all children of the specified element which has an `AXRole` attribute with the matching value. |
| **Parameters**                                       | <ul><li>element  - the axuielement</li><li>value    - the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>All matching children, or <code>nil</code> if none was found</li></ul> |

#### [childWith](#childwith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childWith(element, name, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This searches for the first child of the specified element which has an attribute with the matching name and value. |
| **Parameters**                                       | <ul><li>element  - the axuielement</li><li>name     - the name of the attribute</li><li>value    - the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or nil if none was found</li></ul> |

#### [childWithDescription](#childwithdescription)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childWithDescription(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This searches for the first child of the specified element which has `AXDescription` with the specified value. |
| **Parameters**                                       | <ul><li>element  - the axuielement</li><li>value    - the value</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or <code>nil</code> if none was found</li></ul> |

#### [childWithID](#childwithid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childWithID(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This searches for the first child of the specified element which has `AXIdentifier` with the specified value. |
| **Parameters**                                       | <ul><li>element  - the axuielement</li><li>value    - the value</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or <code>nil</code> if none was found</li></ul> |

#### [childWithRole](#childwithrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childWithRole(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This searches for the first child of the specified element which has `AXRole` with the specified value. |
| **Parameters**                                       | <ul><li>element  - the axuielement</li><li>value    - the value</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or <code>nil</code> if none was found</li></ul> |

#### [childWithTitle](#childwithtitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.childWithTitle(element, value) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This searches for the first child of the specified element which has `AXTitle` with the specified value. |
| **Parameters**                                       | <ul><li>element  - the axuielement</li><li>value    - the value</li></ul> |
| **Returns**                                          | <ul><li>The first matching child, or <code>nil</code> if none was found</li></ul> |

#### [compareBottomToTop](#comparebottomtotop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.compareBottomToTop(a, b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns `true` if element `a` is below element `b`. May be used with `table.sort`. |
| **Returns**                                          | <ul><li><code>true</code> if <code>a</code> is below <code>b</code>.</li></ul> |

#### [compareLeftToRight](#comparelefttoright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.compareLeftToRight(a, b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns `true` if element `a` is left of element `b`. May be used with `table.sort`. |
| **Returns**                                          | <ul><li><code>true</code> if <code>a</code> is left of <code>b</code>.</li></ul> |

#### [compareRightToLeft](#comparerighttoleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.compareRightToLeft(a, b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns `true` if element `a` is right of element `b`. May be used with `table.sort`. |
| **Returns**                                          | <ul><li><code>true</code> if <code>a</code> is right of <code>b</code>.</li></ul> |

#### [compareTopToBottom](#comparetoptobottom)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.compareTopToBottom(a, b) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns `true` if element `a` is above element `b`. May be used with `table.sort`. |
| **Returns**                                          | <ul><li><code>true</code> if <code>a</code> is above <code>b</code>.</li></ul> |

#### [hasAttributeValue](#hasattributevalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.hasAttributeValue(element, name, value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element has a specific value. |
| **Parameters**                                       | <ul><li>element  - the <code>axuielement</code></li><li>name     - the name of the attribute</li><li>value    - the value of the attribute</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the <code>element</code> has the supplied attribute value, otherwise <code>false</code>.</li></ul> |

#### [hasChild](#haschild)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.hasChild(element, matcherFn) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the axuielement has a child that passes the `matcherFn`. |
| **Parameters**                                       | <ul><li>element - the <code>axuielement</code> to check.</li><li>matcherFn - the <code>function</code> that accepts an <code>axuielement</code> and returns a <code>boolean</code></li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if any child matches, otherwise <code>false</code>.</li></ul> |

#### [isValid](#isvalid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.isValid(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the axuilelement is still valid - that is, still active in the UI. |
| **Parameters**                                       | <ul><li>element  - the axuielement</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is valid.</li></ul> |

#### [prop](#prop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.prop(uiFinder, attributeName[, settable]) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new `cp.prop` which will find the `hs._asm.axuielement` via the `uiFinder` and |
| **Parameters**                                       | <ul><li>uiFinder      - the <code>cp.prop</code> or <code>function</code> which will retrieve the current <code>hs._asm.axuielement</code>.</li><li>attributeName - the <code>AX</code> atrribute name the property links to.</li><li>settable      - Defaults to <code>false</code>. If <code>true</code>, the property will also be settable.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.prop</code> for the attribute.</li></ul> |
| **Notes**                                            | <ul><li>If the <code>uiFinder</code> is a <code>cp.prop</code>, it will be monitored for changes, making the resulting <code>prop</code> "live".</li></ul> |

#### [role](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.match.role(roleName) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a `match` function that will return true if the `axuielement` has the specified `AXRole`. |
| **Parameters**                                       | <ul><li>roleName  - The role to check for.</li></ul> |
| **Returns**                                          | <ul><li><code>function(element) -&gt; boolean</code> that checks the <code>AXRole</code> is <code>roleName</code></li></ul> |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.snapshot(element[, filename]) -> hs.image` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Takes a snapshot of the specified `axuielement` and returns it. |
| **Parameters**                                       | <ul><li>element      - The <code>axuielement</code> to snap.</li><li>filename     - (optional) The path to save the image as a PNG file.</li><li>elementFrame - (optional) The hs.geometry frame of what you want to capture</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.image</code> file, or <code>nil</code> if the element could not be snapped.</li></ul> |

#### [valueOf](#valueof)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.valueOf(element, name[, default]) -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the named `AX` attribute value, or the `default` if it is empty. |
| **Parameters**                                       | <ul><li>element - the <code>axuielement</code> to retrieve the attribute value for.</li><li>attribute - The attribute name (e.g. "AXValue")</li><li>default - (optional) if provided, this will be returned if the attribute is <code>nil</code>.</li></ul> |
| **Returns**                                          | <ul><li>The attribute value, or the <code>default</code> if none is found.</li></ul> |

#### [withAttributeValue](#withattributevalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.withAttributeValue(element, name, value) -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element has an attribute value with the specified `name` and `value`. |
| **Parameters**                                       | <ul><li>element       - The element to check</li><li>name          - The name of the attribute to check</li><li>value         - The value of the attribute</li></ul> |
| **Returns**                                          | <ul><li>The <code>axuielement</code> if it matches, otherwise <code>nil</code>.</li></ul> |

#### [withRole](#withrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.withRole(element, role) -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element has an "AXRole" attribute with the specified `role`. |
| **Parameters**                                       | <ul><li>element       - The element to check</li><li>role          - The required role</li></ul> |
| **Returns**                                          | <ul><li>The <code>axuielement</code> if it matches, otherwise <code>nil</code>.</li></ul> |

#### [withTitle](#withtitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.withTitle(element, title) -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element has an "AXTitle" attribute with the specified `title`. |
| **Parameters**                                       | <ul><li>element       - The element to check</li><li>title         - The required title</li></ul> |
| **Returns**                                          | <ul><li>The <code>axuielement</code> if it matches, otherwise <code>nil</code>.</li></ul> |

#### [withValue](#withvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.axutils.withValue(element, value) -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element has an "AXValue" attribute with the specified `value`. |
| **Parameters**                                       | <ul><li>element       - The element to check</li><li>value         - The required value</li></ul> |
| **Returns**                                          | <ul><li>The <code>axuielement</code> if it matches, otherwise <code>nil</code>.</li></ul> |

