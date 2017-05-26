# [docs](index.md) » cp.apple.finalcutpro.main.TimelineContents
---

Timeline Contents Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [clipsUI](#clipsui)
 * [playheadClipsUI](#playheadclipsui)
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
| **Parameters**                                       | <ul><li>expandGroups	- (optional) if true, expand AXGroups to include contained AXLayoutItems</li><li>filterFn		- (optional) if provided, the function will be called to check each clip</li></ul> |
| **Returns**                                          | <ul><li>The table of axuielements that match the conditions</li></ul>          |

#### [playheadClipsUI](#playheadclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:playheadClipsUI(expandedGroups, filterFn) -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table array containing the list of clips in the Timeline under the playhead, ordered with the                                                                                         |
| **Parameters**                                       | <ul><li>expandGroups	- (optional) if true, expand AXGroups to include contained AXLayoutItems</li><li>filterFn		- (optional) if provided, the function will be called to check each clip</li></ul> |
| **Returns**                                          | <ul><li>The table of axuielements that match the conditions</li></ul>          |

### Methods

#### [rangeSelectionUI](#rangeselectionui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:rangeSelectionUI() -> axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the UI for the current 'Range Selection', if present.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The 'Range Selection' UI or `nil`</li></ul>          |

#### [selectedClipsUI](#selectedclipsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.TimelineContents:selectedClipsUI(expandedGroups, filterFn) -> table of axuielements` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table containing the list of selected clips.                                                                                         |
| **Parameters**                                       | <ul><li>expandGroups	- (optional) if true, expand AXGroups to include contained AXLayoutItems</li><li>filterFn		- (optional) if provided, the function will be called to check each clip</li></ul> |
| **Returns**                                          | <ul><li>The table of selected axuielements that match the conditions</li></ul>          |

