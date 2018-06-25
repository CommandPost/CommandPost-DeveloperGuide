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
| **Parameters**                                       | <ul><br /><li>other     - The other object to test.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if it is a <code>menu</code>, <code>false</code> if not.</li><br /></ul>                                           |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu.new(id[, name[, parent]]) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Action` instance.                                                                                         |
| **Parameters**                                       | <ul><br /><li>id        - The ID number of the menu.<em> name      - The name of the menu.</em> parent    - The parent of the menu.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the new <code>menu</code>.</li><br /></ul>                                           |

### Methods

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:controls()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `controls` the menu belongs to.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>controls</code>, or <code>nil</code> if not specified.</li><br /></ul>                                           |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:get() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `get` function, if present, returning the string value for the current menu.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>nil</code></li><br /></ul>                                           |

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:next() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `next` function, if present.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>nil</code></li><br /></ul>                                           |

#### [onGet](#onget)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onGet(getFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a `menu string request`.                                                                                         |
| **Parameters**                                       | <ul><br /><li>getFn     - The function to call when the Tangent requests the <code>menu string</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>parameter</code> instance.</li><br /></ul>                                           |

#### [onNext](#onnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onNext(nextFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a `menu change +1` request.                                                                                         |
| **Parameters**                                       | <ul><br /><li>nextFn     - The function to call when the Tangent requests the <code>menu change +1</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>parameter</code> instance.</li><br /></ul>                                           |

#### [onPrev](#onprev)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:onPrev(prevFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a `menu change -1` request.                                                                                         |
| **Parameters**                                       | <ul><br /><li>prevFn     - The function to call when the Tangent requests the <code>menu change -1</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>parameter</code> instance.</li><br /></ul>                                           |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `group` or `controls` that contains this menu.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The parent.</li><br /></ul>                                           |

#### [prev](#prev)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:prev() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `prev` function, if present.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>nil</code></li><br /></ul>                                           |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:update() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Updates the Tangent panel with the current value.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the update was sent.</li><br /></ul>                                           |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.menu:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Action.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>xml</code> for the Action.</li><br /></ul>                                           |

