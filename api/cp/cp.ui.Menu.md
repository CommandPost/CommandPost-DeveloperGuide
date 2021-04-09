# [docs](index.md) » cp.ui.Menu
---

UI for AXMenus.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Menu](#menu)
* Methods - API calls which can only be made on an object returned by a constructor
 * [cancel](#cancel)
 * [doSelectItem](#doselectitem)
 * [doSelectValue](#doselectvalue)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Menu.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [Menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Menu(parent, uiFinder) -> Menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Menu` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li><li>uiFinder - A function which will return the <code>hs._asm.axuielement</code> when available.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Menu</code> object.</li></ul> |

### Methods

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Menu:cancel() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Closes a menu. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [doSelectItem](#doselectitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Menu:doSelectItem(index) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will select an item on the `MenuButton` by index. |
| **Parameters**                                       | <ul><li>index - The index number of the item to match.</li></ul> |
| **Returns**                                          | <ul><li>the <code>Statement</code>.</li></ul> |

#### [doSelectValue](#doselectvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Menu:doSelectValue(pattern[, altPattern]) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will select an item on the `Menu` by value. |
| **Parameters**                                       | <ul><li>pattern - The pattern to match.</li><li>[altPattern] - An optional alternate pattern to match if the first pattern fails.</li></ul> |
| **Returns**                                          | <ul><li>the <code>Statement</code>.</li></ul> |

