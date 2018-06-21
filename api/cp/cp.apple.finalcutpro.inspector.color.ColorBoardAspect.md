# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorBoardAspect
---

Represents a particular aspect of the color board (Color/Saturation/Exposure).

## API Overview
* Constants - Useful values which cannot be changed
 * [ids](#ids)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [hasAngle](#hasangle)
 * [highlights](#highlights)
 * [id](#id)
 * [index](#index)
 * [isShowing](#isshowing)
 * [master](#master)
 * [midtones](#midtones)
 * [parent](#parent)
 * [reset](#reset)
 * [selected](#selected)
 * [shadows](#shadows)
 * [show](#show)
 * [UI](#ui)

## API Documentation

### Constants

#### [ids](#ids)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect.ids -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the list of aspect IDs ("color", "saturation", "exposure").                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect.new(parent, index[, hasAngle]) -> ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `ColorBoardAspect` object.                                                                                         |
| **Parameters**                                       |  * parent - The parent object. * index - The Color Board Aspect Index. * hasAngle - If `true`, the aspect has an `angle` parameter. Defaults to `false`                                       |
| **Returns**                                          |  * A new `ColorBoardAspect object.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the App instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [hasAngle](#hasangle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:hasAngle() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the aspect has an `angle` property.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `true` if it has an `angle` propery.                                                |

#### [highlights](#highlights)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:highlights() -> ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Highlights ColorPuck object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Highlights ColorPuck object.                                                |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Color Board Aspect ID.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The ID as string.                                                |

#### [index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:index() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Color Board Aspect index.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A number.                                                |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets whether or not the Color Board Aspect is showing.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if showing or `false` if not.                                                |

#### [master](#master)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:master() -> ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Master ColorPuck object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Master ColorPuck object.                                                |

#### [midtones](#midtones)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:midtones() -> ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Midtones ColorPuck object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Midtones ColorPuck object.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:parent() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object.                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:reset() -> cp.apple.finalcutpro.inspector.color.ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resets the Color Board Aspect.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.inspector.color.ColorBoardAspect` object for method chaining.                                                |

#### [selected](#selected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:selected() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Color Board Aspect selected?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if selected otherwise `false`.                                                |

#### [shadows](#shadows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:shadows() -> ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Shadows ColorPuck object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Shadows ColorPuck object.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:show() -> cp.apple.finalcutpro.inspector.color.ColorBoardAspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Color Board Aspect                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.inspector.color.ColorBoardAspect` object for method chaining.                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorBoardAspect:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Color Board Aspect Accessibility Object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An `axuielementObject` or `nil`                                                |

