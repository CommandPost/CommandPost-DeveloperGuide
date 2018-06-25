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
| **Parameters**                                       | <ul><br /><li>id        - The ID number of the binding.* name      - The name of the binding.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the new <code>binding</code>.</li><br /></ul>                                           |

### Methods

#### [member](#member)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding:member(parameter) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a `parameter` as a member of the Binding group. The order is significant                                                                                         |
| **Parameters**                                       | <ul><br /><li>param     - The <code>parameter</code> to add to the binding.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>binding</code> instance.</li><br /></ul>                                           |

#### [members](#members)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding:members(...) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds the list of parameters to this binding.                                                                                         |
| **Parameters**                                       | <ul><br /><li>...   - the list of parameters to bind.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>binding</code> instance.</li><br /></ul>                                           |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.binding:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Binding.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>xml</code> for the Binding.</li><br /></ul>                                           |

