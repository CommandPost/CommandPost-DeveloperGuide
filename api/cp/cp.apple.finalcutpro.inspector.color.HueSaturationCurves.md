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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`parent`		- The parent</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A HueSaturationCurves object</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The application object as a table</li></ul>          |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Hue/Saturation Curves panel currently showing?                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if showing, otherwise `false`</li></ul>          |

#### [mix](#mix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:mix([value]) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the Hue/Saturation Curves mix value.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">[value] - An optional value you want to set the mix value to as number (0 to 1).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A number containing the mix value or `nil` if an error occurs.</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the HueSaturationCurves's parent table                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The parent object as a table</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Color Board within the Color Inspector.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">HueSaturationCurves object</li></ul>          |

#### [viewMode](#viewmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:viewMode([value]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the View Mode for the Hue/Saturation Curves.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">[value] - An optional value to set the View Mode, as defined in `cp.apple.finalcutpro.inspector.color.HueSaturationCurves.VIEW_MODES`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing the View Mode or `nil` if an error occurs.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Value can be:</li><li markdown="1">  6 Curves</li><li markdown="1">  Single Curves</li></ul>                |

#### [visibleCurve](#visiblecurve)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.color.HueSaturationCurves:visibleCurve([value]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the selected hue/saturation curve.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">[value] - An optional value to set the visible curve, as defined in `cp.apple.finalcutpro.inspector.color.HueSaturationCurves.CURVES`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string containing the selected color curve or `nil` if an error occurs.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Value can be:</li><li markdown="1">  6 Curves</li><li markdown="1">  HvH</li><li markdown="1">  HvS</li><li markdown="1">  HvL</li><li markdown="1">  LvS</li><li markdown="1">  SvS</li><li markdown="1">  Orange</li><li markdown="1">Example Usage:</li><li markdown="1">   `require("cp.apple.finalcutpro"):inspector():color():hueSaturationCurves():visibleCurve("HvH")`</li></ul>                |

