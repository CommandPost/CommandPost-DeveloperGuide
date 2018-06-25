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
| **Parameters**                                       | <ul><br /><li>id        - The ID number of the action.* name      - The name of the action.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the new <code>action</code>.</li><br /></ul>                                           |

### Methods

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:controls()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `controls` the action belongs to.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>controls</code>, or <code>nil</code> if not specified.</li><br /></ul>                                           |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action.is() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is an object an action?                                                                                         |
| **Parameters**                                       | <ul><br /><li>otherThing - Object to test.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the object is an action otherwise <code>false</code>.</li><br /></ul>                                           |

#### [onPress](#onpress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:onPress(pressFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'action on' request.                                                                                         |
| **Parameters**                                       | <ul><br /><li>pressFn     - The function to call when the Tangent requests the action on.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>parameter</code> instance.</li><br /></ul>                                           |

#### [onRelease](#onrelease)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:onRelease(releaseFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'action off' request.                                                                                         |
| **Parameters**                                       | <ul><br /><li>releaseFn     - The function to call when the Tangent requests the action off.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>parameter</code> instance.</li><br /></ul>                                           |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `group` or `controls` that contains this action.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The action's parent.</li><br /></ul>                                           |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.action:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Action.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>xml</code> for the Action.</li><br /></ul>                                           |

