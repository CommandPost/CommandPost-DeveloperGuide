# [docs](index.md) » plugins.finalcutpro.viewer.overlays
---

Final Cut Pro Viewer Overlays.

## API Overview
* Variables - Configurable values
 * [activeMemory](#activememory)
 * [basicGridEnabled](#basicgridenabled)
 * [customGridColor](#customgridcolor)
 * [disabled](#disabled)
 * [draggableGuideEnabled](#draggableguideenabled)
 * [gridAlpha](#gridalpha)
 * [gridColor](#gridcolor)
 * [gridSpacing](#gridspacing)
 * [guidePosition](#guideposition)
 * [stillsLayout](#stillslayout)
* Functions - API calls offered directly by the extension
 * [getMemory](#getmemory)
 * [getStillsFolderPath](#getstillsfolderpath)
 * [getViewerUI](#getviewerui)
 * [hide](#hide)
 * [saveMemory](#savememory)
 * [setCustomGridColor](#setcustomgridcolor)
 * [setGridAlpha](#setgridalpha)
 * [setGridColor](#setgridcolor)
 * [setGridSpacing](#setgridspacing)
 * [show](#show)
 * [update](#update)
 * [viewMemory](#viewmemory)

## API Documentation

### Variables

#### [activeMemory](#activememory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.activeMemory <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Viewer Custom Grid Color as HTML value                                                                                         |

#### [basicGridEnabled](#basicgridenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.basicGridEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is Viewer Grid Enabled?                                                                                         |

#### [customGridColor](#customgridcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.customGridColor <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Viewer Custom Grid Color as HTML value                                                                                         |

#### [disabled](#disabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.disabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Are all the Viewer Overlay's disabled?                                                                                         |

#### [draggableGuideEnabled](#draggableguideenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.draggableGuideEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is Viewer Grid Enabled?                                                                                         |

#### [gridAlpha](#gridalpha)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.gridAlpha <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Viewer Grid Alpha                                                                                         |

#### [gridColor](#gridcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.gridColor <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Viewer Grid Color as HTML value                                                                                         |

#### [gridSpacing](#gridspacing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.gridSpacing <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Viewer Custom Grid Color as HTML value                                                                                         |

#### [guidePosition](#guideposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.guidePosition <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Guide Position.                                                                                         |

#### [stillsLayout](#stillslayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.stillsLayout <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Stills layout.                                                                                         |

### Functions

#### [getMemory](#getmemory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getMemory(id) -> image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets an image from memory.                                                                                         |
| **Parameters**                                       | <ul><li>id - The ID of the memory you want to retrieve.</li></ul> |
| **Returns**                                          | <ul><li>The memory as a `hs.image` or `nil` if the memory could not be retrieved.</li></ul>          |

#### [getStillsFolderPath](#getstillsfolderpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getStillsFolderPath() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the stills folder path.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The stills folder path as a string or `nil` if an error occurs.</li></ul>          |

#### [getViewerUI](#getviewerui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getViewerUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the Viewer UI.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hides the Viewer Grid.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [saveMemory](#savememory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.saveMemory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves a still frame to file.                                                                                         |
| **Parameters**                                       | <ul><li>id - An identifier in the form of a number.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setCustomGridColor](#setcustomgridcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setCustomGridColor() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Pops up a Color Dialog box allowing the user to select a custom colour for grid lines.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setGridAlpha](#setgridalpha)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setGridAlpha(value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets Grid Alpha.                                                                                         |
| **Parameters**                                       | <ul><li>value - The value you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setGridColor](#setgridcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setGridColor(value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets Grid Color.                                                                                         |
| **Parameters**                                       | <ul><li>value - The value you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setGridSpacing](#setgridspacing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setGridSpacing(value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets Grid Spacing.                                                                                         |
| **Parameters**                                       | <ul><li>value - The value you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Show's the Viewer Grid.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Viewer Grid.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [viewMemory](#viewmemory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.viewMemory(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | View a memory.                                                                                         |
| **Parameters**                                       | <ul><li>id - The ID of the memory you want to retrieve.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
