# [docs](index.md) » cp.apple.finalcutpro.timeline.AudioRole
---

*Extends [Role](cp.apple.finalcutpro.timeline.Role.md)*

A [Role](cp.apple.finalcutpro.timeline.Role.md) representing Audio.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [AudioRole](#audiorole)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [focusedInTimeline](#focusedintimeline)
 * [subroleLanes](#subrolelanes)
 * [subrolesExpanded](#subrolesexpanded)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doFocusInTimeline](#dofocusintimeline)
 * [doHideSubroleLanes](#dohidesubrolelanes)
 * [doShowSubroleLanes](#doshowsubrolelanes)
 * [doUnfocusInTimeline](#dounfocusintimeline)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.AudioRole.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is a "Audio" Role. |

### Constructors

#### [AudioRole](#audiorole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.AudioRole(parent, uiFinder)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new instance with the specified `parent` and `uiFinder`. |
| **Parameters**                                       | <ul><li>parent - the parent <code>Element</code>.</li><li>uiFinder - a <code>function</code> or <code>cp.prop</code> containing the <code>axuielement</code></li></ul> |
| **Returns**                                          | <ul><li>The new <code>Row</code>.</li></ul> |

### Fields

#### [focusedInTimeline](#focusedintimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.AudioRole.focusedInTimeline <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [CheckBox](cp.ui.CheckBox.md) that toggles this role is larger than the other audio roles on the timeline. |

#### [subroleLanes](#subrolelanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.AudioRole.subroleLanes <cp.ui.CheckButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [CheckButton](cp.ui.CheckButton.md) that toggles whether the subroles are visible in the [Timeline](cp.apple.finalcutpro.timeline.Timeline.md). |

#### [subrolesExpanded](#subrolesexpanded)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.AudioRole.subrolesExpanded <cp.ui.CheckButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [CheckButton](cp.ui.CheckButton.md) that toggles whether the roles are visible in the Index. |
| **Notes**                                            | <ul><li>Unlike the <a href="cp.finalcutpro.apple.timeline.VideoRole.md">VideoRole</a> and <a href="cp.apple.finalcutpro.timeline.CaptionsRole.md">CaptionsRole</a>, this is a <a href="cp.ui.CheckBox.md">CheckBox</a> and is always visible.</li></ul> |

### Methods

#### [doFocusInTimeline](#dofocusintimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.AudioRole:doFocusInTimeline() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to focus on this audio role in the timeline. |

#### [doHideSubroleLanes](#dohidesubrolelanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.AudioRole:doHideSubroleLanes() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to hide the subrole lanes on this audio role in the timeline. |

#### [doShowSubroleLanes](#doshowsubrolelanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.AudioRole:doShowSubroleLanes() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to show the subrole lanes on this audio role in the timeline. |

#### [doUnfocusInTimeline](#dounfocusintimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.AudioRole:doUnfocusInTimeline() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to unfocus on this audio role in the timeline. |

