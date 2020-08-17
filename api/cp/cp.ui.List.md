# [docs](index.md) » cp.ui.List
---

Represents an `AXList` `axuielement` value.

Extends [Element](cp.ui.Element.md).

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [List](#list)
* Methods - API calls which can only be made on an object returned by a constructor
 * [items](#items)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.List.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided `axuielement` is an `AXList`. |
| **Parameters**                                       | <ul><li>element  - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it is an <code>AXList</code>, otherwise <code>false</code>.</li></ul> |

### Constructors

#### [List](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.List(parent, uiFinder, itemAdaptorFn)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new List. |
| **Parameters**                                       | <ul><li>parent       - The parent table. Should have a <code>isShowing</code> property.</li><li>uiFinder      - The <code>function</code> or <code>cp.prop</code> that provides the current <code>hs._asm.axuielement</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>List</code> instance.</li></ul> |

### Methods

#### [items](#items)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.List:items() -> table of values` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the children as items, as adapted by the `itemAdaptor` in the constructor |

