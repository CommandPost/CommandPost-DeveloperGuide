# [docs](index.md) » plugins.core.tangent.manager.parameter
---

Represents a Tangent Parameter

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [change](#change)
 * [controls](#controls)
 * [get](#get)
 * [maxValue](#maxvalue)
 * [minValue](#minvalue)
 * [onChange](#onchange)
 * [onGet](#onget)
 * [onReset](#onreset)
 * [parent](#parent)
 * [press](#press)
 * [release](#release)
 * [reset](#reset)
 * [stepSize](#stepsize)
 * [xml](#xml)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter.is(other) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `other` is a `parameter` instance.                                                                                         |
| **Parameters**                                       |  * other     - The other object to test.                                       |
| **Returns**                                          |  * `true` if it is a `parameter`, `false` if not.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter.new(id[, name[, parent]) -> parameter` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Parameter` instance.                                                                                         |
| **Parameters**                                       |  * id        - The ID number of the parameter. * name      - The name of the parameter. * parent    - The parent of the parameter.                                       |
| **Returns**                                          |  * the new `parameter`.                                                |

### Methods

#### [change](#change)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:change(amount) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `change` function if present, and returns the new result. If                                                                                         |
| **Parameters**                                       |  * amount    - The amount to change the parameter.                                       |
| **Returns**                                          |  * The current value, or `nil` if it can't be accessed.                                                |

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:controls()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `controls` the parameter belongs to.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `controls`, or `nil` if not specified.                                                |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:get() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `get` function if present, and returns the result. If                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The current value, or `nil` if it can't be accessed.                                                |

#### [maxValue](#maxvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:maxValue([value]) -> number | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets or sets the maximum value for the parameter.                                                                                         |
| **Parameters**                                       |  * value     - The new value.                                       |
| **Returns**                                          |  * If `value` is `nil`, the current value is returned, otherwise returns `self`.                                                |

#### [minValue](#minvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:minValue([value]) -> number | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets or sets the minimum value for the parameter.                                                                                         |
| **Parameters**                                       |  * value     - The new value.                                       |
| **Returns**                                          |  * If `value` is `nil`, the current value is returned, otherwise returns `self`.                                                |

#### [onChange](#onchange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:onChange(changeFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter change' request.                                                                                         |
| **Parameters**                                       |  * getFn     - The function to call when the Tangent requests the parameter change.                                       |
| **Returns**                                          |  * The `parameter` instance.                                                |

#### [onGet](#onget)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:onGet(getFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter value' request.                                                                                         |
| **Parameters**                                       |  * getFn     - The function to call when the Tangent requests the parameter value.                                       |
| **Returns**                                          |  * The `parameter` instance.                                                |

#### [onReset](#onreset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:onReset(resetFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter reset' request.                                                                                         |
| **Parameters**                                       |  * resetFn     - The function to call when the Tangent requests the parameter reset.                                       |
| **Returns**                                          |  * The `parameter` instance.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `group` or `controls` that contains this parameter.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent.                                                |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:press() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `press` function, if present.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `nil`                                                |

#### [release](#release)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:release() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `release` function, if present.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `nil`                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:reset() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `reset` function if present. Returns the current value of the parameter after reset.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The current value, or `nil` if it can't be accessed.                                                |

#### [stepSize](#stepsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:stepSize([value]) -> number | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets or sets the step size for the parameter.                                                                                         |
| **Parameters**                                       |  * value     - The new value.                                       |
| **Returns**                                          |  * If `value` is `nil`, the current value is returned, otherwise returns `self`.                                                |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Parameter.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `xml` for the Parameter.                                                |

