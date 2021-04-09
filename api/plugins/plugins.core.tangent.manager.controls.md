# [docs](index.md) » plugins.core.tangent.manager.controls
---

Represents a Tangent Group

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [controls](#controls)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [active](#active)
 * [enabled](#enabled)
* Methods - API calls which can only be made on an object returned by a constructor
 * [action](#action)
 * [controls](#controls)
 * [findByID](#findbyid)
 * [group](#group)
 * [menu](#menu)
 * [parameter](#parameter)
 * [parent](#parent)
 * [register](#register)
 * [tangent](#tangent)
 * [unregister](#unregister)
 * [xml](#xml)

## API Documentation

### Constructors

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls(id, name)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Group` instance. |
| **Parameters**                                       | <ul><li>name      - The name of the controls.</li></ul> |

### Fields

#### [active](#active)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls.active <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the controls are active. They will be active if `enabled` is `true`. |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the controls are enabled. |

### Methods

#### [action](#action)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:action(id[, name]) -> action` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds an `action` to this controls. |
| **Returns**                                          | <ul><li>The new <code>action</code></li></ul> |

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:controls() -> controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns this `controls` instance. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `controls instance.</li></ul> |

#### [findByID](#findbyid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:findByID(id) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds a control (Action/Parameter/Mode) by its unique ID. |
| **Parameters**                                       | <ul><li>id        - the ID to search by</li></ul> |
| **Returns**                                          | <ul><li>The control, or <code>nil</code> if not found.</li></ul> |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:group(name) -> group` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a subgroup to this group. |
| **Returns**                                          | <ul><li>The new <code>group</code></li></ul> |

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:menu(id[, name]) -> menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds an `menu` to this controls. |
| **Returns**                                          | <ul><li>The new <code>menu</code></li></ul> |

#### [parameter](#parameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:parameter(id[, name]) -> parameter` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds an `parameter` to this controls. |
| **Returns**                                          | <ul><li>The new <code>parameter</code></li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:parent() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Always returns `nil`, sinces `controls` have no parent. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>nil</code>.</li></ul> |

#### [register](#register)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:register(control) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Registers a control (Action/Parameter/Menu) with it's ID |
| **Parameters**                                       | <ul><li>control       - The Action/Parameter/Menu to register</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

#### [tangent](#tangent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:tangent() -> hs.tangent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The `hs.tangent` connection. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.tangent</code>.</li></ul> |

#### [unregister](#unregister)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:unregister(control) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Unregisters a control (Action/Parameter/Menu) with it's ID |
| **Parameters**                                       | <ul><li>control       - The Action/Parameter/Menu to unregister</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.controls:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `xml` configuration for the Group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>xml</code> for the Group.</li></ul> |

