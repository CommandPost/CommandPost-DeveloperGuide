# [docs](index.md) » cp.apple.finalcutpro.import.MediaImport
---

Media Import

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isShowing](#isshowing)
* Methods - API calls which can only be made on an object returned by a constructor
 * [watch](#watch)

## API Documentation

### Fields

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the Media Import window showing?                                                                                         |

### Methods

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport:watch() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Watch for events that happen in the command editor. The optional functions will be called when the window is shown or hidden, respectively.                                                                                         |
| **Parameters**                                       | <ul><li>`events` - A table of functions with to watch. These may be:</li><li>  `show(CommandEditor)` - Triggered when the window is shown.</li><li>  `hide(CommandEditor)` - Triggered when the window is hidden.</li></ul> |
| **Returns**                                          | <ul><li>An ID which can be passed to `unwatch` to stop watching.</li></ul>          |

