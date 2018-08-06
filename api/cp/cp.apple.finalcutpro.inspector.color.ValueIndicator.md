# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ValueIndicator
---

ValueIndicator Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [decrement](#decrement)
 * [increment](#increment)
 * [isEnabled](#isenabled)
 * [isShowing](#isshowing)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [saveLayout](#savelayout)
 * [shiftValue](#shiftvalue)
 * [UI](#ui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator.new(parent, finderFn, minValue, maxValue, toAXValueFn, fromAXValueFn) -> ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new ValueIndicator. |
| **Parameters**                                       | <ul><li><code>parent</code>         - The parent table.</li><li><code>finderFn</code>       - The function which returns the <code>axuielement</code>.</li><li><code>minValue</code>       - The minimum value allowed for the value.</li><li><code>maxValue</code>       - The maximum value allowed for the value.</li><li><code>toAXValueFn</code>    - The function which will convert the user value to the actual AXValue.</li><li><code>fromAXValueFn</code>  - The function which will convert the current AXValue to a user value.</li></ul> |
| **Returns**                                          | <ul><li>New <code>ValueIndicator</code> instance.</li></ul> |

### Methods

#### [decrement](#decrement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:decrement() -> cp.apple.finalcutpro.inspector.color.ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Decrements the value indicator. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.inspector.color.ValueIndicator</code> object.</li></ul> |

#### [increment](#increment)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:increment() -> cp.apple.finalcutpro.inspector.color.ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Increments the value indicator. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.inspector.color.ValueIndicator</code> object.</li></ul> |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Is the value indicator enabled? |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if enabled otherwise <code>false</code>.</li></ul> |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Is the Value Indicator currently showing? |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if showing, otherwise <code>false</code></li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a layout. |
| **Parameters**                                       | <ul><li><code>layout</code> - The layout table you want to load.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Value Indicators parent table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the layout. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the layout.</li></ul> |

#### [shiftValue](#shiftvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:shiftValue(value) -> cp.apple.finalcutpro.inspector.color.ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shifts the Value Indicator value. |
| **Parameters**                                       | <ul><li><code>value</code> - The amount to shift the value indicator by as a number.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.inspector.color.ValueIndicator</code> object.</li></ul> |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:UI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `hs._asm.axuielement` object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs._asm.axuielement</code> object or <code>nil</code>.</li></ul> |

