# [docs](index.md) » plugins.core.tangent.manager.controls
---

Represents a Tangent Group

## API Overview
* Constants - Useful values which cannot be changed
 * [controls](#controls)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [action](#action)
 * [controls](#controls)
 * [findByID](#findbyid)
 * [group](#group)
 * [menu](#menu)
 * [parameter](#parameter)
 * [parent](#parent)
 * [register](#register)
 * [unregister](#unregister)
 * [xml](#xml)

## API Documentation

### Constants

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The set of controls currently registered.                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls.new(id, name)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Group` instance.                                                                                         |
| **Parameters**                                       | * name      - The name of the controls.                                       |

### Methods

#### [action](#action)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:action(id[, name]) -> action` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an `action` to this controls.                                                                                         |
| **Returns**                                          | * The new `action`                                                |

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:controls() -> controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns this `controls` instance.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `controls instance.                                                |

#### [findByID](#findbyid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:findByID(id) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds a control (Action/Parameter/Mode) by its unique ID.                                                                                         |
| **Parameters**                                       | * id        - the ID to search by                                       |
| **Returns**                                          | * The control, or `nil` if not found.                                                |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:group(name) -> group` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a subgroup to this group.                                                                                         |
| **Returns**                                          | * The new `group`                                                |

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:menu(id[, name]) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an `menu` to this controls.                                                                                         |
| **Returns**                                          | * The new `menu`                                                |

#### [parameter](#parameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:parameter(id[, name]) -> parameter` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds an `parameter` to this controls.                                                                                         |
| **Returns**                                          | * The new `parameter`                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:parent() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Always returns `nil`, sinces `controls` have no parent.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `nil`.                                                |

#### [register](#register)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:register(control) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers a control (Action/Parameter/Menu) with it's ID                                                                                         |
| **Parameters**                                       | * control       - The Action/Parameter/Menu to register                                       |
| **Returns**                                          | * self                                                |

#### [unregister](#unregister)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:unregister(control) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Unregisters a control (Action/Parameter/Menu) with it's ID                                                                                         |
| **Parameters**                                       | * control       - The Action/Parameter/Menu to unregister                                       |
| **Returns**                                          | * self                                                |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Group.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `xml` for the Group.                                                |

