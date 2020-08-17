# [docs](index.md) » plugins.core.tangent.manager.menu
---

Represents a Tangent Menu. Menus are controls that have a fixed set of
non-numerical values. This could be as simple as "On" and "Off", or a long
list of options.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [menu](#menu)
* Methods - API calls which can only be made on an object returned by a constructor
 * [get](#get)
 * [next](#next)
 * [onGet](#onget)
 * [onNext](#onnext)
 * [onPrev](#onprev)
 * [onReset](#onreset)
 * [prev](#prev)
 * [reset](#reset)
 * [update](#update)
 * [xml](#xml)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `menu` instance. |
| **Parameters**                                       | <ul><li>thing     - The other object to test.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it is a <code>menu</code>, <code>false</code> if not.</li></ul> |

### Constructors

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu(id[, name[, parent]]) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Action` instance. |
| **Parameters**                                       | <ul><li>id        - The ID number of the menu.</li><li>name      - The name of the menu.</li><li>parent    - The parent of the menu.</li></ul> |
| **Returns**                                          | <ul><li>the new <code>menu</code>.</li></ul> |

### Methods

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:get() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the `get` function, if present, returning the string value for the current menu. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>nil</code></li></ul> |

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:next() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the `next` function, if present. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>nil</code></li></ul> |

#### [onGet](#onget)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onGet(getFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the Tangent sends a `menu string request`. |
| **Parameters**                                       | <ul><li>getFn     - The function to call when the Tangent requests the <code>menu string</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>parameter</code> instance.</li></ul> |

#### [onNext](#onnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onNext(nextFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the Tangent sends a `menu change +1` request. |
| **Parameters**                                       | <ul><li>nextFn     - The function to call when the Tangent requests the <code>menu change +1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>parameter</code> instance.</li></ul> |

#### [onPrev](#onprev)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onPrev(prevFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the Tangent sends a `menu change -1` request. |
| **Parameters**                                       | <ul><li>prevFn     - The function to call when the Tangent requests the <code>menu change -1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>parameter</code> instance.</li></ul> |

#### [onReset](#onreset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onReset(resetFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter reset' request. |
| **Parameters**                                       | <ul><li>resetFn     - The function to call when the Tangent requests the parameter reset.</li></ul> |
| **Returns**                                          | <ul><li>The <code>parameter</code> instance.</li></ul> |

#### [prev](#prev)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:prev() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the `prev` function, if present. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>nil</code></li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:reset() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the `reset` function if present. Returns the current value of the parameter after reset. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The current value, or <code>nil</code> if it can't be accessed.</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:update() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Updates the Tangent panel with the current value. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the update was sent.</li></ul> |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `xml` configuration for the Action. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>xml</code> for the Action.</li></ul> |

