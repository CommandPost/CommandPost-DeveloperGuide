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
| **Parameters**                                       | <ul><br /><li>value - An RGB table with the selected colour (see <code>hs.drawing.color</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [deleteHighlight](#deletehighlight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.deleteHighlight() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Delete's the highlight if it's currently visible on the screen.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [getHighlightColor](#gethighlightcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.getHighlightColor() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current highlight colour.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An RGB table with the selected colour (see <code>hs.drawing.color</code>) or <code>nil</code></li><br /></ul>                                           |

#### [getHighlightCustomColor](#gethighlightcustomcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.getHighlightCustomColor() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current custom highlight colour.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An RGB table with the selected colour (see <code>hs.drawing.color</code>) or <code>nil</code></li><br /></ul>                                           |

#### [getHighlightShape](#gethighlightshape)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.getHighlightShape() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current highlight shape.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>"Rectangle", "Circle" or "Diamond" or <code>nil</code>.</li><br /></ul>                                           |

#### [getHighlightTime](#gethighlighttime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.getHighlightTime() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current highlight playhead time.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A number or <code>nil</code></li><br /></ul>                                           |

#### [highlight](#highlight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.highlight() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Highlight's the Final Cut Pro Browser Playhead.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [highlightFrame](#highlightframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.highlightFrame([frame]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Highlights a specific frame.                                                                                         |
| **Parameters**                                       | <ul><br /><li>frame - Frame as per <code>hs.geometry.rect</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [setHighlightColor](#sethighlightcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.setHighlightColor([value]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Playhead Highlight Colour.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value - An RGB table with the selected colour (see <code>hs.drawing.color</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [setHighlightCustomColor](#sethighlightcustomcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.setHighlightCustomColor([value]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Custom Playhead Highlight Colour.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value - An RGB table with the selected colour (see <code>hs.drawing.color</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [setHighlightShape](#sethighlightshape)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.setHighlightShape([value]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Custom Playhead Highlight Shape.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value - A string which can be "Rectangle", "Circle" or "Diamond".</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [setHighlightTime](#sethighlighttime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.playhead.setHighlightTime([value]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Custom Playhead Highlight Time.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value - A number</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

