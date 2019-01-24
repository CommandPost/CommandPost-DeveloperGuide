# [docs](index.md) » cp.apple.finalcutpro.timeline.IndexRoles
---

Provides access to the 'Roles' section of the [Timeline Index](cp.apple.finalcutpro.timeline.Index.md)

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [activate](#activate)
 * [allRoles](#allroles)
 * [area](#area)
 * [audioRoles](#audioroles)
 * [captionRoles](#captionroles)
 * [collapseSubroles](#collapsesubroles)
 * [doActivate](#doactivate)
 * [doCollapseSubroles](#docollapsesubroles)
 * [doDeactivate](#dodeactivate)
 * [doFocusInTimeline](#dofocusintimeline)
 * [doHideAudioLanes](#dohideaudiolanes)
 * [doHideSubroleLanes](#dohidesubrolelanes)
 * [doLayout](#dolayout)
 * [doShowAudioLanes](#doshowaudiolanes)
 * [doShowSubroleLanes](#doshowsubrolelanes)
 * [doUnfocusInTimeline](#dounfocusintimeline)
 * [editRoles](#editroles)
 * [fineRoleTitled](#fineroletitled)
 * [hideAudioLanes](#hideaudiolanes)
 * [list](#list)
 * [saveLayout](#savelayout)
 * [showAudioLanes](#showaudiolanes)
 * [videoRoles](#videoroles)

## API Documentation

### Methods

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:activate() -> cp.ui.RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) that activates the 'Roles' section. |

#### [allRoles](#allroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:allRoles([includeSubroles]) -> table of Roles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds all Roles, optionally including all Subroles |
| **Parameters**                                       | <ul><li>includeSubroles - (defaults to <code>false</code>) if <code>true</code> include subroles.</li></ul> |
| **Returns**                                          | <ul><li>The table of <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>s, or <code>nil</code> if no UI is available.</li></ul> |

#### [area](#area)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:area() -> cp.apple.finalcutpro.timeline.IndexRolesArea` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [IndexRolesArea](cp.apple.finalcutpro.timeline.IndexRolesArea.md) containing the list of [Role](cp.apple.finalcutpro.timeline.Role.md). |

#### [audioRoles](#audioroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:audioRoles([includeSubroles]) -> table of Roles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds all Audio Roles, optionally including all Subroles |
| **Parameters**                                       | <ul><li>includeSubroles - (defaults to <code>false</code>) if <code>true</code> include subroles.</li></ul> |
| **Returns**                                          | <ul><li>The table of <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>s, or <code>nil</code> if no UI is available.</li></ul> |

#### [captionRoles](#captionroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:captionRoles([includeSubroles]) -> table of Roles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds all Caption Roles, optionally including all Subroles |
| **Parameters**                                       | <ul><li>includeSubroles - (defaults to <code>false</code>) if <code>true</code> include subroles.</li></ul> |
| **Returns**                                          | <ul><li>The table of <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>s, or <code>nil</code> if no UI is available.</li></ul> |

#### [collapseSubroles](#collapsesubroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:collapseSubroles() -> cp.ui.Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The `Collapse Subroles` [Button](cp.ui.Button.md). |

#### [doActivate](#doactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doActivate(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will activate the provided role, if it is available. |
| **Parameters**                                       | <ul><li>The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a> to activate.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Video", "Titles", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doCollapseSubroles](#docollapsesubroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doCollapseSubroles() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will collapse subroles, if they are currently expanded. |

#### [doDeactivate](#dodeactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doDeactivate(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will deactivate the provided role, if it is available. |
| **Parameters**                                       | <ul><li>The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a> to activate.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Video", "Titles", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doFocusInTimeline](#dofocusintimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doFocusInTimeline(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will focus the listed role, if it is available and is an [AudioRole](cp.apple.finalcutpro.timeline.AudioRole.md). |
| **Parameters**                                       | <ul><li>The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a> to activate.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Dialogue", "Music", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doHideAudioLanes](#dohideaudiolanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doHideAudioLanes() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will collapse subroles (if necessary) and hide the audio lanes. |

#### [doHideSubroleLanes](#dohidesubrolelanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doHideSubroleLanes(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will hide the subrole lanes for the listed role, if it is available and is an [AudioRole](cp.apple.finalcutpro.timeline.AudioRole.md). |
| **Parameters**                                       | <ul><li>The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Dialogue", "Music", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doLayout](#dolayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doLayout(layout) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will apply the layout provided, if possible. |
| **Parameters**                                       | <ul><li>layout - the <code>table</code> containing the layout configuration. Usually created via the [#saveLayout] method.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a>.</li></ul> |

#### [doShowAudioLanes](#doshowaudiolanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doShowAudioLanes() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will show the Audio Lanes when executed. |

#### [doShowSubroleLanes](#doshowsubrolelanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doShowSubroleLanes(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will show subrole lanes for the role, if it is available and is an [AudioRole](cp.apple.finalcutpro.timeline.AudioRole.md). |
| **Parameters**                                       | <ul><li>The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Dialogue", "Music", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [doUnfocusInTimeline](#dounfocusintimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:doUnfocusInTimeline(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will unfocus the listed role, if it is available and is an [AudioRole](cp.apple.finalcutpro.timeline.AudioRole.md). |
| **Parameters**                                       | <ul><li>The title of the <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a> to activate.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Dialogue", "Music", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [editRoles](#editroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:editRoles() -> cp.ui.Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The `Edit Roles...` [Button](cp.ui.Button.md). |

#### [fineRoleTitled](#fineroletitled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:fineRoleTitled(title) -> Role or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the [Role](cp.apple.finalcutpro.timeline.Role.md) with the specified title. |
| **Parameters**                                       | <ul><li>title - The title to match.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a> with the title, or <code>nil</code>.</li></ul> |
| **Notes**                                            | <ul><li>The title can be the English name (eg. "Video", "Titles", etc.) for default Roles, and it will find the correct role in the current FCPX language.</li></ul> |

#### [hideAudioLanes](#hideaudiolanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:hideAudioLanes() -> cp.ui.Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The `Hide Audio Lanes` [Button](cp.ui.Button.md). |

#### [list](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:list() -> cp.apple.finalcutpro.timeline.IndexRolesList` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [IndexRolesList](cp.apple.finalcutpro.timeline.IndexRolesList.md) for the roles. |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` containing the layout configuration for this class. |
| **Returns**                                          | <ul><li>The layout configuration <code>table</code>.</li></ul> |

#### [showAudioLanes](#showaudiolanes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:showAudioLanes() -> cp.ui.Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The `Show Audio Lanes` [Button](cp.ui.Button.md). |

#### [videoRoles](#videoroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexRoles:videoRoles([includeSubroles]) -> table of Roles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds all Video Roles, optionally including all Subroles |
| **Parameters**                                       | <ul><li>includeSubroles - (defaults to <code>false</code>) if <code>true</code> include subroles.</li></ul> |
| **Returns**                                          | <ul><li>The table of <a href="cp.apple.finalcutpro.timeline.Role.md">Role</a>s, or <code>nil</code> if no UI is available.</li></ul> |

