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
 * [HINTS](#hints)
 * [ui](#ui)
* Functions - API calls offered directly by the extension
 * [adjustWindow](#adjustwindow)
 * [get](#get)
 * [getCell](#getcell)
 * [getGrid](#getgrid)
 * [getGridFrame](#getgridframe)
 * [hide](#hide)
 * [maximizeWindow](#maximizewindow)
 * [pushWindowDown](#pushwindowdown)
 * [pushWindowLeft](#pushwindowleft)
 * [pushWindowRight](#pushwindowright)
 * [pushWindowUp](#pushwindowup)
 * [resizeWindowShorter](#resizewindowshorter)
 * [resizeWindowTaller](#resizewindowtaller)
 * [resizeWindowThinner](#resizewindowthinner)
 * [resizeWindowWider](#resizewindowwider)
 * [set](#set)
 * [setGrid](#setgrid)
 * [setMargins](#setmargins)
 * [show](#show)
 * [snap](#snap)
 * [toggleShow](#toggleshow)

## API Documentation

### Variables

#### [HINTS](#hints)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.HINTS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | A bidimensional array (table of tables of strings) holding the keyboard hints (as per `hs.keycodes.map`) to be used for the interactive resizing interface.                                                                                         |
| **Notes**                                            | <ul><li><code>hs.inspect(hs.grid.HINTS)</code> from the console will show you how the table is built</li></ul><ul><li><code>hs.grid.show()</code></li></ul><pre><code>When displaying interactive grid, if gird dimensions (`hs.grid.setGrid()`) are greater than `HINTS` dimensions,</code></pre><pre><code>then Hammerspoon merges few cells such that interactive grid dimensions do not exceed `HINTS` dimensions.</code></pre><pre><code>This is done to make sure interactive grid cells do not run out of hints. The interactive grid ends up with</code></pre><pre><code>cells of varying height and width.</code></pre><pre><code>The actual grid is not affected. If you use API methods like `hs.grid.pushWindowDown()`, you will not face this</code></pre><pre><code>issue at all.</code></pre><pre><code>If you have a grid of higher dimensions and require an interactive gird that accurately models underlying grid</code></pre><pre><code>then set `HINTS` variable to a table that has same dimensions as your grid.</code></pre><pre><code>Following is an example of grid that has 16 columns</code></pre>                 |

#### [ui](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.ui` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Allows customization of the modal resizing grid user interface                                                                                         |

### Functions

#### [adjustWindow](#adjustwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.adjustWindow(fn, window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Calls a user specified function to adjust a window's cell                                                                                         |
| **Parameters**                                       | <ul><li>fn - a function that accepts a cell object as its only argument. The function should modify it as needed and return nothing</li></ul><ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.get(win) -> cell` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the cell describing a window                                                                                         |
| **Parameters**                                       | <ul><li>an <code>hs.window</code> object to get the cell of</li></ul>   |
| **Returns**                                          | <ul><li>a cell object (i.e. an <code>hs.geometry</code> rect), or nil if an error occurred</li></ul>            |

#### [getCell](#getcell)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.getCell(cell, screen) -> hs.geometry` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the `hs.geometry` rect for a cell on a particular screen                                                                                         |
| **Parameters**                                       | <ul><li>cell - a cell object, i.e. an <code>hs.geometry</code> rect or argument to construct one</li></ul><ul><li>screen - an <code>hs.screen</code> object or argument to <code>hs.screen.find()</code> where the cell is located</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.geometry</code> rect for a cell on a particular screen or nil if the screen isn't found</li></ul>            |

#### [getGrid](#getgrid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.getGrid(screen) -> hs.geometry size` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the defined grid size for a given screen or screen resolution                                                                                         |
| **Parameters**                                       | <ul><li>screen - an <code>hs.screen</code> object, or a valid argument to <code>hs.screen.find()</code>, indicating the screen to get the grid of;</li></ul><p>if omitted or nil, gets the default grid, which is used when no specific grid is found for any given screen/resolution</p>   |
| **Returns**                                          | <ul><li>an <code>hs.geometry</code> size object indicating the number of columns and rows in the grid</li></ul>            |
| **Notes**                                            | <ul><li>if a grid was not set for the specified screen or geometry, the default grid will be returned</li></ul>                 |

#### [getGridFrame](#getgridframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.getGridFrame(screen) -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the defined grid frame for a given screen or screen resolution.                                                                                         |
| **Parameters**                                       | <ul><li>screen - an <code>hs.screen</code> object, or a valid argument to <code>hs.screen.find()</code>, indicating the screen to get the grid frame of</li></ul>   |
| **Returns**                                          | <ul><li>an <code>hs.geometry</code> rect object indicating the frame used by the grid for the given screen; if no custom frame</li></ul><pre><code>was given via `hs.grid.setGrid()`, returns the screen's frame</code></pre>            |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.hide()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hides the grid, if visible, and exits the modal resizing mode.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>If an exit callback was provided when invoking the modal interface, calling <code>.hide()</code> will call it</li></ul>                 |

#### [maximizeWindow](#maximizewindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.maximizeWindow(window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves and resizes a window to fill the entire grid                                                                                         |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [pushWindowDown](#pushwindowdown)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.pushWindowDown(window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves a window one grid cell down the screen, or onto the adjacent screen's grid when necessary                                                                                         |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [pushWindowLeft](#pushwindowleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.pushWindowLeft(window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves a window one grid cell to the left, or onto the adjacent screen's grid when necessary                                                                                         |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [pushWindowRight](#pushwindowright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.pushWindowRight(window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves a window one cell to the right, or onto the adjacent screen's grid when necessary                                                                                         |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [pushWindowUp](#pushwindowup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.pushWindowUp(window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves a window one grid cell up the screen, or onto the adjacent screen's grid when necessary                                                                                         |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [resizeWindowShorter](#resizewindowshorter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.resizeWindowShorter(window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resizes a window so its bottom edge moves one grid cell higher                                                                                         |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [resizeWindowTaller](#resizewindowtaller)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.resizeWindowTaller(window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resizes a window so its bottom edge moves one grid cell lower                                                                                         |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |
| **Notes**                                            | <ul><li>if the window hits the bottom edge of the screen and is asked to become taller, its top edge will shift further up</li></ul>                 |

#### [resizeWindowThinner](#resizewindowthinner)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.resizeWindowThinner(window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resizes a window to be one cell thinner                                                                                         |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [resizeWindowWider](#resizewindowwider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.resizeWindowWider(window) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Resizes a window to be one cell wider                                                                                         |
| **Parameters**                                       | <ul><li>window - an <code>hs.window</code> object to act on; if omitted, the focused or frontmost window will be used</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |
| **Notes**                                            | <ul><li>if the window hits the right edge of the screen and is asked to become wider, its left edge will shift further left</li></ul>                 |

#### [set](#set)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.set(win, cell, screen) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the cell for a window on a particular screen                                                                                         |
| **Parameters**                                       | <ul><li>win - an <code>hs.window</code> object representing the window to operate on</li></ul><ul><li>cell - a cell object, i.e. an <code>hs.geometry</code> rect or argument to construct one, to apply to the window</li></ul><ul><li>screen - (optional) an <code>hs.screen</code> object or argument to <code>hs.screen.find()</code> representing the screen to place the window on; if omitted</li></ul><pre><code>        the window's current screen will be used</code></pre>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [setGrid](#setgrid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.setGrid(grid,screen,frame) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the grid size for a given screen or screen resolution                                                                                         |
| **Parameters**                                       | <ul><li>grid - an <code>hs.geometry</code> size, or argument to construct one, indicating the number of columns and rows for the grid</li></ul><ul><li>screen - an <code>hs.screen</code> object, or a valid argument to <code>hs.screen.find()</code>, indicating the screen(s) to apply the grid to;</li></ul><p>if omitted or nil, sets the default grid, which is used when no specific grid is found for any given screen/resolution</p><ul><li>frame - an <code>hs.geometry</code> rect object indicating the frame that the grid will occupy for the given screen;</li></ul><p>if omitted or nil, the screen's <code>:frame()</code> will be used; use this argument if you want e.g. to leave</p><p>a strip of the desktop unoccluded when using GeekTool or similar. The <code>screen</code> argument <em>must</em> be non-nil when setting a</p><p>custom grid frame.</p>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [setMargins](#setmargins)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.setMargins(margins) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the margins between windows                                                                                         |
| **Parameters**                                       | <ul><li>margins - an <code>hs.geometry</code> point or size, or argument to construct one, indicating the desired margins between windows in screen points</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.show([exitedCallback][, multipleWindows])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the grid and starts the modal interactive resizing process for the focused or frontmost window.                                                                                         |
| **Parameters**                                       | <ul><li>exitedCallback - (optional) a function that will be called after the user dismisses the modal interface</li></ul><ul><li>multipleWindows - (optional) if <code>true</code>, the resizing grid won't automatically go away after selecting the desired cells</li></ul><p>for the frontmost window; instead, it'll switch to the next window</p>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>In the modal interface, press the arrow keys to jump to adjacent screens; spacebar to maximize/unmaximize; esc to quit without any effect</li></ul><ul><li>Pressing <code>tab</code> or <code>shift-tab</code> in the modal interface will cycle to the next or previous window; if <code>multipleWindows</code></li></ul><p>is false or omitted, the first press will just enable the multiple windows behaviour</p><ul><li>The keyboard hints assume a QWERTY layout; if you use a different layout, change <code>hs.grid.HINTS</code> accordingly</li></ul><ul><li>If grid dimensions are greater than 10x10 then you may have to change <code>hs.grid.HINTS</code> depending on your</li></ul><p>requirements. See note in <code>HINTS</code>.</p>                 |

#### [snap](#snap)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.snap(win) -> hs.grid` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Snaps a window into alignment with the nearest grid lines                                                                                         |
| **Parameters**                                       | <ul><li>win - an <code>hs.window</code> object to snap</li></ul>   |
| **Returns**                                          | <ul><li>the <code>hs.grid</code> module for method chaining</li></ul>            |

#### [toggleShow](#toggleshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.grid.toggleShow([exitedCallback][, multipleWindows])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles the grid and modal resizing mode - see `hs.grid.show()` and `hs.grid.hide()`                                                                                         |
| **Returns**                                          | <ul><li>None</li></ul>            |

