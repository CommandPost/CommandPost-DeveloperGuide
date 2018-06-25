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
| **Parameters**                                       | <ul><br /><li>other     - The other object to test.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if it is a <code>parameter</code>, <code>false</code> if not.</li><br /></ul>                                           |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter.new(id[, name[, parent]) -> parameter` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Parameter` instance.                                                                                         |
| **Parameters**                                       | <ul><br /><li>id        - The ID number of the parameter. * name      - The name of the parameter. * parent    - The parent of the parameter.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the new <code>parameter</code>.</li><br /></ul>                                           |

### Methods

#### [change](#change)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:change(amount) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `change` function if present, and returns the new result. If                                                                                         |
| **Parameters**                                       | <ul><br /><li>amount    - The amount to change the parameter.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The current value, or <code>nil</code> if it can't be accessed.</li><br /></ul>                                           |

#### [controls](#controls)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:controls()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `controls` the parameter belongs to.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>controls</code>, or <code>nil</code> if not specified.</li><br /></ul>                                           |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:get() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `get` function if present, and returns the result. If                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The current value, or <code>nil</code> if it can't be accessed.</li><br /></ul>                                           |

#### [maxValue](#maxvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:maxValue([value]) -> number | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets or sets the maximum value for the parameter.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value     - The new value.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>If <code>value</code> is <code>nil</code>, the current value is returned, otherwise returns <code>self</code>.</li><br /></ul>                                           |

#### [minValue](#minvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:minValue([value]) -> number | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets or sets the minimum value for the parameter.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value     - The new value.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>If <code>value</code> is <code>nil</code>, the current value is returned, otherwise returns <code>self</code>.</li><br /></ul>                                           |

#### [onChange](#onchange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:onChange(changeFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter change' request.                                                                                         |
| **Parameters**                                       | <ul><br /><li>getFn     - The function to call when the Tangent requests the parameter change.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>parameter</code> instance.</li><br /></ul>                                           |

#### [onGet](#onget)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:onGet(getFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter value' request.                                                                                         |
| **Parameters**                                       | <ul><br /><li>getFn     - The function to call when the Tangent requests the parameter value.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>parameter</code> instance.</li><br /></ul>                                           |

#### [onReset](#onreset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:onReset(resetFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter reset' request.                                                                                         |
| **Parameters**                                       | <ul><br /><li>resetFn     - The function to call when the Tangent requests the parameter reset.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>parameter</code> instance.</li><br /></ul>                                           |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:parent() -> group | controls` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `group` or `controls` that contains this parameter.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The parent.</li><br /></ul>                                           |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:press() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `press` function, if present.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>nil</code></li><br /></ul>                                           |

#### [release](#release)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:release() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `release` function, if present.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>nil</code></li><br /></ul>                                           |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:reset() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the `reset` function if present. Returns the current value of the parameter after reset.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The current value, or <code>nil</code> if it can't be accessed.</li><br /></ul>                                           |

#### [stepSize](#stepsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:stepSize([value]) -> number | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets or sets the step size for the parameter.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value     - The new value.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>If <code>value</code> is <code>nil</code>, the current value is returned, otherwise returns <code>self</code>.</li><br /></ul>                                           |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `xml` configuration for the Parameter.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>xml</code> for the Parameter.</li><br /></ul>                                           |

