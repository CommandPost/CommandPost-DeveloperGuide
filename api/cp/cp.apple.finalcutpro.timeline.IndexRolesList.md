# [docs](index.md) » cp.apple.finalcutpro.timeline.IndexRolesList
---

Timeline Index Roles List.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [allRoles](#allroles)
 * [audioRoles](#audioroles)
 * [doActivate](#doactivate)
 * [doDeactivate](#dodeactivate)
 * [doFocusInTimeline](#dofocusintimeline)
 * [doHideSubroleLanes](#dohidesubrolelanes)
 * [doShowSubroleLanes](#doshowsubrolelanes)
 * [doUnfocusInTimeline](#dounfocusintimeline)
 * [filterRoles](#filterroles)
 * [findRoleTitled](#findroletitled)
 * [videoRoles](#videoroles)

## API Documentation

### Methods

#### [allRoles](#allroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:allRoles([includeSubroles]) -> table of Roles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the list of caption [Role](cp.ui.Role.md)s in the current list. |
| **Parameters**                                       | <ul><li>includeSubroles - if <code>true</code>, include Subroles, otherwise exclude them.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> of <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>s, or <code>nil</code> if no UI is available currently.</li></ul> |

#### [audioRoles](#audioroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:audioRoles([includeSubroles]) -> table of Roles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the list of all audio [Role](cp.ui.Role.md)s in the current list. |
| **Parameters**                                       | <ul><li>includeSubroles - if <code>true</code>, include Subroles, otherwise exclude them.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> of <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>s, or <code>nil</code> if no UI is available currently.</li></ul> |

#### [doActivate](#doactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:doActivate(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will activate the provided role, if it is available. |
| **Parameters**                                       | <ul><li>title - The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a> to activate.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Video", "Titles", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doDeactivate](#dodeactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:doDeactivate(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will deactivate the provided role, if it is available. |
| **Parameters**                                       | <ul><li>title - The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a> to deactivate.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Video", "Titles", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doFocusInTimeline](#dofocusintimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:doFocusInTimeline(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will focus the provided [AudioRole](cp.apple.finalcutpro.timeline.AudioRole.md), if it is available. |
| **Parameters**                                       | <ul><li>title - The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a> to activate.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Video", "Titles", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doHideSubroleLanes](#dohidesubrolelanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:doHideSubroleLanes(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will hide subrole lanes for the provided [AudioRole](cp.apple.finalcutpro.timeline.AudioRole.md), if it is available. |
| **Parameters**                                       | <ul><li>title - The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Dialogue", "Music", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doShowSubroleLanes](#doshowsubrolelanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:doShowSubroleLanes(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will show subrole lanes for the provided [AudioRole](cp.apple.finalcutpro.timeline.AudioRole.md), if it is available. |
| **Parameters**                                       | <ul><li>title - The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Dialogue", "Music", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doUnfocusInTimeline](#dounfocusintimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:doUnfocusInTimeline(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will unfocus the provided [AudioRole](cp.apple.finalcutpro.timeline.AudioRole.md), if it is available. |
| **Parameters**                                       | <ul><li>title - The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a> to activate.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Dialogue", "Music", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [filterRoles](#filterroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:filterRoles([matcherFn]) -> table of Roles or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Filters the current list of [Role](cp.apple.finalcutpro.timeline.Role.md)s based on the given `matchesFn` predicate. |
| **Parameters**                                       | <ul><li>matchesFn - the matcher function. If not provided, no additional filtering occurs.</li></ul> |
| **Returns**                                          | <ul><li>The table of <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>, or <code>nil</code> if no UI is currently available.</li></ul> |

#### [findRoleTitled](#findroletitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:findRoleTitled(title) -> Role or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the [Role](cp.apple.finalcutpro.timeline.Role.md) with the specified title. |
| **Parameters**                                       | <ul><li>title - The title of the role to find.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>, or <code>nil</code> if it can't be found.</li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Video", "Titles", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [videoRoles](#videoroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRolesList:videoRoles([includeSubroles]) -> table of Roles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the list of all video [Role](cp.ui.Role.md)s in the current list. |
| **Parameters**                                       | <ul><li>includeSubroles - if <code>true</code>, include Subroles, otherwise exclude them.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> of <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>s, or <code>nil</code> if no UI is available currently.</li></ul> |

