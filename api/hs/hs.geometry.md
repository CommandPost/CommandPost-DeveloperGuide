# [docs](index.md) » hs.geometry
---

Utility object to represent points, sizes and rects in a bidimensional plane

An hs.geometry object can be:
 * a *point*, or vector2, with `x` and `y` fields for its coordinates
 * a *size* with `w` and `h` fields for width and height respectively
 * a *rect*, which has both a point component for one of its corners, and a size component - so it has all 4 fields
 * a *unit rect*, which is a rect with all fields between 0 and 1; it represents a "relative" rect within another (absolute) rect
   (e.g. a unit rect `x=0,y=0 , w=0.5,h=0.5` is the quarter portion closest to the origin); please note that hs.geometry
   makes no distinction internally between regular rects and unit rects; you can convert to and from as needed via the appropriate methods

You can create these objects in many different ways, via `my_obj=hs.geometry.new(...)` or simply `my_obj=hs.geometry(...)`
by passing any of the following:
 * 4 parameters `X,Y,W,H` for the respective fields - W and H, or X and Y, can be `nil`:
   * `hs.geometry(X,Y)` creates a point
   * `hs.geometry(nil,nil,W,H)` creates a size
   * `hs.geometry(X,Y,W,H)` creates a rect given its width and height from a corner
 * a table `{X,Y}` creates a point
 * a table `{X,Y,W,H}` creates a rect
 * a table `{x=X,y=Y,w=W,h=H}` creates a rect, or if you omit X and Y, or W and H, creates a size or a point respectively
 * a table `{x1=X1,y1=Y1,x2=X2,y2=Y2}` creates a rect, where X1,Y1 and X2,Y2 are the coordinates of opposite corners
 * a string:
   * `"X Y"` or `"X,Y"` creates a point
   * `"WxH"` or `"W*H"` creates a size
   * `"X Y/WxH"` or `"X,Y W*H"` (or variations thereof) creates a rect given its width and height from a corner
   * `"X1,Y1>X2,Y2"` or `"X1 Y1 X2 Y2"` (or variations thereof) creates a rect given two opposite corners
   * `"[X,Y WxH]"` or `"[X1,Y1 X2,Y2]"` or variations (note the square brackets) creates a unit rect where x=X/100, y=Y/100, w=W/100, h=H/100
 * a point and a size `"X Y","WxH"` or `{x=X,y=Y},{w=W,h=H}` create a rect

