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
| **Parameters**                                       | <ul><li>* id        - The ID number of the binding.</li><li>* name      - The name of the binding.</li></ul> |
| **Returns**                                          | <ul><li>* the new `binding`.</li></ul>          |

### Methods

#### [member](#member)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding:member(parameter) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a `parameter` as a member of the Binding group. The order is significant                                                                                         |
| **Parameters**                                       | <ul><li>* param     - The `parameter` to add to the binding.</li></ul> |
| **Returns**                                          | <ul><li>* The `binding` instance.</li></ul>          |

#### [members](#members)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding:members(...) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the list of parameters to this binding.                                                                                         |
| **Parameters**                                       | <ul><li>* ...   - the list of parameters to bind.</li></ul> |
| **Returns**                                          | <ul><li>* The `binding` instance.</li></ul>          |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Binding.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The `xml` for the Binding.</li></ul>          |

