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

### Methods

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named:name(value) -> string | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the full name. |
| **Parameters**                                       | <ul><li>value - The new name value.</li></ul> |
| **Returns**                                          | <ul><li><code>self</code></li></ul> |

#### [nameX](#namex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.named:nameX(value) -> string | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the name `X`, where `X` is a number as defined when the `named` was creted. |
| **Parameters**                                       | <ul><li>value - The new name value.</li></ul> |
| **Returns**                                          | <ul><li>The current value, or <code>self</code> if a new value was provided.</li></ul> |

