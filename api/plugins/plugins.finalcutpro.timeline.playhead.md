# [docs](index.md) » plugins.finalcutpro.timeline.playhead
---

Manages features relating to the Timeline Playhead.

## API Overview
* Variables - Configurable values
 * [playheadLocked](#playheadlocked)
 * [playheadTracked](#playheadtracked)
 * [scrollingTimeline](#scrollingtimeline)
* Functions - API calls offered directly by the extension
 * [checkScrollingTimeline](#checkscrollingtimeline)
 * [getScrollingTimelineWatcher](#getscrollingtimelinewatcher)
 * [update](#update)

## API Documentation

### Variables

#### [playheadLocked](#playheadlocked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.playhead.playheadLocked <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Playhead Locked?                                                                                         |

#### [playheadTracked](#playheadtracked)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.playhead.playheadTracked <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Checks if the playhead is being actively tracked, either by scrolling timeline or the playhead lock.                                                                                         |

#### [scrollingTimeline](#scrollingtimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.playhead.scrollingTimeline <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Enables or disables the scrolling timeline.                                                                                         |

### Functions

#### [checkScrollingTimeline](#checkscrollingtimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.playhead.checkScrollingTimeline() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if we should actually turn on the scrolling timeline.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if we should, `false` if not.</li></ul>          |

#### [getScrollingTimelineWatcher](#getscrollingtimelinewatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.playhead.getScrollingTimelineWatcher() -> eventtap` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the Scrolling Timeline Watcher.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The scrolling timeline watcher `eventtap`.</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.playhead.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Ensures the Scrolling Timeline/Playhead Lock are in the correct mode                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

