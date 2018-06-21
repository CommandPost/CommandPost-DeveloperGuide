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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* id        - The ID number of the action.</li><li markdown="1">* name      - The name of the action.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* the new `action`.</li></ul>          |

### Methods

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:controls()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `controls` the action belongs to.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `controls`, or `nil` if not specified.</li></ul>          |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action.is() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is an object an action?                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* otherThing - Object to test.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* `true` if the object is an action otherwise `false`.</li></ul>          |

#### [onPress](#onpress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:onPress(pressFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'action on' request.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* pressFn     - The function to call when the Tangent requests the action on.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `parameter` instance.</li></ul>          |

#### [onRelease](#onrelease)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:onRelease(releaseFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'action off' request.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* releaseFn     - The function to call when the Tangent requests the action off.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `parameter` instance.</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `group` or `controls` that contains this action.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The action's parent.</li></ul>          |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Action.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `xml` for the Action.</li></ul>          |

