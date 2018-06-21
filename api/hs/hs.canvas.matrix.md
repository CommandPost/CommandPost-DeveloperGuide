# [docs](index.md) » hs.canvas.matrix
---

A sub module to `hs.canvas` which provides support for basic matrix manipulations which can be used as the values for `transformation` attributes in the `hs.canvas` module.

For mathematical reasons that are beyond the scope of this document, a 3x3 matrix can be used to represent a series of manipulations to be applied to the coordinates of a 2 dimensional drawing object.  These manipulations can include one or more of a combination of translations, rotations, shearing and scaling. Within the 3x3 matrix, only 6 numbers are actually required, and this module represents them as the following keys in a Lua table: `m11`, `m12`, `m21`, `m22`, `tX`, and `tY`. For those of a mathematical bent, the 3x3 matrix used within this module can be visualized as follows:

    [  m11,  m12,  0  ]
    [  m21,  m22,  0  ]
    [  tX,   tY,   1  ]

This module allows you to generate the table which can represent one or more of the recognized transformations without having to understand the math behind the manipulations or specify the matrix values directly.

Many of the methods defined in this module can be used both as constructors and as methods chained to a previous method or constructor. Chaining the methods in this manner allows you to combine multiple transformations into one combined table which can then be assigned to an element in your canvas.
.

For more information on the mathematics behind these, you can check the web.  One site I used for reference (but there are many more which go into much more detail) can be found at http://www.cs.trinity.edu/~jhowland/cs2322/2d/2d/.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [identity](#identity)
* Methods - API calls which can only be made on an object returned by a constructor
 * [append](#append)
 * [invert](#invert)
 * [prepend](#prepend)
 * [rotate](#rotate)
 * [scale](#scale)
 * [shear](#shear)
 * [translate](#translate)

## API Documentation

### Constructors

#### [identity](#identity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.canvas.matrix.identity() -> matrixObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Specifies the identity matrix.  Resets all existing transformations when applied as a method to an existing matrixObject.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the identity matrix.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The identity matrix can be thought of as "apply no transformations at all" or "render as specified".</li><li markdown="1">Mathematically this is represented as:</li><li markdown="1">~~~</li><li markdown="1">[ 1,  0,  0 ]</li><li markdown="1">[ 0,  1,  0 ]</li><li markdown="1">[ 0,  0,  1 ]</li><li markdown="1">~~~</li></ul>                |

### Methods

#### [append](#append)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.canvas.matrix:append(matrix) -> matrixObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Appends the specified matrix transformations to the matrix and returns the new matrix.  This method cannot be used as a constructor.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`matrix` - the table to append to the current matrix.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the new matrix</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Mathematically this method multiples the original matrix by the new one and returns the result of the multiplication.</li><li markdown="1">You can use this method to "stack" additional transformations on top of existing transformations, without having to know what the existing transformations in effect for the canvas element are.</li></ul>                |

#### [invert](#invert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.canvas.matrix:invert() -> matrixObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Generates the mathematical inverse of the matrix.  This method cannot be used as a constructor.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the inverted matrix.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Inverting a matrix which represents a series of transformations has the effect of reversing or undoing the original transformations.</li><li markdown="1">This is useful when used with [hs.canvas.matrix.append](#append) to undo a previously applied transformation without actually replacing all of the transformations which may have been applied to a canvas element.</li></ul>                |

#### [prepend](#prepend)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.canvas.matrix:prepend(matrix) -> matrixObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Prepends the specified matrix transformations to the matrix and returns the new matrix.  This method cannot be used as a constructor.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`matrix` - the table to append to the current matrix.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the new matrix</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Mathematically this method multiples the new matrix by the original one and returns the result of the multiplication.</li><li markdown="1">You can use this method to apply a transformation *before* the currently applied transformations, without having to know what the existing transformations in effect for the canvas element are.</li></ul>                |

#### [rotate](#rotate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.canvas.matrix:rotate(angle) -> matrixObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies a rotation of the specified number of degrees to the transformation matrix.  This method can be used as a constructor or a method.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`angle` - the number of degrees to rotate in a clockwise direction.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the new matrix</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The rotation of an element this matrix is applied to will be rotated about the origin (zero point).  To rotate an object about another point (its center for example), prepend a translation to the point to rotate about, and append a translation reversing the initial translation.</li><li markdown="1">  e.g. `hs.canvas.matrix.translate(x, y):rotate(angle):translate(-x, -y)`</li></ul>                |

#### [scale](#scale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.canvas.matrix:scale(xFactor, [yFactor]) -> matrixObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies a scaling transformation to the matrix.  This method can be used as a constructor or a method.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`xFactor` - the scaling factor to apply to the object in the horizontal orientation.</li><li markdown="1">`yFactor` - an optional argument specifying a different scaling factor in the vertical orientation.  If this argument is not provided, the `xFactor` argument will be used for both orientations.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the new matrix</li></ul>          |

#### [shear](#shear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.canvas.matrix:shear(xFactor, [yFactor]) -> matrixObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies a shearing transformation to the matrix.  This method can be used as a constructor or a method.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`xFactor` - the shearing factor to apply to the object in the horizontal orientation.</li><li markdown="1">`yFactor` - an optional argument specifying a different shearing factor in the vertical orientation.  If this argument is not provided, the `xFactor` argument will be used for both orientations.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the new matrix</li></ul>          |

#### [translate](#translate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.canvas.matrix:translate(x, y) -> matrixObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies a translation transformation to the matrix.  This method can be used as a constructor or a method.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`x` - the distance to translate the object in the horizontal direction.</li><li markdown="1">`y` - the distance to translate the object in the vertical direction.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the new matrix</li></ul>          |

