# [docs](index.md) » hs.drawing.color
---

Provides ccess to the system color lists and a wider variety of ways to represent color within Hammerspoon.

Color is represented within Hammerspoon as a table containing keys which tell Hammerspoon how the color is specified.  You can specify a color in one of the following ways, depending upon the keys you supply within the table:

* As a combination of Red, Green, and Blue elements (RGB Color):
  * red   - the red component of the color specified as a number from 0.0 to 1.0.
  * green - the green component of the color specified as a number from 0.0 to 1.0.
  * blue  - the blue component of the color specified as a number from 0.0 to 1.0.
  * alpha - the color transparency from 0.0 (completely transparent) to 1.0 (completely opaque)

* As a combination of Hue, Saturation, and Brightness (HSB or HSV Color):
  * hue        - the hue component of the color specified as a number from 0.0 to 1.0.
  * saturation - the saturation component of the color specified as a number from 0.0 to 1.0.
  * brightness - the brightness component of the color specified as a number from 0.0 to 1.0.
  * alpha      - the color transparency from 0.0 (completely transparent) to 1.0 (completely opaque)

* As grayscale (Grayscale Color):
  * white - the ratio of white to black from 0.0 (completely black) to 1.0 (completely white)
  * alpha - the color transparency from 0.0 (completely transparent) to 1.0 (completely opaque)

* From the system or Hammerspoon color lists:
  * list - the name of a system color list or a collection list defined in `hs.drawing.color`
  * name - the color name within the specified color list

* As an HTML style hex color specification:
  * hex   - a string of the format "#rrggbb" or "#rgb" where `r`, `g`, and `b` are hexadecimal digits (i.e. 0-9, A-F)
  * alpha - the color transparency from 0.0 (completely transparent) to 1.0 (completely opaque)

* From an image to be used as a tiled pattern:
  * image - an `hs.image` object representing the image to be used as a tiled pattern

Any combination of the above keys may be specified within the color table and they will be evaluated in the following order:
  1. if the `image` key is specified, it will be used to create a tiling pattern.
  2. If the `list` and `name` keys are specified, and if they can be matched to an existing color within the system color lists, that color is used.
  3. If the `hue` key is provided, then the color is generated as an HSB color
  4. If the `white` key is provided, then the color is generated as a Grayscale color
  5. Otherwise, an RGB color is generated.

Except where specified above to indicate the color model being used, any key which is not provided defaults to a value of 0.0, except for `alpha`, which defaults to 1.0.  This means that specifying an empty table as the color will result in an opaque black color.

## API Overview
* Constants - Useful values which cannot be changed
 * [definedCollections](#definedcollections)
* Variables - Configurable values
 * [ansiTerminalColors](#ansiterminalcolors)
 * [hammerspoon](#hammerspoon)
 * [x11](#x11)
* Functions - API calls offered directly by the extension
 * [asHSB](#ashsb)
 * [asRGB](#asrgb)
 * [colorsFor](#colorsfor)
 * [lists](#lists)

## API Documentation

### Constants

#### [definedCollections](#definedcollections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.drawing.color.definedCollections` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | This table contains this list of defined color collections provided by the `hs.drawing.color` module.  Collections differ from the system color lists in that you can modify the color values their members contain by modifying the table at `hs.drawing.color.<collection>.<color>` and future references to that color will reflect the new changes, thus allowing you to customize the palettes for your installation. |
| **Notes**                                            | <ul><li>This list is a constant, but the members it refers to are not.</li></ul> |

### Variables

#### [ansiTerminalColors](#ansiterminalcolors)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.drawing.color.ansiTerminalColors` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A collection of colors representing the ANSI Terminal color sequences.  The color definitions are based upon code found at https://github.com/balthamos/geektool-3 in the /NerdTool/classes/ANSIEscapeHelper.m file. |
| **Notes**                                            | <ul><li>This is not a constant, so you can adjust the colors at run time for your installation if desired.</li></ul> |

#### [hammerspoon](#hammerspoon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.drawing.color.hammerspoon` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | This table contains a collection of various useful pre-defined colors: |
| **Notes**                                            | <ul><li>This is not a constant, so you can adjust the colors at run time for your installation if desired.</li></ul> |

#### [x11](#x11)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.drawing.color.x11` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A collection of colors representing the X11 color names as defined at  https://en.wikipedia.org/wiki/Web_colors#X11_color_names (names in lowercase) |
| **Notes**                                            | <ul><li>This is not a constant, so you can adjust the colors at run time for your installation if desired.</li></ul> |

### Functions

#### [asHSB](#ashsb)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.drawing.color.asHSB(color) -> table | string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the HSB representation of the specified color. |
| **Parameters**                                       | <ul><li>color - a table specifying a color as described in the module definition (see <code>hs.drawing.color</code> in the online help or Dash documentation)</li></ul> |
| **Returns**                                          | <ul><li>a table containing the hue, saturation, brightness, and alpha keys representing the specified color as HSB or a string describing the color's colorspace if conversion is not possible.</li></ul> |
| **Notes**                                            | <ul><li>See also <code>hs.drawing.color.asRGB</code></li></ul> |

#### [asRGB](#asrgb)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.drawing.color.asRGB(color) -> table | string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the RGB representation of the specified color. |
| **Parameters**                                       | <ul><li>color - a table specifying a color as described in the module definition (see <code>hs.drawing.color</code> in the online help or Dash documentation)</li></ul> |
| **Returns**                                          | <ul><li>a table containing the red, blue, green, and alpha keys representing the specified color as RGB or a string describing the color's colorspace if conversion is not possible.</li></ul> |
| **Notes**                                            | <ul><li>See also <code>hs.drawing.color.asHSB</code></li></ul> |

#### [colorsFor](#colorsfor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.drawing.color.colorsFor(list) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the colors for the specified system color list or hs.drawing.color collection. |
| **Parameters**                                       | <ul><li>list - the name of the list to provide colors for</li></ul> |
| **Returns**                                          | <ul><li>a table whose keys are made from the colors provided by the color list or nil if the list does not exist.</li></ul> |
| **Notes**                                            | <ul><li>Where possible, each color node is provided as its RGB color representation.  Where this is not possible, the color node contains the keys <code>list</code> and <code>name</code> which identify the indicated color.  This means that you can use the following wherever a color parameter is expected: <code>hs.drawing.color.colorsFor(list)["color-name"]</code></li><li>This function provides a tostring metatable method which allows listing the defined colors in the list in the Hammerspoon console with: <code>hs.drawing.colorsFor(list)</code></li><li>See also <code>hs.drawing.color.lists</code></li></ul> |

#### [lists](#lists)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.drawing.color.lists() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the system color lists and hs.drawing.color collections with their defined colors. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table whose keys are made from the currently defined system color lists and hs.drawing.color collections.  Each color list key refers to a table whose keys make up the colors provided by the specific color list.</li></ul> |
| **Notes**                                            | <ul><li>Where possible, each color node is provided as its RGB color representation.  Where this is not possible, the color node contains the keys <code>list</code> and <code>name</code> which identify the indicated color.  This means that you can use the following wherever a color parameter is expected: <code>hs.drawing.color.lists()["list-name"]["color-name"]</code></li><li>This function provides a tostring metatable method which allows listing the defined color lists in the Hammerspoon console with: <code>hs.drawing.color.lists()</code></li><li>See also <code>hs.drawing.color.colorsFor</code></li></ul> |

