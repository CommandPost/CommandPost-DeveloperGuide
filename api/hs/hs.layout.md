# [docs](index.md) » hs.layout
---

Window layout manager

This extension allows you to trigger window placement/sizing to a number of windows at once

## API Overview
* Constants - Useful values which cannot be changed
 * [left25](#left25)
 * [left30](#left30)
 * [left50](#left50)
 * [left70](#left70)
 * [left75](#left75)
 * [maximized](#maximized)
 * [right25](#right25)
 * [right30](#right30)
 * [right50](#right50)
 * [right70](#right70)
 * [right75](#right75)
* Functions - API calls offered directly by the extension
 * [apply](#apply)

## API Documentation

### Constants

#### [left25](#left25)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.left25` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the left 25% of a screen                                                                                         |

#### [left30](#left30)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.left30` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the left 30% of a screen                                                                                         |

#### [left50](#left50)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.left50` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the left 50% of a screen                                                                                         |

#### [left70](#left70)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.left70` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the left 70% of a screen                                                                                         |

#### [left75](#left75)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.left75` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the left 75% of a screen                                                                                         |

#### [maximized](#maximized)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.maximized` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy all of a screen                                                                                         |

#### [right25](#right25)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.right25` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the right 25% of a screen                                                                                         |

#### [right30](#right30)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.right30` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the right 30% of a screen                                                                                         |

#### [right50](#right50)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.right50` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the right 50% of a screen                                                                                         |

#### [right70](#right70)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.right70` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the right 70% of a screen                                                                                         |

#### [right75](#right75)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.right75` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A unit rect which will make a window occupy the right 75% of a screen                                                                                         |

### Functions

#### [apply](#apply)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.layout.apply(table[, windowTitleComparator])` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Applies a layout to applications/windows                                                                                         |
| **Parameters**                                       | <ul><li>table - A table describing your desired layout. Each element in the table should be another table describing a set of windows to match, and their desired size/position. The fields in each of these tables are:</li><li> A string containing an application name, or an `hs.application` object, or nil</li><li> A string containing a window title or nil</li><li> A string containing a screen name, or an `hs.screen` object, or a function that accepts no parameters and returns an `hs.screen` object, or nil to select the first available screen</li><li> A Unit rect, or a function which is called for each window and returns a unit rect (see `hs.window.moveToUnit()`). The function should accept one parameter, which is the window object.</li><li> A Frame rect, or a function which is called for each window and returns a frame rect (see `hs.screen:frame()`). The function should accept one parameter, which is the window object.</li><li> A Full-frame rect, of a function which is called for each window and returns a full-frame rect (see `hs.screen:fullFrame()`). The function should accept one parameter, which is the window object.</li><li>windowTitleComparator - (optional) Function to use for window title comparison. It is called with two string arguments (below) and its return value is evaluated as a boolean. If no comparator is provided, the '==' operator is used</li><li> windowTitle: The `:title()` of the window object being examined</li><li> layoutWindowTitle: The window title string (second field) specified in each element of the layout table</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>If the application name argument is nil, window titles will be matched regardless of which app they belong to</li><li>If the window title argument is nil, all windows of the specified application will be matched</li><li>You can specify both application name and window title if you want to match only one window of a particular application</li><li>If you specify neither application name or window title, no windows will be matched :)</li><li>Monitor name is a string, as found in `hs.screen:name()`. You can also pass an `hs.screen` object, or a function that returns an `hs.screen` object. If you pass nil, the first screen will be selected</li><li>The final three arguments use `hs.geometry.rect()` objects to describe the desired position and size of matched windows:</li><li>  Unit rect will be passed to `hs.window.moveToUnit()`</li><li>  Frame rect will be passed to `hs.window.setFrame()` (including menubar and dock)</li><li>  Full-frame rect will be passed to `hs.window.setFrame()` (ignoring menubar and dock)</li><li>If either the x or y components of frame/full-frame rect are negative, they will be applied as offsets against the opposite edge of the screen (e.g. If x is -100 then the left edge of the window will be 100 pixels from the right edge of the screen)</li><li>Only one of the rect arguments will apply to any matched windows. If you specify more than one, the first will win</li><li>An example usage:</li></ul>                |

