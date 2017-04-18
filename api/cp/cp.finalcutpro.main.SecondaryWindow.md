# [docs](index.md) » cp.finalcutpro.main.SecondaryWindow
---

Secondary Window Module.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [watch](#watch)

## API Documentation

### Methods

#### [watch](#watch)
| **Signature**                               | `cp.finalcutpro.main.SecondaryWindow:watch() -> bool`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Method                                                                     |
| **Description**                             | Watch for events that happen in the command editor                                                                     |
| **Parameters**                              | <ul><li>`events` - A table of functions with to watch. These may be:</li><li>  `show(CommandEditor)` - Triggered when the window is shown.</li><li>  `hide(CommandEditor)` - Triggered when the window is hidden.</li></ul> |
| **Returns**                                 | <ul><li>An ID which can be passed to `unwatch` to stop watching.</li></ul>          |

