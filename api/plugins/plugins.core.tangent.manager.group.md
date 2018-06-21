# [docs](index.md) » plugins.core.tangent.manager.group
---

Represents a Tangent Group. Groups can also be used to enable/disable multiple
Parameters/Actions/Menus by enabling/disabling the containing group.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [action](#action)
 * [binding](#binding)
 * [controls](#controls)
 * [group](#group)
 * [menu](#menu)
 * [parameter](#parameter)
 * [parent](#parent)
 * [reset](#reset)
 * [xml](#xml)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group.is(otherThing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `otherThing` is a `group`.                                                                                         |
| **Parameters**                                       |  * otherThing    - The thing to check.                                       |
| **Returns**                                          |  * `true` if it is a `group`, `false` otherwise.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group.new(name, parent, controls)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Group` instance.                                                                                         |
| **Parameters**                                       |  * name      - The name of the group. * parent    - The parent group.                                       |

### Methods

#### [action](#action)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:action(id[, name]) -> action` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an `action` to this group.                                                                                         |
| **Returns**                                          |  * The new `action`                                                |

#### [binding](#binding)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:binding(id[, name]) -> binding` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an `binding` to this group.                                                                                         |
| **Returns**                                          |  * The new `binding`                                                |

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:controls() -> controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Retrieves the `controls` for this group. May be `nil` if the group was created independently.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `controls`, or `nil`.                                                |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:group(name) -> group` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a subgroup to this group.                                                                                         |
| **Returns**                                          |  * The new `group`                                                |

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:menu(id[, name]) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an `menu` to this group.                                                                                         |
| **Returns**                                          |  * The new `menu`                                                |

#### [parameter](#parameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:parameter(id[, name]) -> parameter` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an `parameter` to this group.                                                                                         |
| **Returns**                                          |  * The new `parameter`                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent of the group, which should be either a `group`, `controls` or `nil`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The group's parents.                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:reset() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | This will remove all parameters, actions, menus and bindings from                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `group` instance.                                                |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Group, sorted alphabetically.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `xml` for the Group.                                                |

