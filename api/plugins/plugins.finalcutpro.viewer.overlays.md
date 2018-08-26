# [docs](index.md) » plugins.finalcutpro.viewer.overlays
---

Final Cut Pro Viewer Overlays.

## API Overview
* Variables - Configurable values
 * [activeMemory](#activememory)
 * [basicGridEnabled](#basicgridenabled)
 * [capslock](#capslock)
 * [crossHairAlpha](#crosshairalpha)
 * [crossHairColor](#crosshaircolor)
 * [crossHairEnabled](#crosshairenabled)
 * [customCrossHairColor](#customcrosshaircolor)
 * [customGridColor](#customgridcolor)
 * [customGuideColor](#customguidecolor)
 * [disabled](#disabled)
 * [draggableGuideEnabled](#draggableguideenabled)
 * [gridAlpha](#gridalpha)
 * [gridColor](#gridcolor)
 * [gridSpacing](#gridspacing)
 * [guideAlpha](#guidealpha)
 * [guideColor](#guidecolor)
 * [guidePosition](#guideposition)
 * [letterboxEnabled](#letterboxenabled)
 * [letterboxHeight](#letterboxheight)
 * [stillsLayout](#stillslayout)
* Functions - API calls offered directly by the extension
 * [deleteMemory](#deletememory)
 * [draggableGuidesEnabled](#draggableguidesenabled)
 * [getCustomGuideColor](#getcustomguidecolor)
 * [getDraggableGuideEnabled](#getdraggableguideenabled)
 * [getGuideAlpha](#getguidealpha)
 * [getGuideColor](#getguidecolor)
 * [getGuidePosition](#getguideposition)
 * [getMemory](#getmemory)
 * [getStillsFolderPath](#getstillsfolderpath)
 * [hide](#hide)
 * [importMemory](#importmemory)
 * [saveMemory](#savememory)
 * [setCustomCrossHairColor](#setcustomcrosshaircolor)
 * [setCustomGridColor](#setcustomgridcolor)
 * [setCustomGuideColor](#setcustomguidecolor)
 * [setGridAlpha](#setgridalpha)
 * [setGridColor](#setgridcolor)
 * [setGridSpacing](#setgridspacing)
 * [setGuideAlpha](#setguidealpha)
 * [setGuideColor](#setguidecolor)
 * [show](#show)
 * [toggleDraggableGuide](#toggledraggableguide)
 * [update](#update)
 * [viewMemory](#viewmemory)

## API Documentation

### Variables

#### [activeMemory](#activememory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.activeMemory <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Custom Grid Color as HTML value |

#### [basicGridEnabled](#basicgridenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.basicGridEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Is Viewer Grid Enabled? |

#### [capslock](#capslock)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.capslock <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Toggle Viewer Overlays with Caps Lock. |

#### [crossHairAlpha](#crosshairalpha)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.crossHairAlpha <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Grid Alpha |

#### [crossHairColor](#crosshaircolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.crossHairColor <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Grid Color as HTML value |

#### [crossHairEnabled](#crosshairenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.crossHairEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Is Viewer Cross Hair Enabled? |

#### [customCrossHairColor](#customcrosshaircolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.customCrossHairColor <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Custom Cross Hair Color as HTML value |

#### [customGridColor](#customgridcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.customGridColor <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Custom Grid Color as HTML value |

#### [customGuideColor](#customguidecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.customGuideColor <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Custom Guide Color as HTML value |

#### [disabled](#disabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.disabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Are all the Viewer Overlay's disabled? |

#### [draggableGuideEnabled](#draggableguideenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.draggableGuideEnabled <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Is Viewer Grid Enabled? |

#### [gridAlpha](#gridalpha)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.gridAlpha <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Grid Alpha |

#### [gridColor](#gridcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.gridColor <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Grid Color as HTML value |

#### [gridSpacing](#gridspacing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.gridSpacing <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Custom Grid Color as HTML value |

#### [guideAlpha](#guidealpha)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.guideAlpha <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Guide Alpha |

#### [guideColor](#guidecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.guideColor <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Viewer Guide Color as HTML value |

#### [guidePosition](#guideposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.guidePosition <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Guide Position. |

#### [letterboxEnabled](#letterboxenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.letterboxEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Is Viewer Letterbox Enabled? |

#### [letterboxHeight](#letterboxheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.letterboxHeight <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Letterbox Height |

#### [stillsLayout](#stillslayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.stillsLayout <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Stills layout. |

### Functions

#### [deleteMemory](#deletememory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.deleteMemory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Deletes a memory. |
| **Parameters**                                       | <ul><li>id - An identifier in the form of a number.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [draggableGuidesEnabled](#draggableguidesenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.draggableGuidesEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Are any draggable guides enabled? |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if at least one draggable guide is enabled otherwise <code>false</code></li></ul> |

#### [getCustomGuideColor](#getcustomguidecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getCustomGuideColor(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get Custom Guide Color. |
| **Parameters**                                       | <ul><li>id - The ID of the guide.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getDraggableGuideEnabled](#getdraggableguideenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getDraggableGuideEnabled(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get Guide Enabled. |
| **Parameters**                                       | <ul><li>id - The ID of the guide.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getGuideAlpha](#getguidealpha)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getGuideAlpha() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get Guide Alpha. |
| **Parameters**                                       | <ul><li>id - The ID of the guide.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getGuideColor](#getguidecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getGuideColor(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get Guide Color. |
| **Parameters**                                       | <ul><li>id - The ID of the guide.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getGuidePosition](#getguideposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getGuidePosition() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get Guide Position. |
| **Parameters**                                       | <ul><li>id - The ID of the guide.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getMemory](#getmemory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getMemory(id) -> image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets an image from memory. |
| **Parameters**                                       | <ul><li>id - The ID of the memory you want to retrieve.</li></ul> |
| **Returns**                                          | <ul><li>The memory as a <code>hs.image</code> or <code>nil</code> if the memory could not be retrieved.</li></ul> |

#### [getStillsFolderPath](#getstillsfolderpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.getStillsFolderPath() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the stills folder path. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The stills folder path as a string or <code>nil</code> if an error occurs.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Hides the Viewer Grid. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [importMemory](#importmemory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.importMemory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Import a file to memory. |
| **Parameters**                                       | <ul><li>id - An identifier in the form of a number.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [saveMemory](#savememory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.saveMemory() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Saves a still frame to file. |
| **Parameters**                                       | <ul><li>id - An identifier in the form of a number.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setCustomCrossHairColor](#setcustomcrosshaircolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setCustomCrossHairColor() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Pops up a Color Dialog box allowing the user to select a custom colour for cross hairs. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setCustomGridColor](#setcustomgridcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setCustomGridColor() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Pops up a Color Dialog box allowing the user to select a custom colour for grid lines. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setCustomGuideColor](#setcustomguidecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setCustomGuideColor() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Pops up a Color Dialog box allowing the user to select a custom colour for guide lines. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setGridAlpha](#setgridalpha)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setGridAlpha(value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets Grid Alpha. |
| **Parameters**                                       | <ul><li>value - The value you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setGridColor](#setgridcolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setGridColor(value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets Grid Color. |
| **Parameters**                                       | <ul><li>value - The value you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setGridSpacing](#setgridspacing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setGridSpacing(value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets Grid Spacing. |
| **Parameters**                                       | <ul><li>value - The value you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setGuideAlpha](#setguidealpha)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setGuideAlpha(value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets Guide Alpha. |
| **Parameters**                                       | <ul><li>id - The ID of the guide.</li><li>value - The value you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setGuideColor](#setguidecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.setGuideColor(value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets Guide Color. |
| **Parameters**                                       | <ul><li>id - The ID of the guide.</li><li>value - The value you want to set.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Show's the Viewer Grid. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [toggleDraggableGuide](#toggledraggableguide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.toggleDraggableGuide(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Toggle Guide Enabled. |
| **Parameters**                                       | <ul><li>id - The ID of the guide.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the Viewer Grid. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [viewMemory](#viewmemory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.viewer.overlays.viewMemory(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | View a memory. |
| **Parameters**                                       | <ul><li>id - The ID of the memory you want to retrieve.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

