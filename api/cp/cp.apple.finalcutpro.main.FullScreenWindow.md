# [docs](index.md) » cp.apple.finalcutpro.main.FullScreenWindow
---

Full Screen Window

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [unwatch](#unwatch)
 * [watch](#watch)

## API Documentation

### Methods

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow:unwatch(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Unwatches an event.                                                                                         |
| **Parameters**                                       | <ul><li>id - The ID that would have been previously returned by the `watch()` function.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FullScreenWindow:watch() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Watch for events that happen in the command editor                                                                                         |
| **Parameters**                                       | <ul><li>`events` - A table of functions with to watch. These may be:</li><li>  `show(CommandEditor)` - Triggered when the window is shown.</li><li>  `hide(CommandEditor)` - Triggered when the window is hidden.</li></ul> |
| **Returns**                                          | <ul><li>A table containing an ID which can be passed to `unwatch` to stop watching.</li></ul>          |

