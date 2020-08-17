# [docs](index.md) » plugins.core.tangent.manager.group
---

Represents a Tangent Group. Groups can also be used to enable/disable multiple
Parameters/Actions/Menus by enabling/disabling the containing group.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [group](#group)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [active](#active)
 * [enabled](#enabled)
 * [localActive](#localactive)
* Methods - API calls which can only be made on an object returned by a constructor
 * [action](#action)
 * [binding](#binding)
 * [controls](#controls)
 * [group](#group)
 * [menu](#menu)
 * [name](#name)
 * [parameter](#parameter)
 * [parent](#parent)
 * [reset](#reset)
 * [xml](#xml)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `group`. |
| **Parameters**                                       | <ul><li>thing    - The thing to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it is a <code>group</code>, <code>false</code> otherwise.</li></ul> |

### Constructors

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group(name[, parent[, localActive]])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Group` instance. |
| **Parameters**                                       | <ul><li>name      - The name of the group.</li><li>parent    - The parent group.</li><li>localActive - If <code>true</code>, this group will ignore the parent's <code>active</code> status when determining its own <code>active</code> status. Defaults to <code>false</code>.</li></ul> |

### Fields

#### [active](#active)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group.active <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the group is active. It will only be active if |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the group is enabled. |

#### [localActive](#localactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group.localActive <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the group should ignore the parent's `enabled` state when determining if the group is active. |

### Methods

#### [action](#action)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:action(id[, name[, localActive]]) -> action` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds an `action` to this group. |
| **Returns**                                          | <ul><li>The new <code>action</code></li></ul> |

#### [binding](#binding)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:binding(id[, name]) -> binding` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds an `binding` to this group. |
| **Returns**                                          | <ul><li>The new <code>binding</code></li></ul> |

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:controls() -> controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Retrieves the `controls` for this group. May be `nil` if the group was created independently. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>controls</code>, or <code>nil</code>.</li></ul> |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:group(name[, localActive]) -> group` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a subgroup to this group. |
| **Returns**                                          | <ul><li>The new <code>group</code></li></ul> |

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:menu(id[, name]) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds an `menu` to this group. |
| **Returns**                                          | <ul><li>The new <code>menu</code></li></ul> |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:name() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `name` given to the group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The name.</li></ul> |

#### [parameter](#parameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:parameter(id[, name]) -> parameter` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds an `parameter` to this group. |
| **Returns**                                          | <ul><li>The new <code>parameter</code></li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the parent of the group, which should be either a `group`, `controls` or `nil`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The group's parents.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:reset() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | This will remove all parameters, actions, menus and bindings from |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>group</code> instance.</li></ul> |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.group:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `xml` configuration for the Group, sorted alphabetically. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>xml</code> for the Group.</li></ul> |

