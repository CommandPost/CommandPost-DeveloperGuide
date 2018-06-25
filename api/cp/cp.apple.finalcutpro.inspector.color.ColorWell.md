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
| **Type**                                             | Constant |
| **Description**                                      | This can be used with `nudge` to shift by the same distance |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.matches(element)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the specified element is a Color Well. |
| **Parameters**                                       | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is a Color Well.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell.new(parent, finderFn) -> ColorWell` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ColorWell` instance, with the specified parent and finder function. |
| **Parameters**                                       | <ul><li>parent - The parent object* finderFn - Returns the <code>axuielement</code> that represents the color well.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>ColorWell</code> instance.</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:app() -> cp.apple.finalcutpro` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Final Cut Pro object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Final Cut Pro object.</li></ul> |

#### [nudge](#nudge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:nudge(right, up) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Nudges the `colorPosition` by `right`/`up` values. Negative `right` values shift left, |
| **Parameters**                                       | <ul><li><code>right</code> - The number of steps to shift right. May be negative to shift left. * <code>up</code> - The number of pixels to shift down. May be negative to shift down.</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorWell</code> instance.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Color Well parent table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:reset() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resets the color wheel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorWell</code> instance.</li></ul> |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorWell:select() -> cp.apple.finalcutpro.inspector.color.ColorWell` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects this color well. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorWell</code> instance.</li></ul> |

