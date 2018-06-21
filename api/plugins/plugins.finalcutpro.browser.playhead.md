# [docs](index.md) » plugins.finalcutpro.browser.playhead
---

Browser Playhead Plugin.

## API Overview
* Functions - API calls offered directly by the extension
 * [changeHighlightColor](#changehighlightcolor)
 * [deleteHighlight](#deletehighlight)
 * [getHighlightColor](#gethighlightcolor)
 * [getHighlightCustomColor](#gethighlightcustomcolor)
 * [getHighlightShape](#gethighlightshape)
 * [getHighlightTime](#gethighlighttime)
 * [highlight](#highlight)
 * [highlightFrame](#highlightframe)
 * [setHighlightColor](#sethighlightcolor)
 * [setHighlightCustomColor](#sethighlightcustomcolor)
 * [setHighlightShape](#sethighlightshape)
 * [setHighlightTime](#sethighlighttime)

## API Documentation

### Functions

#### [changeHighlightColor](#changehighlightcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.changeHighlightColor([value]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Prompts the user to change the Playhead Highlight Colour.                                                                                         |
| **Parameters**                                       |  * value - An RGB table with the selected colour (see `hs.drawing.color`)                                       |
| **Returns**                                          |  * None                                                |

#### [deleteHighlight](#deletehighlight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.deleteHighlight() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Delete's the highlight if it's currently visible on the screen.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [getHighlightColor](#gethighlightcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.getHighlightColor() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current highlight colour.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An RGB table with the selected colour (see `hs.drawing.color`) or `nil`                                                |

#### [getHighlightCustomColor](#gethighlightcustomcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.getHighlightCustomColor() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current custom highlight colour.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An RGB table with the selected colour (see `hs.drawing.color`) or `nil`                                                |

#### [getHighlightShape](#gethighlightshape)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.getHighlightShape() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current highlight shape.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * "Rectangle", "Circle" or "Diamond" or `nil`.                                                |

#### [getHighlightTime](#gethighlighttime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.getHighlightTime() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current highlight playhead time.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A number or `nil`                                                |

#### [highlight](#highlight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.highlight() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Highlight's the Final Cut Pro Browser Playhead.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [highlightFrame](#highlightframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.highlightFrame([frame]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Highlights a specific frame.                                                                                         |
| **Parameters**                                       |  * frame - Frame as per `hs.geometry.rect`                                       |
| **Returns**                                          |  * None                                                |

#### [setHighlightColor](#sethighlightcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.setHighlightColor([value]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Playhead Highlight Colour.                                                                                         |
| **Parameters**                                       |  * value - An RGB table with the selected colour (see `hs.drawing.color`)                                       |
| **Returns**                                          |  * None                                                |

#### [setHighlightCustomColor](#sethighlightcustomcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.setHighlightCustomColor([value]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Custom Playhead Highlight Colour.                                                                                         |
| **Parameters**                                       |  * value - An RGB table with the selected colour (see `hs.drawing.color`)                                       |
| **Returns**                                          |  * None                                                |

#### [setHighlightShape](#sethighlightshape)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.setHighlightShape([value]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Custom Playhead Highlight Shape.                                                                                         |
| **Parameters**                                       |  * value - A string which can be "Rectangle", "Circle" or "Diamond".                                       |
| **Returns**                                          |  * None                                                |

#### [setHighlightTime](#sethighlighttime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.setHighlightTime([value]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Custom Playhead Highlight Time.                                                                                         |
| **Parameters**                                       |  * value - A number                                       |
| **Returns**                                          |  * None                                                |

