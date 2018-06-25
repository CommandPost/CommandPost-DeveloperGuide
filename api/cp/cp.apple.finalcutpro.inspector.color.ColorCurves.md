# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorCurves
---

Color Curves Module.

Requires Final Cut Pro 10.4 or later.

## API Overview
* Constants - Useful values which cannot be changed
 * [CURVES](#curves)
 * [VIEW_MODES](#view_modes)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [isShowing](#isshowing)
 * [mix](#mix)
 * [parent](#parent)
 * [preserveLuma](#preserveluma)
 * [show](#show)
 * [viewMode](#viewmode)
 * [visibleCurve](#visiblecurve)

## API Documentation

### Constants

#### [CURVES](#curves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.CURVES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table containing all the different types of Color Curves |

#### [VIEW_MODES](#view_modes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.VIEW_MODES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | View Modes for Color Curves |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves.new(parent) -> ColorCurves object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new ColorCurves object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A ColorInspector object</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul> |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Is the Color Curves panel currently showing? |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if showing, otherwise <code>false</code></li></ul> |

#### [mix](#mix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves:mix([value]) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets or gets the color curves mix value. |
| **Parameters**                                       | <ul><li>[value] - An optional value you want to set the mix value to as number (0 to 1).</li></ul> |
| **Returns**                                          | <ul><li>A number containing the mix value or <code>nil</code> if an error occurs.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the ColorCurves's parent table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul> |

#### [preserveLuma](#preserveluma)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves:preserveLuma([value]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets or gets whether or not Preserve Luma is active. |
| **Parameters**                                       | <ul><li>[value] - An optional boolean value to set the Preserve Luma option.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if Preserve Luma is selected, otherwise <code>false</code>.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's the Color Board within the Color Inspector. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorCurves object</li></ul> |

#### [viewMode](#viewmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves:viewMode([value]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets or gets the View Mode for the Color Curves. |
| **Parameters**                                       | <ul><li>[value] - An optional value to set the View Mode, as defined in <code>cp.apple.finalcutpro.inspector.color.ColorCurves.VIEW_MODES</code>.</li></ul> |
| **Returns**                                          | <ul><li>A string containing the View Mode or <code>nil</code> if an error occurs.</li></ul> |
| **Notes**                                            | <ul><li>Value can be:   * All Curves   * Single Curves</li></ul> |

#### [visibleCurve](#visiblecurve)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.ColorCurves:visibleCurve([value]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets or gets the selected color curve. |
| **Parameters**                                       | <ul><li>[value] - An optional value to set the visible curve, as defined in <code>cp.apple.finalcutpro.inspector.color.ColorCurves.CURVES</code>.</li></ul> |
| **Returns**                                          | <ul><li>A string containing the selected color curve or <code>nil</code> if an error occurs.</li></ul> |
| **Notes**                                            | <ul><li>Value can be:   * All Curves   * Luma   * Red   * Green   * Blue * Example Usage:   <code>require("cp.apple.finalcutpro"):inspector():color():colorCurves():visibleCurve("Luma")</code></li></ul> |

