# [docs](index.md) » plugins.core.tangent.manager.action
---

Represents a Tangent Action

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [controls](#controls)
 * [is](#is)
 * [onPress](#onpress)
 * [onRelease](#onrelease)
 * [parent](#parent)
 * [xml](#xml)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action.new(id[, name]) -> action` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Action` instance.                                                                                         |
| **Parameters**                                       | * id        - The ID number of the action.* name      - The name of the action.                                       |
| **Returns**                                          | * the new `action`.                                                |

### Methods

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:controls()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `controls` the action belongs to.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `controls`, or `nil` if not specified.                                                |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action.is() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is an object an action?                                                                                         |
| **Parameters**                                       | * otherThing - Object to test.                                       |
| **Returns**                                          | * `true` if the object is an action otherwise `false`.                                                |

#### [onPress](#onpress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:onPress(pressFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'action on' request.                                                                                         |
| **Parameters**                                       | * pressFn     - The function to call when the Tangent requests the action on.                                       |
| **Returns**                                          | * The `parameter` instance.                                                |

#### [onRelease](#onrelease)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:onRelease(releaseFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'action off' request.                                                                                         |
| **Parameters**                                       | * releaseFn     - The function to call when the Tangent requests the action off.                                       |
| **Returns**                                          | * The `parameter` instance.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `group` or `controls` that contains this action.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The action's parent.                                                |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Action.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `xml` for the Action.                                                |

