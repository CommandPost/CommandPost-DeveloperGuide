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
 * [isPersistent](#ispersistent)
 * [isShowing](#isshowing)
 * [isSkimming](#isskimming)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [getCenter](#getcenter)
 * [getFrame](#getframe)
 * [getPosition](#getposition)
 * [getTimecode](#gettimecode)
 * [getX](#getx)
 * [hide](#hide)
 * [parent](#parent)
 * [setTimecode](#settimecode)
 * [show](#show)
 * [UI](#ui)

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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:new(parent, skimming, containerFn) -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new Playhead                                                                                         |
| **Parameters**                                       | <ul><li>* parent        - The parent object</li><li>* skimming      - (optional) if `true`, this links to the 'skimming' playhead created under the mouse, if present.</li><li>* containerFn   - (optional) a function which returns the container axuielement which contains the playheads. If not present, it will use the parent's UI element.</li></ul> |
| **Returns**                                          | <ul><li>* The new `Playhead` instance.</li></ul>          |

### Fields

#### [isPersistent](#ispersistent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.isPersistent <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the playhead persistent?                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.isShowing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the playhead showing?                                                                                         |

#### [isSkimming](#isskimming)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead.isSkimming <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the playhead skimming?                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The application object as a table</li></ul>          |

#### [getCenter](#getcenter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:getCenter() -> hs.geometry.point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the centre of the playhead.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The playhead centre position as a `hs.geometry.point`.</li></ul>          |

#### [getFrame](#getframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:getFrame() -> hs.geometry.frame` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the frame of the playhead.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The playhead frame.</li></ul>          |

#### [getPosition](#getposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:getPosition() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the position of the playhead.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The playhead position as a number.</li></ul>          |

#### [getTimecode](#gettimecode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:getTimecode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the timecode of the current playhead position.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Timecode value as string.</li></ul>          |

#### [getX](#getx)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:getX() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `x` position of the playhead.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`x` position as number.</li></ul>          |

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

#### [setTimecode](#settimecode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:setTimecode(timecode) -> Playhead object | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Moves the playhead to a specific timecode value.                                                                                         |
| **Parameters**                                       | <ul><li>timecode - The timecode value you want to move to as a string in the following format: "hh:mm:ss:ff" (i.e. "01:00:00:00").</li></ul> |
| **Returns**                                          | <ul><li>Playhead object is successful otherwise `nil`</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:show() -> Playhead object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Playhead                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Playhead object</li></ul>          |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:UI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Playhead                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A `hs._asm.axuielement` object</li></ul>          |

