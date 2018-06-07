# [docs](index.md) » cp.apple.finalcutpro.inspector.color.HueSaturationCurves
---

Hue/Saturation Curves Module.

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
 * [show](#show)
 * [viewMode](#viewmode)
 * [visibleCurve](#visiblecurve)

## API Documentation

### Constants

#### [CURVES](#curves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.CURVES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table containing all the different types of Color Curves                                                                                         |

#### [VIEW_MODES](#view_modes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.VIEW_MODES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | View Modes for Color Curves                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves.new(parent) -> HueSaturationCurves object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new HueSaturationCurves object                                                                                         |
| **Parameters**                                       | <ul><li>`parent`		- The parent</li></ul> |
| **Returns**                                          | <ul><li>A HueSaturationCurves object</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul>          |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Hue/Saturation Curves panel currently showing?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if showing, otherwise `false`</li></ul>          |

#### [mix](#mix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:mix([value]) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the Hue/Saturation Curves mix value.                                                                                         |
| **Parameters**                                       | <ul><li>[value] - An optional value you want to set the mix value to as number (0 to 1).</li></ul> |
| **Returns**                                          | <ul><li>A number containing the mix value or `nil` if an error occurs.</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the HueSaturationCurves's parent table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Color Board within the Color Inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>HueSaturationCurves object</li></ul>          |

#### [viewMode](#viewmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:viewMode([value]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the View Mode for the Hue/Saturation Curves.                                                                                         |
| **Parameters**                                       | <ul><li>[value] - An optional value to set the View Mode, as defined in `cp.apple.finalcutpro.inspector.color.HueSaturationCurves.VIEW_MODES`.</li></ul> |
| **Returns**                                          | <ul><li>A string containing the View Mode or `nil` if an error occurs.</li></ul>          |
| **Notes**                                            | <ul><li>Value can be:</li><li>  6 Curves</li><li>  Single Curves</li></ul>                |

#### [visibleCurve](#visiblecurve)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:visibleCurve([value]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the selected hue/saturation curve.                                                                                         |
| **Parameters**                                       | <ul><li>[value] - An optional value to set the visible curve, as defined in `cp.apple.finalcutpro.inspector.color.HueSaturationCurves.CURVES`.</li></ul> |
| **Returns**                                          | <ul><li>A string containing the selected color curve or `nil` if an error occurs.</li></ul>          |
| **Notes**                                            | <ul><li>Value can be:</li><li>  6 Curves</li><li>  HvH</li><li>  HvS</li><li>  HvL</li><li>  LvS</li><li>  SvS</li><li>  Orange</li><li>Example Usage:</li><li>   `require("cp.apple.finalcutpro"):inspector():color():hueSaturationCurves():visibleCurve("HvH")`</li></ul>                |

