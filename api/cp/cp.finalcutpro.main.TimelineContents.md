# [docs](index.md) » cp.finalcutpro.main.TimelineContents
---

Timeline Contents Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [clipsUI](#clipsUI)
 * [playheadClipsUI](#playheadClipsUI)
 * [selectedClipsUI](#selectedClipsUI)

## API Documentation

### Functions

| [clipsUI](#clipsUI)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.main.TimelineContents:clipsUI(expandedGroups, filterFn) -> table of axuielements`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table containing the list of clips in the Timeline.                                                                     |
| **Parameters**                              | <ul><li>expandGroups	- (optional) if true, expand AXGroups to include contained AXLayoutItems</li><li>filterFn		- (optional) if provided, the function will be called to check each clip</li></ul> |
| **Returns**                                 | <ul><li>The table of axuielements that match the conditions</li></ul>          |

| [playheadClipsUI](#playheadClipsUI)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.main.TimelineContents:playheadClipsUI(expandedGroups, filterFn) -> table of axuielements`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table array containing the list of clips in the Timeline under the playhead, ordered with the                                                                     |
| **Parameters**                              | <ul><li>expandGroups	- (optional) if true, expand AXGroups to include contained AXLayoutItems</li><li>filterFn		- (optional) if provided, the function will be called to check each clip</li></ul> |
| **Returns**                                 | <ul><li>The table of axuielements that match the conditions</li></ul>          |

| [selectedClipsUI](#selectedClipsUI)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.main.TimelineContents:selectedClipsUI(expandedGroups, filterFn) -> table of axuielements`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table containing the list of selected clips.                                                                     |
| **Parameters**                              | <ul><li>expandGroups	- (optional) if true, expand AXGroups to include contained AXLayoutItems</li><li>filterFn		- (optional) if provided, the function will be called to check each clip</li></ul> |
| **Returns**                                 | <ul><li>The table of selected axuielements that match the conditions</li></ul>          |

