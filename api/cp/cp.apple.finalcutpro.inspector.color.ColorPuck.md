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
| **Type**                                             | Constant |
| **Description**                                      | The table of default angles for the various pucks (1-4). |

#### [ELASTICITY](#elasticity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.ELASTICITY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Elasticity as number. |

#### [NATURAL_LENGTH](#natural_length)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.NATURAL_LENGTH -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Natural Length as number. |

#### [RANGE](#range)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.RANGE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of puck ranges. |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.new(parent, puckNumber, labelKeys, hasAngle) -> ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ColorPuck` object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent * <code>puckNumber</code> - The puck number * <code>labelKeys</code>  - Label Keys * <code>hasAngle</code>   - If <code>true</code>, the puck has an <code>angle</code> parameter.</li></ul> |
| **Returns**                                          | <ul><li>A ColorInspector object</li></ul> |

### Fields

#### [skimming](#skimming)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck.skimming <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Skimming Preferences value. |

### Methods

#### [accumulate](#accumulate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:accumulate() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Accumulate's the Shift Values. |
| **Parameters**                                       | <ul><li><code>xShift</code> - <code>x</code> value as number* <code>yShift</code> - <code>y</code> value as number</li></ul> |
| **Returns**                                          | <ul><li><code>x</code> - Accumulated <code>x</code> value as number* <code>y</code> - Accumulated <code>y</code> value as number</li></ul> |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the App instance representing Final Cut Pro. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [cleanup](#cleanup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:cleanup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Cleans up the Color Puck drawings. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [colorMarker](#colormarker)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:colorMarker(pct, angle) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Draws a Color Marker. |
| **Parameters**                                       | <ul><li>pct - Percentage</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [contentUI](#contentui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:contentUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Content Accessibility Object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An <code>axuielementObject</code> or <code>nil</code></li></ul> |

#### [drawMarker](#drawmarker)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:drawMarker() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Draws a marker. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getArc](#getarc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:getArc() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the arc value. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The arc value as number.</li></ul> |

#### [getBrightness](#getbrightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:getBrightness() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the brightness value. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The brightness value as number.</li></ul> |

#### [hasAngle](#hasangle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:hasAngle() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates if the puck has an `angle` parameter. The `angle` `cp.prop` will always |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the puck has an <code>angle</code>.</li></ul> |

#### [index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:index() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the puck number (1 through 4). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The puck number.</li></ul> |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets whether or not the Color Puck is showing. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if showing or <code>false</code> if not.</li></ul> |

#### [loop](#loop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:loop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loops the Color Puck function. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:parent() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Parent object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:reset() -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resets the puck to its default settings. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorPuck</code> instance.</li></ul> |

#### [select](#select)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:select() -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects this puck. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorPuck</code> instance.</li></ul> |

#### [shiftAngle](#shiftangle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:shiftAngle(amount) -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shifts the angle value by the provide amount. |
| **Parameters**                                       | <ul><li>amount - The amount to shift the angle value.</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorPuck</code> instance.</li></ul> |

#### [shiftPercent](#shiftpercent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:shiftPercent(amount) -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shifts the percent value by the provide amount. |
| **Parameters**                                       | <ul><li><code>amount</code> - The amount to shift the percent value.</li></ul> |
| **Returns**                                          | <ul><li>The updated value.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:show() -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Color Puck |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.inspector.color.ColorPuck</code> object for method chaining.</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:start() -> cp.apple.finalcutpro.inspector.color.ColorPuck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Starts a Color Puck. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>ColorPuck</code> instance.</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops a Color Puck. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorPuck:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Color Puck Accessibility Object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An <code>axuielementObject</code> or <code>nil</code></li></ul> |

