# [docs](index.md) » cp.apple.finalcutpro.WindowWatcher
---

Window Watcher Module.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [new](#new)
 * [unwatch](#unwatch)
 * [watch](#watch)

## API Documentation

### Methods

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.WindowWatcher:new(windowFn) -> WindowWatcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new WindowWatcher                                                                                         |
| **Parameters**                                       | <ul><li>`window`     - the window object (eg. CommandEditor)</li></ul> |
| **Returns**                                          | <ul><li>`WindowWatcher`  - the new WindowWatcher instance.</li></ul>          |

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.WindowWatcher:unwatch() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Removes the watch with the specified ID                                                                                         |
| **Parameters**                                       | <ul><li>`id` - The ID returned from `watch` that wants to be removed.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.WindowWatcher:watch() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Watch for events that happen in the window                                                                                         |
| **Parameters**                                       | <ul><li>`events` - A table of functions with to watch. These may be:</li><li>  `show(window)` - Triggered when the window is shown.</li><li>  `hide(window)` - Triggered when the window is hidden.</li><li>  `open(window)` - Triggered when the window is opened.</li><li>  `close(window)` - Triggered when the window is closed.</li><li>  `move(window)` - Triggered when the window is moved.</li></ul> |
| **Returns**                                          | <ul><li>An ID which can be passed to `unwatch` to stop watching.</li></ul>          |

