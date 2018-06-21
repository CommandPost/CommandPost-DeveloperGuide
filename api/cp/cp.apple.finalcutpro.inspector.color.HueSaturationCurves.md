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
| **Parameters**                                       |  * `parent`		- The parent                                       |
| **Returns**                                          |  * A HueSaturationCurves object                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The application object as a table                                                |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Hue/Saturation Curves panel currently showing?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if showing, otherwise `false`                                                |

#### [mix](#mix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:mix([value]) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the Hue/Saturation Curves mix value.                                                                                         |
| **Parameters**                                       |  * [value] - An optional value you want to set the mix value to as number (0 to 1).                                       |
| **Returns**                                          |  * A number containing the mix value or `nil` if an error occurs.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the HueSaturationCurves's parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Color Board within the Color Inspector.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * HueSaturationCurves object                                                |

#### [viewMode](#viewmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:viewMode([value]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the View Mode for the Hue/Saturation Curves.                                                                                         |
| **Parameters**                                       |  * [value] - An optional value to set the View Mode, as defined in `cp.apple.finalcutpro.inspector.color.HueSaturationCurves.VIEW_MODES`.                                       |
| **Returns**                                          |  * A string containing the View Mode or `nil` if an error occurs.                                                |
| **Notes**                                            |  * Value can be:   * 6 Curves   * Single Curves                                                      |

#### [visibleCurve](#visiblecurve)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:visibleCurve([value]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the selected hue/saturation curve.                                                                                         |
| **Parameters**                                       |  * [value] - An optional value to set the visible curve, as defined in `cp.apple.finalcutpro.inspector.color.HueSaturationCurves.CURVES`.                                       |
| **Returns**                                          |  * A string containing the selected color curve or `nil` if an error occurs.                                                |
| **Notes**                                            |  * Value can be:   * 6 Curves   * HvH   * HvS   * HvL   * LvS   * SvS   * Orange * Example Usage:   `require("cp.apple.finalcutpro"):inspector():color():hueSaturationCurves():visibleCurve("HvH")`                                                      |

