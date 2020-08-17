# [docs](index.md) » cp.apple.finalcutpro.timeline.Toolbar
---

Timeline Toolbar

## Submodules
 * [cp.apple.finalcutpro.timeline.Toolbar.Browser](cp.apple.finalcutpro.timeline.Toolbar.Browser.md)
 * [cp.apple.finalcutpro.timeline.Toolbar.Skimming](cp.apple.finalcutpro.timeline.Toolbar.Skimming.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Toolbar](#toolbar)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [appearance](#appearance)
 * [appearanceToggle](#appearancetoggle)
 * [back](#back)
 * [browser](#browser)
 * [duration](#duration)
 * [forward](#forward)
 * [index](#index)
 * [skimming](#skimming)
 * [skimmingGroup](#skimminggroup)
 * [title](#title)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is a Toolbar. |
| **Parameters**                                       | <ul><li>element - the <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches, otherwise <code>false</code>.</li></ul> |

### Constructors

#### [Toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar(timeline) -> cp.apple.finalcutpro.timeline.Toolbar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Toolbar with the specified parent. |
| **Parameters**                                       | <ul><li>timeline - The <a href="cp.apple.finalcutpro.timeline.Timeline.md">Timeline</a>.</li></ul> |
| **Returns**                                          | <ul><li>The new Toolbar instance.</li></ul> |

### Fields

#### [appearance](#appearance)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.appearance <cp.apple.finalcutpro.timeline.Appearance>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Appearance](cp.apple.finalcutpro.timeline.Appearance.md) button/palette control. |

#### [appearanceToggle](#appearancetoggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.appearanceToggle <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `CheckBox` field which will toggle the `appearance` popover. |

#### [back](#back)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.back <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Button](cp.ui.Button.md) for "go back in timeline history". |

#### [browser](#browser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.browser <cp.apple.finalcutpro.timeline.Toolbar.Browser>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Toolbar.Browser](cp.apple.finalcutpro.timeline.Toolbar.Browser.md) containing buttons that will toggle the Effects/Transitions browsers. |

#### [duration](#duration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.duration <cp.ui.StaticText>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The duration [StaticText](cp.ui.StaticText.md) from the Timeline Titlebar. |

#### [forward](#forward)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.forward <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Button](cp.ui.Button.md) for "go forward in timeline history". |

#### [index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.index <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [CheckBox](cp.ui.CheckBox.md) which indicates if the Timeline Index is visible. |

#### [skimming](#skimming)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.skimming <cp.apple.finalcutpro.timeline.Toolbar.Skimming>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Skimming](cp.apple.finalcutpro.timeline.Toolbar.Skimming.md) group of checkbox items. |

#### [skimmingGroup](#skimminggroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.skimmingGroup <cp.ui.Group>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [Group](cp.ui.Group.md) containing buttons relating to mouse skimming behaviour, waveforms, snapping, etc. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.title <cp.ui.StaticText>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The title [StaticText](cp.ui.StaticText.md) from the Timeline Titlebar. |

