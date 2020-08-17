# [docs](index.md) » plugins.core.tangent.manager.action
---

Represents a Tangent Action

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [action](#action)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [active](#active)
 * [localActive](#localactive)
* Methods - API calls which can only be made on an object returned by a constructor
 * [is](#is)
 * [onPress](#onpress)
 * [onRelease](#onrelease)
 * [xml](#xml)

## API Documentation

### Constructors

#### [action](#action)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action(id[, name[, parent[, localActive]]]) -> action` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Action` instance. |
| **Parameters**                                       | <ul><li>id        - The ID number of the action.</li><li>name      - The name of the action.</li><li>parent    - The parent group. (optional)</li><li>localActive - If set to <code>true</code>, the parent's <code>active</code> state will be ignored when determining if this action is active. Defaults to <code>false</code>.</li></ul> |
| **Returns**                                          | <ul><li>the new <code>action</code>.</li></ul> |

### Fields

#### [active](#active)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action.active <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the action is active. It will only be active if |

#### [localActive](#localactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action.localActive <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the action should ignore the parent's `enabled` state when determining if the action is active. |

### Methods

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action.is() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Is an object an action? |
| **Parameters**                                       | <ul><li>otherThing - Object to test.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the object is an action otherwise <code>false</code>.</li></ul> |

#### [onPress](#onpress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:onPress(pressFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'action on' request. |
| **Parameters**                                       | <ul><li>pressFn     - The function to call when the Tangent requests the action on.</li></ul> |
| **Returns**                                          | <ul><li>The <code>parameter</code> instance.</li></ul> |

#### [onRelease](#onrelease)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:onRelease(releaseFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'action off' request. |
| **Parameters**                                       | <ul><li>releaseFn     - The function to call when the Tangent requests the action off.</li></ul> |
| **Returns**                                          | <ul><li>The <code>parameter</code> instance.</li></ul> |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `xml` configuration for the Action. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>xml</code> for the Action.</li></ul> |

