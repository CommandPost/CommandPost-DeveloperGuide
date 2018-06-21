# [docs](index.md) » cp.apple.finalcutpro.main.Timeline
---

Timeline Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
 * [matchesMain](#matchesmain)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [contents](#contents)
 * [effects](#effects)
 * [hide](#hide)
 * [playhead](#playhead)
 * [show](#show)
 * [showOnPrimary](#showonprimary)
 * [showOnSecondary](#showonsecondary)
 * [skimmingPlayhead](#skimmingplayhead)
 * [toolbar](#toolbar)
 * [transitions](#transitions)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`.                                                |

#### [matchesMain](#matchesmain)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline.matchesMain(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline.new(app) -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Timeline` instance.                                                                                         |
| **Parameters**                                       |  * app - The `cp.apple.finalcutpro` object.                                       |
| **Returns**                                          |  * A new `Timeline` object.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [contents](#contents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:contents() -> TimelineContent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Timeline Contents. The Content is the main body of the timeline,                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `TimelineContent` object.                                                |

#### [effects](#effects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:effects() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the (sometimes hidden) Effect Browser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `EffectsBrowser` object.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:hide() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hide's the Timeline (regardless of whether it was on the Primary or Secondary display).                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `Timeline` object.                                                |

#### [playhead](#playhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:playhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Timeline Playhead.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `Playhead` object.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:show() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Timeline on the Primary Display.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `Timeline` object.                                                |

#### [showOnPrimary](#showonprimary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:showOnPrimary() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Timeline on the Primary Display.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `Timeline` object.                                                |

#### [showOnSecondary](#showonsecondary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:showOnSecondary() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Timeline on the Secondary Display.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `Timeline` object.                                                |

#### [skimmingPlayhead](#skimmingplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:skimmingPlayhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Playhead that tracks under the mouse while skimming.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `Playhead` object.                                                |

#### [toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:toolbar() -> TimelineToolbar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the bar at the top of the timeline.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `TimelineToolbar` object.                                                |

#### [transitions](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:transitions() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the (sometimes hidden) Transitions Browser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `EffectsBrowser` object.                                                |

