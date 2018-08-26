# [docs](index.md) » cp.collect.List
---

Lists are similar `tables` which can contain `nil` items without shortening the length.
They also have a few additional methods to assist with managing the size.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [of](#of)
 * [sized](#sized)
* Methods - API calls which can only be made on an object returned by a constructor
 * [size](#size)
 * [trim](#trim)

## API Documentation

### Constructors

#### [of](#of)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.List.of(...) -> cp.collect.List` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `List` with the specified items init. |
| **Parameters**                                       | <ul><li>...       - The items to put in the list, in order.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>List</code> instance.</li></ul> |

#### [sized](#sized)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.List.sized([size[, defaultValue]]) -> cp.collect.List` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `List` with the specified size. |
| **Parameters**                                       | <ul><li>size          - The size of the list. Defaults to <code>0</code>.</li><li>defaultValue  - If specified, all items in the list will be initialised to the default value.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>List</code> instance.</li></ul> |

### Methods

#### [size](#size)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.List:size([newSize]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns and/or sets the current size of the list. |
| **Parameters**                                       | <ul><li>newSize       - if provided, sets the new size of the list. Any values contained above the new size are set to <code>nil</code>.</li></ul> |
| **Returns**                                          | <ul><li>The size of the list.</li></ul> |

#### [trim](#trim)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.List:trim([minSize]) -> cp.collect.List` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Trims the current `List` to only contain trailing values that are not `nil`. |
| **Parameters**                                       | <ul><li>minSize   - If provided, the minimum size to trim down to. Defaults to <code>0</code>.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>List</code> instance.</li></ul> |

