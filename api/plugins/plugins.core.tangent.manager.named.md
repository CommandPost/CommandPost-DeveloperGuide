# [docs](index.md) » plugins.core.tangent.manager.named
---

Provides common functions for 'named' Tangent nodes

Tables with `named` in it's metatable chain will have `name` methods added
as described below.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
 * [xml](#xml)
* Methods - API calls which can only be made on an object returned by a constructor
 * [name](#name)
 * [nameX](#namex)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Check if the `thing` is a `named` table.                                                                                         |
| **Parameters**                                       | * thing     - The thing to check.                                       |
| **Returns**                                          | * `true` if it is `named.                                                |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named.xml(thing) -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Action.                                                                                         |
| **Parameters**                                       | * thing     - The thing to retrieve the names from.                                       |
| **Returns**                                          | * The `xml` for the Action.                                                |

### Methods

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named:name(value) -> string | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets or sets the full name.                                                                                         |
| **Parameters**                                       | * value - The new name value.                                       |
| **Returns**                                          | * `self`                                                |

#### [nameX](#namex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named:nameX(value) -> string | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the name `X`, where `X` is a number as defined when the `named` was creted.                                                                                         |
| **Parameters**                                       | * value - The new name value.                                       |
| **Returns**                                          | * The current value, or `self` if a new value was provided.                                                |

