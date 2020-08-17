# [docs](index.md) » plugins.core.tangent.manager.parameter
---

Represents a Tangent Parameter control.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
 * [update](#update)
* Constructors - API calls which return an object, typically one that offers API methods
 * [parameter](#parameter)
* Methods - API calls which can only be made on an object returned by a constructor
 * [change](#change)
 * [get](#get)
 * [maxValue](#maxvalue)
 * [minValue](#minvalue)
 * [onChange](#onchange)
 * [onGet](#onget)
 * [onReset](#onreset)
 * [press](#press)
 * [release](#release)
 * [reset](#reset)
 * [stepSize](#stepsize)
 * [xml](#xml)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `parameter` instance. |
| **Parameters**                                       | <ul><li>thing     - The other object to test.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it is a <code>parameter</code>, <code>false</code> if not.</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:update()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the Tangent with the current value of the parameter. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing.</li></ul> |

### Constructors

#### [parameter](#parameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter(id[, name[, parent]) -> parameter` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Parameter` instance. |
| **Parameters**                                       | <ul><li>id        - The ID number of the parameter.</li><li>name      - The name of the parameter.</li><li>parent    - The parent of the parameter.</li></ul> |
| **Returns**                                          | <ul><li>the new <code>parameter</code>.</li></ul> |

### Methods

#### [change](#change)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:change(amount) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the `change` function if present, and returns the new result. If |
| **Parameters**                                       | <ul><li>amount    - The amount to change the parameter.</li></ul> |
| **Returns**                                          | <ul><li>The current value, or <code>nil</code> if it can't be accessed.</li></ul> |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:get() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the `get` function if present, and returns the result. If |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The current value, or <code>nil</code> if it can't be accessed.</li></ul> |

#### [maxValue](#maxvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:maxValue([value]) -> number | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the maximum value for the parameter. |
| **Parameters**                                       | <ul><li>value     - The new value.</li></ul> |
| **Returns**                                          | <ul><li>If <code>value</code> is <code>nil</code>, the current value is returned, otherwise returns <code>self</code>.</li></ul> |

#### [minValue](#minvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:minValue([value]) -> number | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the minimum value for the parameter. |
| **Parameters**                                       | <ul><li>value     - The new value.</li></ul> |
| **Returns**                                          | <ul><li>If <code>value</code> is <code>nil</code>, the current value is returned, otherwise returns <code>self</code>.</li></ul> |

#### [onChange](#onchange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:onChange(changeFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter change' request. |
| **Parameters**                                       | <ul><li>getFn     - The function to call when the Tangent requests the parameter change.</li></ul> |
| **Returns**                                          | <ul><li>The <code>parameter</code> instance.</li></ul> |

#### [onGet](#onget)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:onGet(getFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter value' request. |
| **Parameters**                                       | <ul><li>getFn     - The function to call when the Tangent requests the parameter value.</li></ul> |
| **Returns**                                          | <ul><li>The <code>parameter</code> instance.</li></ul> |

#### [onReset](#onreset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:onReset(resetFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the function that will be called when the Tangent sends a 'parameter reset' request. |
| **Parameters**                                       | <ul><li>resetFn     - The function to call when the Tangent requests the parameter reset.</li></ul> |
| **Returns**                                          | <ul><li>The <code>parameter</code> instance.</li></ul> |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:press() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the `press` function, if present. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>nil</code></li></ul> |

#### [release](#release)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:release() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the `release` function, if present. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>nil</code></li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:reset() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Executes the `reset` function if present. Returns the current value of the parameter after reset. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The current value, or <code>nil</code> if it can't be accessed.</li></ul> |

#### [stepSize](#stepsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:stepSize([value]) -> number | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the step size for the parameter. |
| **Parameters**                                       | <ul><li>value     - The new value.</li></ul> |
| **Returns**                                          | <ul><li>If <code>value</code> is <code>nil</code>, the current value is returned, otherwise returns <code>self</code>.</li></ul> |

#### [xml](#xml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tangent.manager.parameter:xml() -> cp.web.xml` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `xml` configuration for the Parameter. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>xml</code> for the Parameter.</li></ul> |

