# [docs](index.md) » plugins.finder.window
---

Handy tools for Windows Management in macOS.

Inspired by [WinWin](http://www.hammerspoon.org/Spoons/WinWin.html) for [Hammerspoon](http://www.hammerspoon.org/).

## API Overview
* Variables - Configurable values
 * [gridparts](#gridparts)
* Functions - API calls offered directly by the extension
 * [centerCursor](#centercursor)
 * [grid](#grid)
 * [hints](#hints)
 * [moveAndResize](#moveandresize)
 * [moveToScreen](#movetoscreen)
 * [stepMove](#stepmove)
 * [stepResize](#stepresize)
 * [undo](#undo)

## API Documentation

### Variables

#### [gridparts](#gridparts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finder.window.gridparts` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | An integer specifying how many gridparts the screen should be divided into. Defaults to 30.                                                                                         |

### Functions

#### [centerCursor](#centercursor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finder.window.centerCursor() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Center the cursor on the focused window.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [grid](#grid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finder.window.grid() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows a modal keyboard driven interface for interactive window resizing.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [hints](#hints)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finder.window.hints() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a keyboard hint for switching focus to each window.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [moveAndResize](#moveandresize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finder.window.moveAndResize(option)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Move and resize the focused window.                                                                                         |
| **Parameters**                                       | <ul><br /><li>option - A string specifying the option, valid strings are: <code>halfleft</code>, <code>halfright</code>, <code>halfup</code>, <code>halfdown</code>, <code>cornerNW</code>, <code>cornerSW</code>, <code>cornerNE</code>, <code>cornerSE</code>, <code>center</code>, <code>fullscreen</code>, <code>expand</code>, <code>shrink</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [moveToScreen](#movetoscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finder.window.moveToScreen(direction)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Move the focused window between all of the screens in the `direction`.                                                                                         |
| **Parameters**                                       | <ul><br /><li>direction - A string specifying the direction, valid strings are: <code>left</code>, <code>right</code>, <code>up</code>, <code>down</code>, <code>next</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [stepMove](#stepmove)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finder.window.stepMove(direction)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Move the focused window in the `direction` by one step. The step scale equals to the width/height of one gridpart.                                                                                         |
| **Parameters**                                       | <ul><br /><li>direction - A string specifying the direction, valid strings are: <code>left</code>, <code>right</code>, <code>up</code>, <code>down</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [stepResize](#stepresize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finder.window.stepResize(direction)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resize the focused window in the `direction` by on step.                                                                                         |
| **Parameters**                                       | <ul><br /><li>direction - A string specifying the direction, valid strings are: <code>left</code>, <code>right</code>, <code>up</code>, <code>down</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [undo](#undo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finder.window.undo()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Undo the last window manipulation. Only those "moveAndResize" manipulations can be undone.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

