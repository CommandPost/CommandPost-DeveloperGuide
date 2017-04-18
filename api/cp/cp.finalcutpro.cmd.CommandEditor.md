# [docs](index.md) » cp.finalcutpro.cmd.CommandEditor
---

Command Editor Module.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [watch](#watch)

## API Documentation

### Methods

#### [watch](#watch)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.finalcutpro.cmd.CommandEditor:watch() -> bool` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Watch for events that happen in the command editor. The optional functions will be called when the window is shown or hidden, respectively.                                                                                         |
| **Parameters**                                       | <ul><li>`events` - A table of functions with to watch. These may be:</li><li>  `show(CommandEditor)` - Triggered when the window is shown.</li><li>  `hide(CommandEditor)` - Triggered when the window is hidden.</li></ul> |
| **Returns**                                          | <ul><li>An ID which can be passed to `unwatch` to stop watching.</li></ul>          |

