# [docs](index.md) » cp.apple.finalcutpro.timeline.Timeline
---

Timeline Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
 * [matchesMain](#matchesmain)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Timeline](#timeline)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contents](#contents)
 * [effects](#effects)
 * [index](#index)
 * [isFocused](#isfocused)
 * [isLoaded](#isloaded)
 * [isLockedInCentre](#islockedincentre)
 * [isLockedPlayhead](#islockedplayhead)
 * [isOnPrimary](#isonprimary)
 * [isOnSecondary](#isonsecondary)
 * [isPlaying](#isplaying)
 * [isShowing](#isshowing)
 * [mainUI](#mainui)
 * [playhead](#playhead)
 * [rangeSelected](#rangeselected)
 * [skimmingPlayhead](#skimmingplayhead)
 * [speedPopover](#speedpopover)
 * [title](#title)
 * [toolbar](#toolbar)
 * [transitions](#transitions)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [doFocus](#dofocus)
 * [doHide](#dohide)
 * [doOpenProject](#doopenproject)
 * [doShowOnPrimary](#doshowonprimary)
 * [doShowOnSecondary](#doshowonsecondary)
 * [hide](#hide)
 * [show](#show)
 * [showOnPrimary](#showonprimary)
 * [showOnSecondary](#showonsecondary)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code>.</li></ul> |
| **Notes**                                            | <ul><li><code>element</code> should be an <code>AXGroup</code>, which contains an <code>AXSplitGroup</code> with an   <code>AXIdentifier</code> of <code>_NS:237</code> (as of Final Cut Pro 10.4)</li></ul> |

#### [matchesMain](#matchesmain)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.matchesMain(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |
| **Notes**                                            | <ul><li><code>element</code> should be an <code>AXSplitGroup</code> with an <code>AXIdentifier</code> of <code>_NS:237</code>   (as of Final Cut Pro 10.4)</li><li>Because the timeline contents is hard to detect, we look for the timeline   toolbar instead.</li></ul> |

### Constructors

#### [Timeline](#timeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline(app) -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Timeline` instance. |
| **Parameters**                                       | <ul><li>app - The <code>cp.apple.finalcutpro</code> object.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Timeline</code> object.</li></ul> |

### Fields

#### [contents](#contents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.contents <cp.apple.finalcutpro.timeline.Contents>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Timeline Contents. The Content is the main body of the timeline, |

#### [effects](#effects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.effects <cp.apple.finalcutpro.main.EffectsBrowser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The (sometimes hidden) Effect Browser. |

#### [index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.index <cp.apple.finalcutpro.timeline.Index>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Index](cp.apple.finalcutpro.timeline.Index.md). |

#### [isFocused](#isfocused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.isFocused <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Timeline is the focused panel. |

#### [isLoaded](#isloaded)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.isLoaded <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Timeline has finished loading. |

#### [isLockedInCentre](#islockedincentre)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.isLockedInCentre <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is Playhead Locked in the centre? |

#### [isLockedPlayhead](#islockedplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.isLockedPlayhead <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is Playhead Locked? |

#### [isOnPrimary](#isonprimary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.isOnPrimary <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Timeline is on the Primary Display. |

#### [isOnSecondary](#isonsecondary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.isOnSecondary <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Timeline is on the Secondary Display. |

#### [isPlaying](#isplaying)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.isPlaying <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is the timeline playing? |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if the Timeline is showing on either the Primary or Secondary display. |

#### [mainUI](#mainui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.mainUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `axuielement` representing the 'timeline', or `nil` if not available. |

#### [playhead](#playhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.playhead <Playhead>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Timeline Playhead. |

#### [rangeSelected](#rangeselected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.rangeSelected <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Checks if a range is selected in the timeline. |

#### [skimmingPlayhead](#skimmingplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.skimmingPlayhead <Playhead>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Playhead that tracks under the mouse while skimming. |

#### [speedPopover](#speedpopover)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.speedPopover <cp.apple.finalcutpro.timeline.SpeedPopover>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [SpeedPopover](cp.apple.finalcutpro.timeline.SpeedPopover.md). |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.title <cp.ui.StaticText>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [StaticText](cp.ui.StaticText.md) containing the title. |

#### [toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.toolbar <Toolbar>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The bar at the top of the timeline. |

#### [transitions](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline.transitions <cp.apple.finalcutpro.main.EffectsBrowser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The (sometimes hidden) Transitions Browser. |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the app instance representing Final Cut Pro. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [doFocus](#dofocus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:doFocus() -> cp.rx.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to focus on the Timeline. |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will hide the Timeline (regardless of whether it |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code> ready to run.</li></ul> |

#### [doOpenProject](#doopenproject)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:doOpenProject(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Opens a project from the timeline navigation popups. |
| **Parameters**                                       | <ul><li>title - The title of the project you want to open.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to run.</li></ul> |
| **Notes**                                            | <ul><li>The title supports patterns, so you can do things like:   <code>require("cp.apple.finalcutpro").timeline:doOpenProject("Audio.*"):Now()</code></li></ul> |

#### [doShowOnPrimary](#doshowonprimary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:doShowOnPrimary() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will ensure the timeline is in the primary window. |
| **Parameters**                                       | <ul><li>timeout  - The timeout period for the operation.</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code> which will send <code>true</code> if it successful, or <code>false</code> otherwise.</li></ul> |

#### [doShowOnSecondary](#doshowonsecondary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:doShowOnSecondary() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will ensure the timeline is in the secondary window. |
| **Parameters**                                       | <ul><li>timeout  - The timeout period for the operation.</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code> which will send <code>true</code> if it successful, or <code>false</code> otherwise.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:hide() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hide's the Timeline (regardless of whether it was on the Primary or Secondary display). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>Timeline</code> object.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:show() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's the Timeline on the Primary Display. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>Timeline</code> object.</li></ul> |

#### [showOnPrimary](#showonprimary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:showOnPrimary() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's the Timeline on the Primary Display. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>Timeline</code> object.</li></ul> |

#### [showOnSecondary](#showonsecondary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Timeline:showOnSecondary() -> Timeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's the Timeline on the Secondary Display. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>Timeline</code> object.</li></ul> |

