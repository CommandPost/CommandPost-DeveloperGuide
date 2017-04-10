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
| Signature   | hs.layout.left25  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the left 25% of a screen |

#### [left30](#left30)
| Signature   | hs.layout.left30  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the left 30% of a screen |

#### [left50](#left50)
| Signature   | hs.layout.left50  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the left 50% of a screen |

#### [left70](#left70)
| Signature   | hs.layout.left70  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the left 70% of a screen |

#### [left75](#left75)
| Signature   | hs.layout.left75  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the left 75% of a screen |

#### [maximized](#maximized)
| Signature   | hs.layout.maximized  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy all of a screen |

#### [right25](#right25)
| Signature   | hs.layout.right25  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the right 25% of a screen |

#### [right30](#right30)
| Signature   | hs.layout.right30  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the right 30% of a screen |

#### [right50](#right50)
| Signature   | hs.layout.right50  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the right 50% of a screen |

#### [right70](#right70)
| Signature   | hs.layout.right70  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the right 70% of a screen |

#### [right75](#right75)
| Signature   | hs.layout.right75  |
| Type        | Constant |
| Description | A unit rect which will make a window occupy the right 75% of a screen |

### Functions

#### [apply](#apply)
| Signature   | hs.layout.apply(table[, windowTitleComparator])  |
| Type        | Function |
| Description | Applies a layout to applications/windows |
      ```layout1 = {
            {"Mail", nil, "Color LCD", hs.layout.maximized, nil, nil},
            {"Safari", nil, "Thunderbolt Display", hs.layout.maximized, nil, nil},
            {"iTunes", "iTunes", "Color LCD", hs.layout.maximized, nil, nil},
            {"iTunes", "MiniPlayer", "Color LCD", nil, nil, hs.geometry.rect(0, -48, 400, 48)},
          }```
     * An example of a function that works well as a `windowTitleComparator` is the Lua built-in `string.match`, which uses Lua Patterns to match strings
| Parameters |  * table - A table describing your desired layout. Each element in the table should be another table describing a set of windows to match, and their desired size/position. The fields in each of these tables are:  * A string containing an application name, or an `hs.application` object, or nil  * A string containing a window title or nil  * A string containing a screen name, or an `hs.screen` object, or a function that accepts no parameters and returns an `hs.screen` object, or nil to select the first available screen  * A Unit rect, or a function which is called for each window and returns a unit rect (see `hs.window.moveToUnit()`). The function should accept one parameter, which is the window object.  * A Frame rect, or a function which is called for each window and returns a frame rect (see `hs.screen:frame()`). The function should accept one parameter, which is the window object.  * A Full-frame rect, of a function which is called for each window and returns a full-frame rect (see `hs.screen:fullFrame()`). The function should accept one parameter, which is the window object. * windowTitleComparator - (optional) Function to use for window title comparison. It is called with two string arguments (below) and its return value is evaluated as a boolean. If no comparator is provided, the '==' operator is used  * windowTitle: The `:title()` of the window object being examined  * layoutWindowTitle: The window title string (second field) specified in each element of the layout table | | Returns |  * None | | Notes |  * If the application name argument is nil, window titles will be matched regardless of which app they belong to * If the window title argument is nil, all windows of the specified application will be matched * You can specify both application name and window title if you want to match only one window of a particular application * If you specify neither application name or window title, no windows will be matched :) * Monitor name is a string, as found in `hs.screen:name()`. You can also pass an `hs.screen` object, or a function that returns an `hs.screen` object. If you pass nil, the first screen will be selected * The final three arguments use `hs.geometry.rect()` objects to describe the desired position and size of matched windows:   * Unit rect will be passed to `hs.window.moveToUnit()`   * Frame rect will be passed to `hs.window.setFrame()` (including menubar and dock)   * Full-frame rect will be passed to `hs.window.setFrame()` (ignoring menubar and dock) * If either the x or y components of frame/full-frame rect are negative, they will be applied as offsets against the opposite edge of the screen (e.g. If x is -100 then the left edge of the window will be 100 pixels from the right edge of the screen) * Only one of the rect arguments will apply to any matched windows. If you specify more than one, the first will win * An example usage: | 