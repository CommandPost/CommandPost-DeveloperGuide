# [docs](index.md) » cp.ui.Group
---

UI Group.

## API Overview
* Functions - API calls offered directly by the extension
 * [contents](#contents)
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Group](#group)

## API Documentation

### Functions

#### [contents](#contents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Group.contents(element) -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the `AXContents` of the element, if it is an `AXGroup`. |
| **Parameters**                                       | <ul><li>element  - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li>The list of <code>axuielements</code> for the <code>AXContents</code> of the <code>AXGroup</code>, or <code>nil</code>.</li></ul> |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Group.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [Group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Group(parent, uiFinder[, contentsClass]) -> Alert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Group` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li><li>uiFinder - A function which will return the <code>hs._asm.axuielement</code> when available.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Group</code> object.</li></ul> |

