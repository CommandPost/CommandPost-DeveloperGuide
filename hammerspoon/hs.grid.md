# [docs](index.md) » hs.grid
---

Move/resize windows within a grid

The grid partitions your screens for the purposes of window management. The default layout of the grid is 3 columns by 3 rows.
You can specify different grid layouts for different screens and/or screen resolutions.

Windows that are aligned with the grid have their location and size described as a `cell`. Each cell is an `hs.geometry` rect with these fields:
 * x - The column of the left edge of the window
 * y - The row of the top edge of the window
 * w - The number of columns the window occupies
 * h - The number of rows the window occupies

For a grid of 3x3:
 * a cell `'0,0 1x1'` will be in the upper-left corner
 * a cell `'2,0 1x1'` will be in the upper-right corner
 * and so on...

Additionally, a modal keyboard driven interface for interactive resizing is provided via `hs.grid.show()`;
The grid will be overlaid on the focused or frontmost window's screen with keyboard hints.
To resize/move the window, you can select the corner cells of the desired position.
For a move-only, you can select a cell and confirm with 'return'. The celected cell will become the new upper-left of the window.
You can also use the arrow keys to move the window onto adjacent screens, and the tab/shift-tab keys to cycle to the next/previous window.
Once you selected a cell, you can use the arrow keys to navigate through the grid. In this case, the grid will highlight the selected cells.
After highlighting enough cells, press enter to move/resize the window to the highlighted area.

