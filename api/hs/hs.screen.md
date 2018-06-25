# [docs](index.md) » hs.screen
---

Manipulate screens (i.e. monitors)

The macOS coordinate system used by Hammerspoon assumes a grid that spans all the screens (positioned as per
System Preferences->Displays->Arrangement). The origin `0,0` is at the top left corner of the *primary screen*.
(Screens to the left of the primary screen, or above it, and windows on these screens, will have negative coordinates)

## Submodules
 * [hs.screen.watcher](hs.screen.watcher.md)

## API Overview
* Variables - Configurable values
 * [strictScreenInDirection](#strictscreenindirection)
* Functions - API calls offered directly by the extension
 * [accessibilitySettings](#accessibilitysettings)
 * [find](#find)
 * [restoreGamma](#restoregamma)
 * [screenPositions](#screenpositions)
* Constructors - API calls which return an object, typically one that offers API methods
 * [allScreens](#allscreens)
 * [mainScreen](#mainscreen)
 * [primaryScreen](#primaryscreen)
* Methods - API calls which can only be made on an object returned by a constructor
 * [absoluteToLocal](#absolutetolocal)
 * [availableModes](#availablemodes)
 * [currentMode](#currentmode)
 * [desktopImageURL](#desktopimageurl)
 * [frame](#frame)
 * [fromUnitRect](#fromunitrect)
 * [fullFrame](#fullframe)
 * [getBrightness](#getbrightness)
 * [getGamma](#getgamma)
 * [id](#id)
 * [localToAbsolute](#localtoabsolute)
 * [name](#name)
 * [next](#next)
 * [position](#position)
 * [previous](#previous)
 * [rotate](#rotate)
 * [setBrightness](#setbrightness)
 * [setGamma](#setgamma)
 * [setMode](#setmode)
 * [setPrimary](#setprimary)
 * [shotAsJPG](#shotasjpg)
 * [shotAsPNG](#shotaspng)
 * [snapshot](#snapshot)
 * [toEast](#toeast)
 * [toNorth](#tonorth)
 * [toSouth](#tosouth)
 * [toUnitRect](#tounitrect)
 * [toWest](#towest)

## API Documentation

### Variables

#### [strictScreenInDirection](#strictscreenindirection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.strictScreenInDirection` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | If set to `true`, the methods `hs.screen:toEast()`, `:toNorth()` etc. will disregard screens that lie perpendicularly to the desired axis                                                                                         |

### Functions

#### [accessibilitySettings](#accessibilitysettings)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.accessibilitySettings() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the current state of the screen-related accessibility settings                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing the following keys, and corresponding boolean values for whether the user has enabled these options:   * ReduceMotion (only available on macOS 10.12 or later)   * ReduceTransparency   * IncreaseContrast   * InvertColors (only available on macOS 10.12 or later)   * DifferentiateWithoutColor</li><br /></ul>                                           |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.find(hint) -> hs.screen object(s)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Finds screens                                                                                         |
| **Parameters**                                       | <ul><br /><li>hint - search criterion for the desired screen(s); it can be:  * a number as per <code>hs.screen:id()</code>  * a string pattern that matches (via <code>string.match</code>) the screen name as per <code>hs.screen:name()</code> (for convenience, the matching will be done on lowercased strings)  * an hs.geometry <em>point</em> object, or constructor argument, with the <em>x and y position</em> of the screen in the current layout as per <code>hs.screen:position()</code>  * an hs.geometry <em>size</em> object, or constructor argument, with the <em>resolution</em> of the screen as per <code>hs.screen:fullFrame()</code>  * an hs.geometry <em>rect</em> object, or constructor argument, with an arbitrary rect in absolute coordinates; the screen     containing the largest part of the rect will be returned</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>one or more hs.screen objects that match the supplied search criterion, or <code>nil</code> if none found</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>for convenience you call call this as <code>hs.screen(hint)</code></li><br /></ul>                                             |

#### [restoreGamma](#restoregamma)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.restoreGamma()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Restore the gamma settings to defaults                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This returns all displays to the gamma tables specified by the user's selected ColorSync display profiles</li><br /></ul>                                             |

#### [screenPositions](#screenpositions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.screenPositions() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of all connected and enabled screens, along with their "position" relative to the primary screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table where each <em>key</em> is an <code>hs.screen</code> object, and the corresponding value is a table {x=X,y=Y}, where X and Y attempt to indicate each screen's position relative to the primary screen (which is at {x=0,y=0}); so e.g. a value of {x=-1,y=0} indicates a screen immediately to the left of the primary screen, and a value of {x=0,y=2} indicates a screen positioned below the primary screen, with another screen inbetween.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>grid-like arrangements of same-sized screens should behave consistently; but there's no guarantee of a consistent result for more "exotic" screen arrangements</li><br /></ul>                                             |

### Constructors

#### [allScreens](#allscreens)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.allScreens() -> hs.screen[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns all the screens                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing one or more <code>hs.screen</code> objects</li><br /></ul>                                           |

#### [mainScreen](#mainscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.mainScreen() -> screen` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns the 'main' screen, i.e. the one containing the currently focused window                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object</li><br /></ul>                                           |

#### [primaryScreen](#primaryscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen.primaryScreen() -> screen` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Gets the primary screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object</li><br /></ul>                                           |

### Methods

#### [absoluteToLocal](#absolutetolocal)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:absoluteToLocal(geom) -> hs.geometry object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Transforms from the absolute coordinate space used by OSX/Hammerspoon to the screen's local                                                                                         |
| **Parameters**                                       | <ul><br /><li>geom - an hs.geometry point or rect, or arguments to construct one</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an hs.geometry point or rect, transformed to the screen's local coordinate space</li><br /></ul>                                           |

#### [availableModes](#availablemodes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:availableModes() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table containing the screen modes supported by the screen. A screen mode is a combination of resolution, scaling factor and colour depth                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing the supported screen modes. The keys of the table take the form of "1440x900@2x" (for a HiDPI mode) or "1680x1050@1x" (for a native DPI mode). The values are tables which contain the keys:  * w - A number containing the width of the screen mode in points  * h - A number containing the height of the screen mode in points  * scale - A number containing the scaling factor of the screen mode (typically <code>1</code> for a native mode, <code>2</code> for a HiDPI mode)</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Only 32-bit colour modes are returned. If you really need to know about 16-bit modes, please file an Issue on GitHub * "points" are not necessarily the same as pixels, because they take the scale factor into account (e.g. "1440x900@2x" is a 2880x1800 screen resolution, with a scaling factor of 2, i.e. with HiDPI pixel-doubled rendering enabled), however, they are far more useful to work with than native pixel modes, when a Retina screen is involved. For non-retina screens, points and pixels are equivalent.</li><br /></ul>                                             |

#### [currentMode](#currentmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:currentMode() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table describing the current screen mode                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing the current screen mode. The keys of the table are:  * w - A number containing the width of the screen mode in points  * h - A number containing the height of the screen mode in points  * scale - A number containing the scaling factor of the screen mode (typically <code>1</code> for a native mode, <code>2</code> for a HiDPI mode)  * desc - A string containing a representation of the mode as used in <code>hs.screen:availableModes()</code> - e.g. "1920x1080@2x"</li><br /></ul>                                           |

#### [desktopImageURL](#desktopimageurl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:desktopImageURL([imageURL])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets/Sets the desktop background image for a screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>imageURL - An optional file:// URL to an image file to set as the background. If omitted, the current file URL is returned</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the <code>hs.screen</code> object if a new URL was set, otherwise a string containing the current URL</li><br /></ul>                                           |

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:frame() -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the screen frame, without the dock or menu.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an hs.geometry rect describing this screen's "usable" frame (i.e. without the dock and menu bar) in absolute coordinates</li><br /></ul>                                           |

#### [fromUnitRect](#fromunitrect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:fromUnitRect(unitrect) -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the absolute rect of a given unit rect within this screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>unitrect - an hs.geometry unit rect, or arguments to construct one</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an hs.geometry rect describing the given unit rect in absolute coordinates</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>this method is just a convenience wrapper for <code>hs.geometry.fromUnitRect(unitrect,this_screen:frame())</code></li><br /></ul>                                             |

#### [fullFrame](#fullframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:fullFrame() -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the screen frame, including the dock and menu.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an hs.geometry rect describing this screen's frame in absolute coordinates</li><br /></ul>                                           |

#### [getBrightness](#getbrightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:getBrightness() -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the screen's brightness                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A floating point number between 0 and 1, containing the current brightness level, or nil if the display does not support brightness queries</li><br /></ul>                                           |

#### [getGamma](#getgamma)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:getGamma() -> [whitepoint, blackpoint] or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the current whitepoint and blackpoint of the screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing the white point and black point of the screen, or nil if an error occurred. The keys <code>whitepoint</code> and <code>blackpoint</code> each have values of a table containing the following keys, with corresponding values between 0.0 and 1.0:  * red  * green  * blue</li><br /></ul>                                           |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:id() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a screen's unique ID                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A number containing the ID of the screen</li><br /></ul>                                           |

#### [localToAbsolute](#localtoabsolute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:localToAbsolute(geom) -> hs.geometry object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Transforms from the screen's local coordinate space, where `0,0` is at the screen's top left corner,                                                                                         |
| **Parameters**                                       | <ul><br /><li>geom - an hs.geometry point or rect, or arguments to construct one</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an hs.geometry point or rect, transformed to the absolute coordinate space</li><br /></ul>                                           |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:name() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the preferred name for the screen set by the manufacturer                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string containing the name of the screen, or nil if an error occurred</li><br /></ul>                                           |

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:next() -> screen` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the screen 'after' this one (in arbitrary order); this method wraps around to the first screen.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object</li><br /></ul>                                           |

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:position() -> x, y` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a given screen's position relative to the primary screen - see 'hs.screen.screenPositions()'                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>two integers indicating the screen position in the current screen arrangement, in the x and y axis respectively.</li><br /></ul>                                           |

#### [previous](#previous)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:previous() -> screen` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the screen 'before' this one (in arbitrary order); this method wraps around to the last screen.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object</li><br /></ul>                                           |

#### [rotate](#rotate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:rotate([degrees]) -> bool or rotation angle` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets/Sets the rotation of a screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>degrees - An optional number indicating how many degrees clockwise, to rotate. If no number is provided, the current rotation will be returned. This number must be one of:  * 0  * 90  * 180  * 270</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>If the rotation is being set, a boolean, true if the operation succeeded, otherwise false. If the rotation is being queried, a number will be returned</li><br /></ul>                                           |

#### [setBrightness](#setbrightness)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:setBrightness(brightness) -> `hs.screen` object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the screen's brightness                                                                                         |
| **Parameters**                                       | <ul><br /><li>brightness - A floating point number between 0 and 1</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.screen</code> object</li><br /></ul>                                           |

#### [setGamma](#setgamma)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:setGamma(whitepoint, blackpoint) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the current white point and black point of the screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>whitepoint - A table containing color component values between 0.0 and 1.0 for each of the keys:  * red  * green  * blue * blackpoint - A table containing color component values between 0.0 and 1.0 for each of the keys:  * red  * green  * blue</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A boolean, true if the gamma settings were applied, false if an error occurred</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If the whitepoint and blackpoint specified, are very similar, it will be impossible to read the screen. You should exercise caution, and may wish to bind a hotkey to <code>hs.screen.restoreGamma()</code> when experimenting</li><br /></ul>                                             |

#### [setMode](#setmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:setMode(width, height, scale) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the screen to a new mode                                                                                         |
| **Parameters**                                       | <ul><br /><li>width - A number containing the width in points of the new mode * height - A number containing the height in points of the new mode * scale - A number containing the scaling factor of the new mode (typically 1 for native pixel resolutions, 2 for HiDPI/Retina resolutions)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A boolean, true if the requested mode was set, otherwise false</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The available widths/heights/scales can be seen in the output of <code>hs.screen:availableModes()</code>, however, it should be noted that the CoreGraphics subsystem seems to list more modes for a given screen than it is actually prepared to set, so you may find that seemingly valid modes still return false. It is not currently understood why this is so!</li><br /></ul>                                             |

#### [setPrimary](#setprimary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:setPrimary() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the screen to be the primary display (i.e. contain the menubar and dock)                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A boolean, true if the operation succeeded, otherwise false</li><br /></ul>                                           |

#### [shotAsJPG](#shotasjpg)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:shotAsJPG(filePath[, screenRect])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves an image of the screen to a JPG file                                                                                         |
| **Parameters**                                       | <ul><br /><li>filePath - A string containing a file path to save the screenshot as * screenRect - An optional <code>hs.geometry</code> rect (or arguments for its constructor) containing a portion of the screen to capture. Defaults to the whole screen</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [shotAsPNG](#shotaspng)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:shotAsPNG(filePath[, screenRect])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves an image of the screen to a PNG file                                                                                         |
| **Parameters**                                       | <ul><br /><li>filePath - A string containing a file path to save the screenshot as * screenRect - An optional <code>hs.geometry</code> rect (or arguments for its constructor) containing a portion of the screen to capture. Defaults to the whole screen</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:snapshot([rect]) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Captures an image of the screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>rect - An optional <code>rect-table</code> containing a portion of the screen to capture. Defaults to the whole screen</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.image</code> object, or nil if an error occurred</li><br /></ul>                                           |

#### [toEast](#toeast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:toEast() -> hs.screen object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the first screen to the east of this one, ordered by proximity to its center or a specified point.                                                                                         |
| **Parameters**                                       | <ul><br /><li>from - An <code>hs.geometry.rect</code> or <code>hs.geometry.point</code> object; if omitted, the geometric center of this screen will be used  * strict - If <code>true</code>, disregard screens that lie completely above or below this one (alternatively, set <code>hs.screen.strictScreenInDirection</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object, or <code>nil</code> if not found</li><br /></ul>                                           |

#### [toNorth](#tonorth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:toNorth() -> hs.screen object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the first screen to the north of this one, ordered by proximity to its center or a specified point.                                                                                         |
| **Parameters**                                       | <ul><br /><li>from - An <code>hs.geometry.rect</code> or <code>hs.geometry.point</code> object; if omitted, the geometric center of this screen will be used  * strict - If <code>true</code>, disregard screens that lie completely to the left or to the right of this one (alternatively, set <code>hs.screen.strictScreenInDirection</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object, or <code>nil</code> if not found</li><br /></ul>                                           |

#### [toSouth](#tosouth)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:toSouth() -> hs.screen object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the first screen to the south of this one, ordered by proximity to its center or a specified point.                                                                                         |
| **Parameters**                                       | <ul><br /><li>from - An <code>hs.geometry.rect</code> or <code>hs.geometry.point</code> object; if omitted, the geometric center of this screen will be used  * strict - If <code>true</code>, disregard screens that lie completely to the left or to the right of this one (alternatively, set <code>hs.screen.strictScreenInDirection</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object, or <code>nil</code> if not found</li><br /></ul>                                           |

#### [toUnitRect](#tounitrect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:toUnitRect(rect) -> hs.geometry unitrect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the unit rect of a given rect, relative to this screen                                                                                         |
| **Parameters**                                       | <ul><br /><li>rect - an hs.geometry rect, or arguments to construct one</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an hs.geometry unit rect describing the given rect relative to this screen's frame</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>this method is just a convenience wrapper for <code>hs.geometry.toUnitRect(rect,this_screen:frame())</code></li><br /></ul>                                             |

#### [toWest](#towest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.screen:toWest() -> hs.screen object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the first screen to the west of this one, ordered by proximity to its center or a specified point.                                                                                         |
| **Parameters**                                       | <ul><br /><li>from - An <code>hs.geometry.rect</code> or <code>hs.geometry.point</code> object; if omitted, the geometric center of this screen will be used  * strict - If <code>true</code>, disregard screens that lie completely above or below this one (alternatively, set <code>hs.screen.strictScreenInDirection</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.screen</code> object, or <code>nil</code> if not found</li><br /></ul>                                           |

