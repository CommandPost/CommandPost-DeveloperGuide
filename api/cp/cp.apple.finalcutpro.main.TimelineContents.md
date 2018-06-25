# [docs](index.md) » cp.apple.finalcutpro.main.TimelineContents
---

Timeline Contents Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [clipsUI](#clipsui)
 * [playheadClipsUI](#playheadclipsui)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [horizontalScrollBarUI](#horizontalscrollbarui)
 * [isFocused](#isfocused)
 * [isLoaded](#isloaded)
 * [isShowing](#isshowing)
 * [scrollAreaUI](#scrollareaui)
 * [UI](#ui)
 * [verticalScrollBarUI](#verticalscrollbarui)
 * [viewFrame](#viewframe)
* Methods - API calls which can only be made on an object returned by a constructor
 * [rangeSelectionUI](#rangeselectionui)
 * [selectedClipsUI](#selectedclipsui)

## API Documentation

### Functions

#### [clipsUI](#clipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:clipsUI(expandedGroups, filterFn) -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table containing the list of clips in the Timeline.                                                                                         |
| **Parameters**                                       | <ul><br /><li>expandGroups - (optional) if true, expand AXGroups to include contained AXLayoutItems * filterFn     - (optional) if provided, the function will be called to check each clip</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The table of axuielements that match the conditions</li><br /></ul>                                           |

#### [playheadClipsUI](#playheadclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:playheadClipsUI(expandedGroups, filterFn) -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table array containing the list of clips in the Timeline under the playhead, ordered with the                                                                                         |
| **Parameters**                                       | <ul><br /><li>expandGroups - (optional) if true, expand AXGroups to include contained AXLayoutItems * filterFn     - (optional) if provided, the function will be called to check each clip</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The table of axuielements that match the conditions</li><br /></ul>                                           |

### Fields

#### [horizontalScrollBarUI](#horizontalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.horizontalScrollBarUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `AXHorizontalScrolLbar` for the Timeline Contents area.                                                                                         |

#### [isFocused](#isfocused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.isFocused <cp.prop: booelan; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the Timeline is currently the focused panel.                                                                                         |

#### [isLoaded](#isloaded)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.isLoaded <cp.prop: booelan; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the Timeline has content loaded.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.isShowing <cp.prop: booelan; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the Timeline is currently showing.                                                                                         |

#### [scrollAreaUI](#scrollareaui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.scrollAreaUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The parent `ScrollArea` UI of the Timeline Contents area.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.UI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The main UI of the Timeline Contents area.                                                                                         |

#### [verticalScrollBarUI](#verticalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.verticalScrollBarUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `AXVerticalScrollBar` for the Timeline Contents area.                                                                                         |

#### [viewFrame](#viewframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents.viewFrame <cp.prop: table; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The current 'frame' of the internal timeline content,  or `nil` if not available.                                                                                         |

### Methods

#### [rangeSelectionUI](#rangeselectionui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:rangeSelectionUI() -> axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the UI for the current 'Range Selection', if present.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The 'Range Selection' UI or <code>nil</code></li><br /></ul>                                           |

#### [selectedClipsUI](#selectedclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:selectedClipsUI(expandedGroups, filterFn) -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table containing the list of selected clips.                                                                                         |
| **Parameters**                                       | <ul><br /><li>expandGroups - (optional) if true, expand AXGroups to include contained AXLayoutItems * filterFn     - (optional) if provided, the function will be called to check each clip</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The table of selected axuielements that match the conditions</li><br /></ul>                                           |

