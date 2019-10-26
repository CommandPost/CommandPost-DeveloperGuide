# [docs](index.md) » cp.apple.finalcutpro.timeline.SpeedPopover
---

*Extends [Timeline](cp.apple.finalcutpro.timeline.md)*

Represents the Speed Popover.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [SpeedPopover](#speedpopover)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [direction](#direction)
 * [duration](#duration)
 * [durationValue](#durationvalue)
 * [forward](#forward)
 * [rate](#rate)
 * [rateValue](#ratevalue)
 * [reverse](#reverse)
 * [ripple](#ripple)
 * [setSpeed](#setspeed)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doShow](#doshow)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is a "Video" Role. |

### Constructors

#### [SpeedPopover](#speedpopover)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover(parent, uiFinder)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new instance with the specified `parent` and `uiFinder`. |
| **Parameters**                                       | <ul><li>parent - the parent <code>Element</code>.</li><li>uiFinder - a <code>function</code> or <code>cp.prop</code> containing the <code>axuielement</code></li></ul> |
| **Returns**                                          | <ul><li>The new <code>SpeedPopover</code>.</li></ul> |

### Fields

#### [direction](#direction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:direction <cp.ui.RadioGroup>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioGroup](cp.ui.RadioGroup.md) for the "Direction" radio group. |

#### [duration](#duration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:duration <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Forward" radio button. |

#### [durationValue](#durationvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:durationValue <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [TextField](cp.ui.TextField.md) for the "Duration" text field. |

#### [forward](#forward)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:forward <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Forward" radio button. |

#### [rate](#rate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:rate <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Forward" radio button. |

#### [rateValue](#ratevalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:rateValue <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [TextField](cp.ui.TextField.md) for the "Rate" text field. |

#### [reverse](#reverse)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:reverse <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Reverse" radio button. |

#### [ripple](#ripple)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:ripple <cp.ui.RadioGroup>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [CheckBox](cp.ui.CheckBox.md) for the "Ripple" checkbox. |

#### [setSpeed](#setspeed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:setSpeed <cp.ui.RadioGroup>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioGroup](cp.ui.RadioGroup.md) for the "Set Speed" radio group. |

### Methods

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.SpeedPopover:doShow() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will show the Speed Popover. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code> which will send <code>true</code> if it successful, or <code>false</code> otherwise.</li></ul> |

