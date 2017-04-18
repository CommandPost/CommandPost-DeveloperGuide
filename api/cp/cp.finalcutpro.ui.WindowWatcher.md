# [docs](index.md) » cp.finalcutpro.ui.WindowWatcher
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
| **Signature**                               | `cp.finalcutpro.ui.WindowWatcher:new(windowFn) -> WindowWatcher`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Creates a new WindowWatcher                                                                     |
| **Parameters**                              | <ul><li>`window` 	- the window object (eg. CommandEditor)</li></ul> |
| **Returns**                                 | <ul><li>`WindowWatcher`	- the new WindowWatcher instance.</li></ul>          |

#### [unwatch](#unwatch)
| **Signature**                               | `cp.finalcutpro.ui.WindowWatcher:unwatch() -> bool`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Removes the watch with the specified ID                                                                     |
| **Parameters**                              | <ul><li>`id` - The ID returned from `watch` that wants to be removed.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

#### [watch](#watch)
| **Signature**                               | `cp.finalcutpro.ui.WindowWatcher:watch() -> bool`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Watch for events that happen in the window                                                                     |
| **Parameters**                              | <ul><li>`events` - A table of functions with to watch. These may be:</li><li>  `show(CommandEditor)` - Triggered when the window is shown.</li><li>  `hide(window)` - Triggered when the window is hidden.</li></ul> |
| **Returns**                                 | <ul><li>An ID which can be passed to `unwatch` to stop watching.</li></ul>          |

