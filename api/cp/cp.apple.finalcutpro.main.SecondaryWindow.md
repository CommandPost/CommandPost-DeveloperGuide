# [docs](index.md) » cp.apple.finalcutpro.main.SecondaryWindow
---

Secondary Window Module.

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [frame](#frame)
* Methods - API calls which can only be made on an object returned by a constructor
 * [watch](#watch)
 * [window](#window)

## API Documentation

### Fields

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.SecondaryWindow.frame <cp.prop: frame>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The current position (x, y, width, height) of the window.                                                                                         |

### Methods

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.SecondaryWindow:watch() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Watch for events that happen in the command editor                                                                                         |
| **Parameters**                                       | <ul><li>`events` - A table of functions with to watch. These may be:</li><li>  `show(window)` - Triggered when the window is shown.</li><li>  `hide(window)` - Triggered when the window is hidden.</li><li>  `move(window)` - Triggered when the window is moved.</li></ul> |
| **Returns**                                          | <ul><li>An ID which can be passed to `unwatch` to stop watching.</li></ul>          |

#### [window](#window)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.SecondaryWindow:window() -> cp.ui.Window` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `Window` instance.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `Window` instance.</li></ul>          |