## API Overview
* Variables - Configurable values
 * [HINTS](#HINTS)
 * [ui](#ui)
* Functions - API calls offered directly by the extension
 * [adjustWindow](#adjustWindow)
 * [get](#get)
 * [getCell](#getCell)
 * [getGrid](#getGrid)
 * [getGridFrame](#getGridFrame)
 * [hide](#hide)
 * [maximizeWindow](#maximizeWindow)
 * [pushWindowDown](#pushWindowDown)
 * [pushWindowLeft](#pushWindowLeft)
 * [pushWindowRight](#pushWindowRight)
 * [pushWindowUp](#pushWindowUp)
 * [resizeWindowShorter](#resizeWindowShorter)
 * [resizeWindowTaller](#resizeWindowTaller)
 * [resizeWindowThinner](#resizeWindowThinner)
 * [resizeWindowWider](#resizeWindowWider)
 * [set](#set)
 * [setGrid](#setGrid)
 * [setMargins](#setMargins)
 * [show](#show)
 * [snap](#snap)
 * [toggleShow](#toggleShow)

## API Documentation

### Variables

| #### [HINTS](#HINTS)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.HINTS                                                            |
| **Type**                                    | Variable                                                           |
| **Description**                             | A bidimensional array (table of tables of strings) holding the keyboard hints (as per `hs.keycodes.map`) to be used for the interactive resizing interface.                                                           |
| **Notes**                                   |  * `hs.inspect(hs.grid.HINTS)` from the console will show you how the table is built                        |

| #### [ui](#ui)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.ui                                                            |
| **Type**                                    | Variable                                                           |
| **Description**                             | Allows customization of the modal resizing grid user interface                                                           |

### Functions

| #### [adjustWindow](#adjustWindow)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.adjustWindow(fn, window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Calls a user specified function to adjust a window's cell                                                           |
| **Parameters**                              |  * fn - a function that accepts a cell object as its only argument. The function should modify it as needed and return nothing * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [get](#get)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.get(win) -> cell                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the cell describing a window                                                           |
| **Parameters**                              | * an `hs.window` object to get the cell of         |
| **Returns**                                 | * a cell object (i.e. an `hs.geometry` rect), or nil if an error occurred                  |

| #### [getCell](#getCell)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.getCell(cell, screen) -> hs.geometry                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the `hs.geometry` rect for a cell on a particular screen                                                           |
| **Parameters**                              |  * cell - a cell object, i.e. an `hs.geometry` rect or argument to construct one * screen - an `hs.screen` object or argument to `hs.screen.find()` where the cell is located         |
| **Returns**                                 |  * the `hs.geometry` rect for a cell on a particular screen or nil if the screen isn't found                  |

| #### [getGrid](#getGrid)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.getGrid(screen) -> hs.geometry size                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the defined grid size for a given screen or screen resolution                                                           |
| **Parameters**                              |  * screen - an `hs.screen` object, or a valid argument to `hs.screen.find()`, indicating the screen to get the grid of;   if omitted or nil, gets the default grid, which is used when no specific grid is found for any given screen/resolution         |
| **Returns**                                 |   * an `hs.geometry` size object indicating the number of columns and rows in the grid                  |
| **Notes**                                   |   * if a grid was not set for the specified screen or geometry, the default grid will be returned                        |

| #### [getGridFrame](#getGridFrame)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.getGridFrame(screen) -> hs.geometry rect                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the defined grid frame for a given screen or screen resolution.                                                           |
| **Parameters**                              |  * screen - an `hs.screen` object, or a valid argument to `hs.screen.find()`, indicating the screen to get the grid frame of         |
| **Returns**                                 |   * an `hs.geometry` rect object indicating the frame used by the grid for the given screen; if no custom frame    was given via `hs.grid.setGrid()`, returns the screen's frame                  |

| #### [hide](#hide)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.hide()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Hides the grid, if visible, and exits the modal resizing mode.                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |
| **Notes**                                   |  * If an exit callback was provided when invoking the modal interface, calling `.hide()` will call it                        |

| #### [maximizeWindow](#maximizeWindow)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.maximizeWindow(window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Moves and resizes a window to fill the entire grid                                                           |
| **Parameters**                              |  * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [pushWindowDown](#pushWindowDown)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.pushWindowDown(window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Moves a window one grid cell down the screen, or onto the adjacent screen's grid when necessary                                                           |
| **Parameters**                              |  * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [pushWindowLeft](#pushWindowLeft)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.pushWindowLeft(window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Moves a window one grid cell to the left, or onto the adjacent screen's grid when necessary                                                           |
| **Parameters**                              |  * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [pushWindowRight](#pushWindowRight)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.pushWindowRight(window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Moves a window one cell to the right, or onto the adjacent screen's grid when necessary                                                           |
| **Parameters**                              |  * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [pushWindowUp](#pushWindowUp)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.pushWindowUp(window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Moves a window one grid cell up the screen, or onto the adjacent screen's grid when necessary                                                           |
| **Parameters**                              |  * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [resizeWindowShorter](#resizeWindowShorter)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.resizeWindowShorter(window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Resizes a window so its bottom edge moves one grid cell higher                                                           |
| **Parameters**                              |  * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [resizeWindowTaller](#resizeWindowTaller)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.resizeWindowTaller(window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Resizes a window so its bottom edge moves one grid cell lower                                                           |
| **Parameters**                              |  * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |
| **Notes**                                   |  * if the window hits the bottom edge of the screen and is asked to become taller, its top edge will shift further up                        |

| #### [resizeWindowThinner](#resizeWindowThinner)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.resizeWindowThinner(window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Resizes a window to be one cell thinner                                                           |
| **Parameters**                              |  * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [resizeWindowWider](#resizeWindowWider)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.resizeWindowWider(window) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Resizes a window to be one cell wider                                                           |
| **Parameters**                              |  * window - an `hs.window` object to act on; if omitted, the focused or frontmost window will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |
| **Notes**                                   |  * if the window hits the right edge of the screen and is asked to become wider, its left edge will shift further left                        |

| #### [set](#set)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.set(win, cell, screen) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Sets the cell for a window on a particular screen                                                           |
| **Parameters**                              |  * win - an `hs.window` object representing the window to operate on * cell - a cell object, i.e. an `hs.geometry` rect or argument to construct one, to apply to the window * screen - (optional) an `hs.screen` object or argument to `hs.screen.find()` representing the screen to place the window on; if omitted            the window's current screen will be used         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [setGrid](#setGrid)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.setGrid(grid,screen,frame) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Sets the grid size for a given screen or screen resolution                                                           |
| **Parameters**                              |  * grid - an `hs.geometry` size, or argument to construct one, indicating the number of columns and rows for the grid * screen - an `hs.screen` object, or a valid argument to `hs.screen.find()`, indicating the screen(s) to apply the grid to;   if omitted or nil, sets the default grid, which is used when no specific grid is found for any given screen/resolution * frame - an `hs.geometry` rect object indicating the frame that the grid will occupy for the given screen;   if omitted or nil, the screen's `:frame()` will be used; use this argument if you want e.g. to leave   a strip of the desktop unoccluded when using GeekTool or similar. The `screen` argument *must* be non-nil when setting a   custom grid frame.         |
| **Returns**                                 |   * the `hs.grid` module for method chaining                  |

| #### [setMargins](#setMargins)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.setMargins(margins) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Sets the margins between windows                                                           |
| **Parameters**                              |  * margins - an `hs.geometry` point or size, or argument to construct one, indicating the desired margins between windows in screen points         |
| **Returns**                                 |   * the `hs.grid` module for method chaining                  |

| #### [show](#show)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.show([exitedCallback][, multipleWindows])                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Shows the grid and starts the modal interactive resizing process for the focused or frontmost window.                                                           |
| **Parameters**                              |  * exitedCallback - (optional) a function that will be called after the user dismisses the modal interface * multipleWindows - (optional) if `true`, the resizing grid won't automatically go away after selecting the desired cells   for the frontmost window; instead, it'll switch to the next window         |
| **Returns**                                 |  * None                  |
| **Notes**                                   |  * In the modal interface, press the arrow keys to jump to adjacent screens; spacebar to maximize/unmaximize; esc to quit without any effect * Pressing `tab` or `shift-tab` in the modal interface will cycle to the next or previous window; if `multipleWindows`   is false or omitted, the first press will just enable the multiple windows behaviour * The keyboard hints assume a QWERTY layout; if you use a different layout, change `hs.grid.HINTS` accordingly                        |

| #### [snap](#snap)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.snap(win) -> hs.grid                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Snaps a window into alignment with the nearest grid lines                                                           |
| **Parameters**                              |  * win - an `hs.window` object to snap         |
| **Returns**                                 |  * the `hs.grid` module for method chaining                  |

| #### [toggleShow](#toggleShow)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.grid.toggleShow([exitedCallback][, multipleWindows])                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Toggles the grid and modal resizing mode - see `hs.grid.show()` and `hs.grid.hide()`                                                           |
| **Returns**                                 |  * None                  |

