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
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator.new(parent, finderFn, minValue, maxValue, toAXValueFn, fromAXValueFn) -> ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new ValueIndicator.                                                                                         |
| **Parameters**                                       |  * `parent`         - The parent table. * `finderFn`       - The function which returns the `axuielement`. * `minValue`       - The minimum value allowed for the value. * `maxValue`       - The maximum value allowed for the value. * `toAXValueFn`    - The function which will convert the user value to the actual AXValue. * `fromAXValueFn`  - The function which will convert the current AXValue to a user value.                                       |
| **Returns**                                          |  * New `ValueIndicator` instance.                                                |

### Methods

#### [decrement](#decrement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:decrement() -> cp.apple.finalcutpro.inspector.color.ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Decrements the value indicator.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.inspector.color.ValueIndicator` object.                                                |

#### [increment](#increment)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:increment() -> cp.apple.finalcutpro.inspector.color.ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Increments the value indicator.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.inspector.color.ValueIndicator` object.                                                |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the value indicator enabled?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if enabled otherwise `false`.                                                |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Value Indicator currently showing?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if showing, otherwise `false`                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a layout.                                                                                         |
| **Parameters**                                       |  * `layout` - The layout table you want to load.                                       |
| **Returns**                                          |  * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Value Indicators parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the layout.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the layout.                                                |

#### [shiftValue](#shiftvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:shiftValue(value) -> cp.apple.finalcutpro.inspector.color.ValueIndicator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shifts the Value Indicator value.                                                                                         |
| **Parameters**                                       |  * `value` - The amount to shift the value indicator by as a number.                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.inspector.color.ValueIndicator` object.                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ValueIndicator:UI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `hs._asm.axuielement` object or `nil`.                                                |