You can use any of these anywhere an hs.geometry object is expected in Hammerspoon; the constructor will be called for you.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [copy](#copy)
 * [new](#new)
 * [point](#point)
 * [rect](#rect)
 * [size](#size)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [area](#area)
 * [aspect](#aspect)
 * [bottomright](#bottomright)
 * [center](#center)
 * [h](#h)
 * [length](#length)
 * [string](#string)
 * [table](#table)
 * [topleft](#topleft)
 * [w](#w)
 * [wh](#wh)
 * [x](#x)
 * [x1](#x1)
 * [x2](#x2)
 * [x2y2](#x2y2)
 * [xy](#xy)
 * [y](#y)
 * [y1](#y1)
 * [y2](#y2)
* Methods - API calls which can only be made on an object returned by a constructor
 * [angle](#angle)
 * [angleTo](#angleto)
 * [distance](#distance)
 * [equals](#equals)
 * [fit](#fit)
 * [floor](#floor)
 * [fromUnitRect](#fromunitrect)
 * [inside](#inside)
 * [intersect](#intersect)
 * [move](#move)
 * [normalize](#normalize)
 * [rotateCCW](#rotateccw)
 * [scale](#scale)
 * [toUnitRect](#tounitrect)
 * [type](#type)
 * [union](#union)
 * [vector](#vector)

## API Documentation

### Constructors

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.copy(geom) -> hs.geometry object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a copy of an hs.geometry object |
| **Parameters**                                       | <ul><li>geom - an hs.geometry object to copy</li></ul> |
| **Returns**                                          | <ul><li>a newly created copy of the hs.geometry object</li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.new(...) -> hs.geometry object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new hs.geometry object |
| **Parameters**                                       | <ul><li>... - see the module description at the top</li></ul> |
| **Returns**                                          | <ul><li>a newly created hs.geometry object</li></ul> |

#### [point](#point)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.point(x, y) -> hs.geometry point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Convenience function for creating a point object |
| **Parameters**                                       | <ul><li>x - A number containing the horizontal co-ordinate of the point</li><li>y - A number containing the vertical co-ordinate of the point</li></ul> |
| **Returns**                                          | <ul><li>An hs.geometry point object</li></ul> |

#### [rect](#rect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.rect(x, y, w, h) -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Convenience function for creating a rect-table |
| **Parameters**                                       | <ul><li>x - A number containing the horizontal co-ordinate of the top-left point of the rect</li><li>y - A number containing the vertical co-ordinate of the top-left point of the rect</li><li>w - A number containing the width of the rect</li><li>h - A number containing the height of the rect</li></ul> |
| **Returns**                                          | <ul><li>An hs.geometry rect object</li></ul> |

#### [size](#size)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.size(w, h) -> hs.geometry size` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Convenience function for creating a size object |
| **Parameters**                                       | <ul><li>w - A number containing a width</li><li>h - A number containing a height</li></ul> |
| **Returns**                                          | <ul><li>An hs.geometry size object</li></ul> |

### Fields

#### [area](#area)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.area` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A number representing the area of this rect or size; changing it will scale the rect/size - see `hs.geometry:scale()` |

#### [aspect](#aspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.aspect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A number representing the aspect ratio of this rect or size; changing it will reshape the rect/size, keeping its area and center constant |

#### [bottomright](#bottomright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.bottomright` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Alias for `x2y2` |

#### [center](#center)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.center` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A point representing the geometric center of this rect or the midpoint of this vector2; changing it will move the rect/vector accordingly |

#### [h](#h)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.h` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The height of this rect or size; changing it will keep the rect's x,y corner constant |

#### [length](#length)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.length` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A number representing the length of the diagonal of this rect, or the length of this vector2; changing it will scale the rect/vector - see `hs.geometry:scale()` |

#### [string](#string)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `"X,Y/WxH"` string for this hs.geometry object (*reduced precision*); useful e.g. for logging |

#### [table](#table)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `{x=X,y=Y,w=W,h=H}` table for this hs.geometry object; useful e.g. for serialization/deserialization |

#### [topleft](#topleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.topleft` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Alias for `xy` |

#### [w](#w)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.w` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The width of this rect or size; changing it will keep the rect's x,y corner constant |

#### [wh](#wh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.wh` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The size component for this hs.geometry object; setting this to a new size will keep the rect's x,y corner constant |

#### [x](#x)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.x` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The x coordinate for this point or rect's corner; changing it will move the rect but keep the same width and height |

#### [x1](#x1)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.x1` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Alias for `x` |

#### [x2](#x2)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.x2` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The x coordinate for the second corner of this rect; changing it will affect the rect's width |

#### [x2y2](#x2y2)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.x2y2` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The point denoting the other corner of this hs.geometry object; setting this to a new point will change the rect's width and height |

#### [xy](#xy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.xy` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The point component for this hs.geometry object; setting this to a new point will move the rect but keep the same width and height |

#### [y](#y)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.y` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The y coordinate for this point or rect's corner; changing it will move the rect but keep the same width and height |

#### [y1](#y1)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.y1` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Alias for `y` |

#### [y2](#y2)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry.y2` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The y coordinate for the second corner of this rect; changing it will affect the rect's height |

### Methods

#### [angle](#angle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:angle() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the angle between the positive x axis and this vector2 |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a number represeting the angle in radians</li></ul> |

#### [angleTo](#angleto)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:angleTo(point) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the angle between the positive x axis and the vector connecting this point or rect's center to another point or rect's center |
| **Parameters**                                       | <ul><li>point - an hs.geometry object, or a table or string or parameter list to construct one; if a rect, uses the rect's center</li></ul> |
| **Returns**                                          | <ul><li>a number represeting the angle in radians</li></ul> |

#### [distance](#distance)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:distance(point) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the distance between this point or rect's center and another point or rect's center |
| **Parameters**                                       | <ul><li>point - an hs.geometry object, or a table or string or parameter list to construct one; if a rect, uses the rect's center</li></ul> |
| **Returns**                                          | <ul><li>a number indicating the distance</li></ul> |

#### [equals](#equals)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:equals(other) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if two geometry objects are equal |
| **Parameters**                                       | <ul><li>other - another hs.geometry object, or a table or string or parameter list to construct one</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if this hs.geometry object perfectly overlaps other, <code>false</code> otherwise</li></ul> |

#### [fit](#fit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:fit(bounds) -> hs.geometry object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensure this rect is fully inside `bounds`, by scaling it down if it's larger (preserving its aspect ratio) and moving it if necessary |
| **Parameters**                                       | <ul><li>bounds - an hs.geometry rect object, or a table or string or parameter list to construct one, indicating the rect that   must fully contain this rect</li></ul> |
| **Returns**                                          | <ul><li>this hs.geometry object for method chaining</li></ul> |

#### [floor](#floor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:floor() -> hs.geometry object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Truncates all coordinates in this object to integers |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>this hs.geometry point for method chaining</li></ul> |

#### [fromUnitRect](#fromunitrect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:fromUnitRect(frame) -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Converts a unit rect within a given frame into a rect |
| **Parameters**                                       | <ul><li>frame - an hs.geometry rect (with <code>w</code> and <code>h</code> &gt;0)</li></ul> |
| **Returns**                                          | <ul><li>An hs.geometry rect object</li></ul> |

#### [inside](#inside)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:inside(rect) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if this hs.geometry object lies fully inside a given rect |
| **Parameters**                                       | <ul><li>rect - an hs.geometry rect, or a table or string or parameter list to construct one</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if this point/rect lies fully inside the given rect, <code>false</code> otherwise</li></ul> |

#### [intersect](#intersect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:intersect(rect) -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the intersection rect between this rect and another rect |
| **Parameters**                                       | <ul><li>rect - an hs.geometry rect, or a table or string or parameter list to construct one</li></ul> |
| **Returns**                                          | <ul><li>a new hs.geometry rect</li></ul> |
| **Notes**                                            | <ul><li>If the two rects don't intersect, the result rect will be a "projection" of the second rect onto this rect's   closest edge or corner along the x or y axis; the <code>w</code> and/or <code>h</code> fields in the result rect will be 0.</li></ul> |

#### [move](#move)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:move(point) -> hs.geometry object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Moves this point/rect |
| **Parameters**                                       | <ul><li>point - an hs.geometry object, or a table or string or parameter list to construct one, indicating the x and y displacement to apply</li></ul> |
| **Returns**                                          | <ul><li>this hs.geometry object for method chaining</li></ul> |

#### [normalize](#normalize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:normalize() -> point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Normalizes this vector2 |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>this hs.geometry point for method chaining</li></ul> |

#### [rotateCCW](#rotateccw)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:rotateCCW(aroundpoint, ntimes) -> hs.geometry point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Rotates a point around another point N times |
| **Parameters**                                       | <ul><li>aroundpoint - an hs.geometry point to rotate this point around</li><li>ntimes - the number of times to rotate, defaults to 1</li></ul> |
| **Returns**                                          | <ul><li>A new hs.geometry point containing the location of the rotated point</li></ul> |

#### [scale](#scale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:scale(size) -> hs.geometry object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Scales this vector2/size, or this rect *keeping its center constant* |
| **Parameters**                                       | <ul><li>size - an hs.geometry object, or a table or string or parameter list to construct one, indicating the factors for scaling this rect's width and height;   if a number, the rect will be scaled by the same factor in both axes</li></ul> |
| **Returns**                                          | <ul><li>this hs.geometry object for method chaining</li></ul> |

#### [toUnitRect](#tounitrect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:toUnitRect(frame) -> hs.geometry unit rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Converts a rect into its unit rect within a given frame |
| **Parameters**                                       | <ul><li>frame - an hs.geometry rect (with <code>w</code> and <code>h</code> &gt;0)</li></ul> |
| **Returns**                                          | <ul><li>An hs.geometry unit rect object</li></ul> |
| **Notes**                                            | <ul><li>The resulting unit rect is always clipped within <code>frame</code>'s bounds (via <code>hs.geometry:intersect()</code>); if <code>frame</code>   does not encompass this rect <em>no error will be thrown</em>, but the resulting unit rect won't be a direct match with this rect   (i.e. calling <code>:fromUnitRect(frame)</code> on it will return a different rect)</li></ul> |

#### [type](#type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:type() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the type of an hs.geometry object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string describing the type of this hs.geometry object, i.e. 'point', 'size', 'rect' or 'unitrect'; <code>nil</code> if not a valid object</li></ul> |

#### [union](#union)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:union(rect) -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the smallest rect that encloses both this rect and another rect |
| **Parameters**                                       | <ul><li>rect - an hs.geometry rect, or a table or string or parameter list to construct one</li></ul> |
| **Returns**                                          | <ul><li>a new hs.geometry rect</li></ul> |

#### [vector](#vector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.geometry:vector(point) -> point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the vector2 from this point or rect's center to another point or rect's center |
| **Parameters**                                       | <ul><li>point - an hs.geometry object, or a table or string or parameter list to construct one; if a rect, uses the rect's center</li></ul> |
| **Returns**                                          | <ul><li>an hs.geometry point</li></ul> |

