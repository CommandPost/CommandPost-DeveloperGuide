# [docs](index.md) » plugins.core.tangent.manager.menu
---

Represents a Tangent Menu. Menus are controls that have a fixed set of
non-numerical values. This could be as simple as "On" and "Off", or a long
list of options.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [controls](#controls)
 * [get](#get)
 * [next](#next)
 * [onGet](#onget)
 * [onNext](#onnext)
 * [onPrev](#onprev)
 * [parent](#parent)
 * [prev](#prev)
 * [update](#update)
 * [xml](#xml)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu.is(other) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `other` is a `menu` instance.                                                                                         |
| **Parameters**                                       | * other     - The other object to test.                                       |
| **Returns**                                          | * `true` if it is a `menu`, `false` if not.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu.new(id[, name[, parent]]) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Action` instance.                                                                                         |
| **Parameters**                                       | * id        - The ID number of the menu.* name      - The name of the menu.* parent    - The parent of the menu.                                       |
| **Returns**                                          | * the new `menu`.                                                |

### Methods

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:controls()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `controls` the menu belongs to.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `controls`, or `nil` if not specified.                                                |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:get() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `get` function, if present, returning the string value for the current menu.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `nil`                                                |

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:next() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `next` function, if present.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `nil`                                                |

#### [onGet](#onget)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onGet(getFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a `menu string request`.                                                                                         |
| **Parameters**                                       | * getFn     - The function to call when the Tangent requests the `menu string`.                                       |
| **Returns**                                          | * The `parameter` instance.                                                |

#### [onNext](#onnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onNext(nextFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a `menu change +1` request.                                                                                         |
| **Parameters**                                       | * nextFn     - The function to call when the Tangent requests the `menu change +1`.                                       |
| **Returns**                                          | * The `parameter` instance.                                                |

#### [onPrev](#onprev)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onPrev(prevFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a `menu change -1` request.                                                                                         |
| **Parameters**                                       | * prevFn     - The function to call when the Tangent requests the `menu change -1`.                                       |
| **Returns**                                          | * The `parameter` instance.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `group` or `controls` that contains this menu.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The parent.                                                |

#### [prev](#prev)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:prev() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `prev` function, if present.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `nil`                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:update() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Updates the Tangent panel with the current value.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `true` if the update was sent.                                                |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Action.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `xml` for the Action.                                                |

