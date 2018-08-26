# [docs](index.md) » cp.apple.finalcutpro.main.TimelineContents
---

Timeline Contents Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [clipsUI](#clipsui)
 * [playheadClipsUI](#playheadclipsui)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [children](#children)
 * [horizontalScrollBarUI](#horizontalscrollbarui)
 * [isFocused](#isfocused)
 * [isLoaded](#isloaded)
 * [isShowing](#isshowing)
 * [scrollAreaUI](#scrollareaui)
 * [selectedChildren](#selectedchildren)
 * [UI](#ui)
 * [verticalScrollBarUI](#verticalscrollbarui)
 * [viewFrame](#viewframe)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doFocus](#dofocus)
 * [doHide](#dohide)
 * [doSelectClip](#doselectclip)
 * [doSelectClips](#doselectclips)
 * [doShow](#doshow)
 * [rangeSelectionUI](#rangeselectionui)
 * [selectedClipsUI](#selectedclipsui)

## API Documentation

### Functions

#### [clipsUI](#clipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:clipsUI(expandedGroups, filterFn) -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the list of clips in the Timeline. |
| **Parameters**                                       | <ul><li>expandGroups - (optional) if true, expand AXGroups to include contained AXLayoutItems</li><li>filterFn     - (optional) if provided, the function will be called to check each clip</li></ul> |
| **Returns**                                          | <ul><li>The table of axuielements that match the conditions</li></ul> |

#### [playheadClipsUI](#playheadclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:playheadClipsUI(expandedGroups, filterFn) -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table array containing the list of clips in the Timeline under the playhead, ordered with the |
| **Parameters**                                       | <ul><li>expandGroups - (optional) if true, expand AXGroups to include contained AXLayoutItems</li><li>filterFn     - (optional) if provided, the function will be called to check each clip</li></ul> |
| **Returns**                                          | <ul><li>The table of axuielements that match the conditions</li></ul> |

### Fields

#### [children](#children)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.children <cp.prop: table; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current set of child elements in the TimelineContents. |

#### [horizontalScrollBarUI](#horizontalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.horizontalScrollBarUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `AXHorizontalScrolLbar` for the Timeline Contents area. |

#### [isFocused](#isfocused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.isFocused <cp.prop: booelan; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Timeline is currently the focused panel. |

#### [isLoaded](#isloaded)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.isLoaded <cp.prop: booelan; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Timeline has content loaded. |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.isShowing <cp.prop: booelan; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Timeline is currently showing. |

#### [scrollAreaUI](#scrollareaui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.scrollAreaUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The parent `ScrollArea` UI of the Timeline Contents area. |

#### [selectedChildren](#selectedchildren)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.selectedChildren <cp.prop: table; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current set of selected child elements in the TimelineContents. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.UI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The main UI of the Timeline Contents area. |

#### [verticalScrollBarUI](#verticalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.verticalScrollBarUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `AXVerticalScrollBar` for the Timeline Contents area. |

#### [viewFrame](#viewframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.viewFrame <cp.prop: table; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current 'frame' of the internal timeline content,  or `nil` if not available. |

### Methods

#### [doFocus](#dofocus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:doFocus(show) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which will focus on the `TimelineContents`. |
| **Parameters**                                       | <ul><li>show      - if <code>true</code>, the <code>TimelineContents</code> will be shown before focusing.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>.</li></ul> |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to hide the Timeline Contents. |
| **Returns**                                          | <ul><li>The <code>Statement</code>.</li></ul> |

#### [doSelectClip](#doselectclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:doSelectClip(clipUI) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which will select the specified single `hs._asm.axuielement` value in the Timeline Contents area. |
| **Parameters**                                       | <ul><li>clipUI       - The <code>hs._asm.axuilement</code> values to select.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a> that will select the clip or throw an error if there is an issue.</li></ul> |

#### [doSelectClips](#doselectclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:doSelectClips(clipsUI) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which will select the specified list of `hs._asm.axuielement` values in the Timeline Contents area. |
| **Parameters**                                       | <ul><li>clipsUI       - The table of <code>hs._asm.axuilement</code> values to select.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a> that will select the clips or throw an error if there is an issue.</li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to show the Timeline Contents. |
| **Returns**                                          | <ul><li>The <code>Statement</code>.</li></ul> |

#### [rangeSelectionUI](#rangeselectionui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:rangeSelectionUI() -> axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the UI for the current 'Range Selection', if present. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The 'Range Selection' UI or <code>nil</code></li></ul> |

#### [selectedClipsUI](#selectedclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:selectedClipsUI(expandedGroups, filterFn) -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table containing the list of selected clips. |
| **Parameters**                                       | <ul><li>expandGroups - (optional) if true, expand AXGroups to include contained AXLayoutItems</li><li>filterFn     - (optional) if provided, the function will be called to check each clip</li></ul> |
| **Returns**                                          | <ul><li>The table of selected axuielements that match the conditions</li></ul> |

