# [docs](index.md) » plugins.core.tangent.manager.named
---

Provides common functions for 'named' Tangent nodes

Tables with `named` in it's metatable chain will have `name` methods added
as described below.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
 * [xml](#xml)
* Constructors - API calls which return an object, typically one that offers API methods
 * [named](#named)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [active](#active)
 * [enabled](#enabled)
* Methods - API calls which can only be made on an object returned by a constructor
 * [controls](#controls)
 * [name](#name)
 * [nameX](#namex)
 * [parent](#parent)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Check if the `thing` is a `named` table. |
| **Parameters**                                       | <ul><li>thing     - The thing to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it is `named.</li></ul> |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named.xml(thing) -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the `xml` configuration for the Action. |
| **Parameters**                                       | <ul><li>thing     - The thing to retrieve the names from.</li></ul> |
| **Returns**                                          | <ul><li>The <code>xml</code> for the Action.</li></ul> |

### Constructors

#### [named](#named)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named(id, name[, parent]) -> named` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `named` instance, with the specified base name. |
| **Parameters**                                       | <ul><li>id - the unique ID for the value.</li><li>name - The base name of the</li></ul> |

### Fields

#### [active](#active)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named.active <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the parameter is active. It will only be active if |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the parameter is enabled. |

### Methods

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named:controls()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `controls` the parameter belongs to. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>controls</code>, or <code>nil</code> if not specified.</li></ul> |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named:name(value) -> string | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the full name. |
| **Parameters**                                       | <ul><li>value - The new name value.</li></ul> |
| **Returns**                                          | <ul><li>The current value, or <code>self</code> if a new value was provided.</li></ul> |

#### [nameX](#namex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named:nameX(value) -> string | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the name `X`, where `X` is a number as defined when the `named` was created. |
| **Parameters**                                       | <ul><li>value - The new name value.</li></ul> |
| **Returns**                                          | <ul><li>The current value, or <code>self</code> if a new value was provided.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `group` or `controls` that contains this parameter. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent.</li></ul> |

