# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorWell
---

Represents a single Color Well in the Color Wheels Inspector.

## API Overview
* Constants - Useful values which cannot be changed
 * [KEY_PRESS](#key_press)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [nudge](#nudge)
 * [parent](#parent)
 * [reset](#reset)
 * [select](#select)

## API Documentation

### Constants

#### [KEY_PRESS](#key_press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.KEY_PRESS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | This can be used with `nudge` to shift by the same distance                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the specified element is a Color Well.                                                                                         |
| **Parameters**                                       | * element   - The element to check                                       |
| **Returns**                                          | * `true` if the element is a Color Well.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.new(parent, finderFn) -> ColorWell` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `ColorWell` instance, with the specified parent and finder function.                                                                                         |
| **Parameters**                                       | * parent - The parent object* finderFn - Returns the `axuielement` that represents the color well.                                       |
| **Returns**                                          | * A new `ColorWell` instance.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:app() -> cp.apple.finalcutpro` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Final Cut Pro object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Final Cut Pro object.                                                |

#### [nudge](#nudge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:nudge(right, up) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Nudges the `colorPosition` by `right`/`up` values. Negative `right` values shift left,                                                                                         |
| **Parameters**                                       |  * `right` - The number of steps to shift right. May be negative to shift left. * `up` - The number of pixels to shift down. May be negative to shift down.                                       |
| **Returns**                                          |  * The `ColorWell` instance.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Color Well parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:reset() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resets the color wheel.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `ColorWell` instance.                                                |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:select() -> cp.apple.finalcutpro.inspector.color.ColorWell` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects this color well.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `ColorWell` instance.                                                |

