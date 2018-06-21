# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorPuck
---

Color Puck Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_ANGLES](#default_angles)
 * [ELASTICITY](#elasticity)
 * [NATURAL_LENGTH](#natural_length)
 * [RANGE](#range)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [skimming](#skimming)
* Methods - API calls which can only be made on an object returned by a constructor
 * [accumulate](#accumulate)
 * [app](#app)
 * [cleanup](#cleanup)
 * [colorMarker](#colormarker)
 * [contentUI](#contentui)
 * [drawMarker](#drawmarker)
 * [getArc](#getarc)
 * [getBrightness](#getbrightness)
 * [hasAngle](#hasangle)
 * [index](#index)
 * [isShowing](#isshowing)
 * [loop](#loop)
 * [parent](#parent)
 * [reset](#reset)
 * [select](#select)
 * [shiftAngle](#shiftangle)
 * [shiftPercent](#shiftpercent)
 * [show](#show)
 * [start](#start)
 * [stop](#stop)
 * [UI](#ui)

## API Documentation

### Constants

#### [DEFAULT_ANGLES](#default_angles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.DEFAULT_ANGLES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The table of default angles for the various pucks (1-4).                                                                                         |

#### [ELASTICITY](#elasticity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.ELASTICITY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Elasticity as number.                                                                                         |

#### [NATURAL_LENGTH](#natural_length)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.NATURAL_LENGTH -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Natural Length as number.                                                                                         |

#### [RANGE](#range)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.RANGE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of puck ranges.                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.new(parent, puckNumber, labelKeys, hasAngle) -> ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `ColorPuck` object                                                                                         |
| **Parameters**                                       |  * `parent`     - The parent * `puckNumber` - The puck number * `labelKeys`  - Label Keys * `hasAngle`   - If `true`, the puck has an `angle` parameter.                                       |
| **Returns**                                          |  * A ColorInspector object                                                |

### Fields

#### [skimming](#skimming)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.skimming <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The Skimming Preferences value.                                                                                         |

### Methods

#### [accumulate](#accumulate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:accumulate() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Accumulate's the Shift Values.                                                                                         |
| **Parameters**                                       | * `xShift` - `x` value as number* `yShift` - `y` value as number                                       |
| **Returns**                                          | * `x` - Accumulated `x` value as number* `y` - Accumulated `y` value as number                                                |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the App instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [cleanup](#cleanup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:cleanup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Cleans up the Color Puck drawings.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * None                                                |

#### [colorMarker](#colormarker)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:colorMarker(pct, angle) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Draws a Color Marker.                                                                                         |
| **Parameters**                                       |  * pct - Percentage                                       |
| **Returns**                                          |  * None                                                |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:contentUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Content Accessibility Object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An `axuielementObject` or `nil`                                                |

#### [drawMarker](#drawmarker)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:drawMarker() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Draws a marker.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [getArc](#getarc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:getArc() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the arc value.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The arc value as number.                                                |

#### [getBrightness](#getbrightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:getBrightness() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the brightness value.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The brightness value as number.                                                |

#### [hasAngle](#hasangle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:hasAngle() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Indicates if the puck has an `angle` parameter. The `angle` `cp.prop` will always                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `true` if the puck has an `angle`.                                                |

#### [index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:index() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the puck number (1 through 4).                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The puck number.                                                |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets whether or not the Color Puck is showing.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if showing or `false` if not.                                                |

#### [loop](#loop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:loop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loops the Color Puck function.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:parent() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object.                                                |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:reset() -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resets the puck to its default settings.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `ColorPuck` instance.                                                |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:select() -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects this puck.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `ColorPuck` instance.                                                |

#### [shiftAngle](#shiftangle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:shiftAngle(amount) -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shifts the angle value by the provide amount.                                                                                         |
| **Parameters**                                       | * amount - The amount to shift the angle value.                                       |
| **Returns**                                          | * The `ColorPuck` instance.                                                |

#### [shiftPercent](#shiftpercent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:shiftPercent(amount) -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shifts the percent value by the provide amount.                                                                                         |
| **Parameters**                                       |  * `amount` - The amount to shift the percent value.                                       |
| **Returns**                                          |  * The updated value.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:show() -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Color Puck                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.inspector.color.ColorPuck` object for method chaining.                                                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:start() -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts a Color Puck.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `ColorPuck` instance.                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops a Color Puck.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * None                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Color Puck Accessibility Object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An `axuielementObject` or `nil`                                                |

