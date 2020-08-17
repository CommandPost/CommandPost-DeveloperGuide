# [docs](index.md) » cp.apple.finalcutpro.timeline.CaptionsRole
---

*Extends [Role](cp.apple.finalcutpro.timeline.Role.md)*

A [Role](cp.apple.finalcutpro.timeline.Role.md) representing Captions.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [CaptionsRole](#captionsrole)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [subrolesExpanded](#subrolesexpanded)
 * [visibleInViewer](#visibleinviewer)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.CaptionsRole.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is a "Captions" Role. |

### Constructors

#### [CaptionsRole](#captionsrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.CaptionsRole(parent, uiFinder)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new instance with the specified `parent` and `uiFinder`. |
| **Parameters**                                       | <ul><li>parent - the parent <code>Element</code>.</li><li>uiFinder - a <code>function</code> or <code>cp.prop</code> containing the <code>axuielement</code></li></ul> |
| **Returns**                                          | <ul><li>The new <code>Row</code>.</li></ul> |

### Fields

#### [subrolesExpanded](#subrolesexpanded)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.CaptionsRole.subrolesExpanded <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [Button](cp.ui.Button.md) that toggles whether the sub-captions are visible. |

#### [visibleInViewer](#visibleinviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.CaptionsRole.visibleInViewer <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [CheckBox](cp.ui.CheckBox.md) that toggles whether captions are visible in the [Viewer](cp.apple.finalcutpro.viewer.Viewer.md). |

