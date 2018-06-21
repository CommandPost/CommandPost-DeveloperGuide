# [docs](index.md) » plugins.core.tangent.manager.binding
---

Represents a Tangent Binding

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [member](#member)
 * [members](#members)
 * [xml](#xml)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding.new(id[, name]) -> binding` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Binding` instance.                                                                                         |
| **Parameters**                                       | * id        - The ID number of the binding.* name      - The name of the binding.                                       |
| **Returns**                                          | * the new `binding`.                                                |

### Methods

#### [member](#member)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding:member(parameter) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a `parameter` as a member of the Binding group. The order is significant                                                                                         |
| **Parameters**                                       | * param     - The `parameter` to add to the binding.                                       |
| **Returns**                                          | * The `binding` instance.                                                |

#### [members](#members)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding:members(...) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the list of parameters to this binding.                                                                                         |
| **Parameters**                                       | * ...   - the list of parameters to bind.                                       |
| **Returns**                                          | * The `binding` instance.                                                |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Binding.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `xml` for the Binding.                                                |

