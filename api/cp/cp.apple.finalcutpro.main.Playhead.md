# [docs](index.md) » cp.apple.finalcutpro.main.Playhead
---

Playhead Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [find](#find)
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [center](#center)
 * [currentViewer](#currentviewer)
 * [frame](#frame)
 * [isPersistent](#ispersistent)
 * [isShowing](#isshowing)
 * [position](#position)
 * [timecode](#timecode)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [hide](#hide)
 * [parent](#parent)
 * [show](#show)

## API Documentation

### Functions

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.find(containerUI, skimming) -> hs._asm.axuielement object | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Finds the playhead (either persistent or skimming) in the specified container. Defaults to persistent.                                                                                         |
| **Parameters**                                       | <ul><li>`containerUI` - The container UI</li><li>`skimming` - Whether or not you want the skimming playhead as boolean.</li></ul> |
| **Returns**                                          | <ul><li>The playhead `hs._asm.axuielement` object or `nil` if not found.</li></ul>          |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if a GUI element is the Playhead or not                                                                                         |
| **Parameters**                                       | <ul><li>`element`    - The element you want to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if the `element` is the Playhead otherwise `false`</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.new(parent[, skimming[, containerFn[, useEventViewer]]]) -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new Playhead                                                                                         |
| **Parameters**                                       | <ul><li>parent        - The parent object</li><li>skimming      - (optional) if `true`, this links to the 'skimming' playhead created under the mouse, if present.</li><li>containerUI   - (optional) a `cp.prop` which returns the container axuielement which contains the playheads. If not present, it will use the parent's UI element.</li><li>useEventViewer - (optional) if `true`, this will use the Event Viewer's timecode, when available.</li></ul> |
| **Returns**                                          | <ul><li>The new `Playhead` instance.</li></ul>          |

### Fields

#### [center](#center)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.center <cp.prop: hs.geometry.point; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Gets the centre point (`{x, y}`) of the playhead.                                                                                         |

#### [currentViewer](#currentviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.currentViewer <cp.prop: cp.apple.finalcutpro.main.Viewer; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Represents the current viewer for the playhead. This may be either the primary Viewer or the Event Viewer,                                                                                         |

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.frame <cp.prop: hs.geometry.frame; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Gets the frame of the playhead.                                                                                         |

#### [isPersistent](#ispersistent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.isPersistent <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the playhead persistent?                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.isShowing <cp.prop: boolean; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the playhead showing?                                                                                         |

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.position <cp.prop; number; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Gets the horizontal position of the playhead line, which may be different to the `x` position of the playhead.                                                                                         |

#### [timecode](#timecode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.timecode <cp.prop: string; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Gets and sets the current timecode.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.UI <cp.prop: hs._asm.axuielement; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Playhead                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:hide() -> Playhead object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Playhead                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Playhead object</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Playhead's parent table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:show() -> Playhead object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Playhead                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Playhead object</li></ul>          |

