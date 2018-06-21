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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if matches otherwise `false`.</li></ul>          |

#### [matchesMain](#matchesmain)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline.matchesMain(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if matches otherwise `false`</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline.new(app) -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Timeline` instance.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">app - The `cp.apple.finalcutpro` object.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A new `Timeline` object.</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">App</li></ul>          |

#### [contents](#contents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:contents() -> TimelineContent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Timeline Contents. The Content is the main body of the timeline,                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`TimelineContent` object.</li></ul>          |

#### [effects](#effects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:effects() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the (sometimes hidden) Effect Browser.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`EffectsBrowser` object.</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:hide() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hide's the Timeline (regardless of whether it was on the Primary or Secondary display).                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`Timeline` object.</li></ul>          |

#### [playhead](#playhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:playhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Timeline Playhead.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`Playhead` object.</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:show() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Timeline on the Primary Display.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`Timeline` object.</li></ul>          |

#### [showOnPrimary](#showonprimary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:showOnPrimary() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Timeline on the Primary Display.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`Timeline` object.</li></ul>          |

#### [showOnSecondary](#showonsecondary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:showOnSecondary() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the Timeline on the Secondary Display.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`Timeline` object.</li></ul>          |

#### [skimmingPlayhead](#skimmingplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:skimmingPlayhead() -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Playhead that tracks under the mouse while skimming.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`Playhead` object.</li></ul>          |

#### [toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:toolbar() -> TimelineToolbar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the bar at the top of the timeline.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`TimelineToolbar` object.</li></ul>          |

#### [transitions](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:transitions() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the (sometimes hidden) Transitions Browser.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`EffectsBrowser` object.</li></ul>          |

