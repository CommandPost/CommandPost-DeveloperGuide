# [docs](index.md) » cp.apple.finalcutpro.timeline.CaptionsSubrole
---

*Extends [Role](cp.apple.finalcutpro.timeline.Role.md)*

A [Role](cp.apple.finalcutpro.timeline.Role.md) representing Captions.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [CaptionsSubrole](#captionssubrole)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [format](#format)
 * [visibleInTimeline](#visibleintimeline)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.CaptionsSubrole.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is a "Captions" Subrole. |

### Constructors

#### [CaptionsSubrole](#captionssubrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.CaptionsSubrole(parent, uiFinder)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new instance with the specified `parent` and `uiFinder`. |
| **Parameters**                                       | <ul><li>parent - the parent <code>Element</code>.</li><li>uiFinder - a <code>function</code> or <code>cp.prop</code> containing the <code>axuielement</code></li></ul> |
| **Returns**                                          | <ul><li>The new <code>Row</code>.</li></ul> |

### Fields

#### [format](#format)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.CaptionsSubrole.format <cp.ui.StaticText>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [StaticText](cp.ui.StaticText.md) which represents the subtitle format (e.g. "ITT", "SRT"). |

#### [visibleInTimeline](#visibleintimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.CaptionsSubrole.visibleInTimeline <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [CheckBox](cp.ui.CheckBox.md) that indicates if the subtitle track is visible in the Viewer. |

