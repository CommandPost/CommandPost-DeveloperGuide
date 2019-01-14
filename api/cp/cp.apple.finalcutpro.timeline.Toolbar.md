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
* Methods - API calls which can only be made on an object returned by a constructor
 * [appearance](#appearance)
 * [browser](#browser)
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

### Methods

#### [appearance](#appearance)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar:appearance() -> cp.apple.finalcutpro.timeline.Appearance` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [Appearance](cp.apple.finalcutpro.timeline.Appearance.md) button/palette control. |
| **Returns**                                          | <ul><li>The <code>Appearance</code> class.</li></ul> |

#### [browser](#browser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar:browser() -> cp.apple.finalcutpro.timeline.Toolbar.Browser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [Toolbar.Browser](cp.apple.finalcutpro.timeline.Toolbar.Browser.md) containing buttons that will toggle the Effects/Transitions browsers. |

#### [index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar:index() -> cp.ui.CheckBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [CheckBox](cp.ui.CheckBox.md) which indicates if the Timeline Index is visible. |

#### [skimming](#skimming)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar.skimming() -> cp.apple.finalcutpro.timeline.Toolbar.Skimming` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [Skimming](cp.apple.finalcutpro.timeline.Toolbar.Skimming.md) group of checkbox items. |

#### [skimmingGroup](#skimminggroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar:skimmingGroup() -> cp.ui.Group` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Group](cp.ui.Group.md) containing buttons relating to mouse skimming behaviour, waveforms, snapping, etc. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Toolbar:title() -> cp.ui.StaticText` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the title [StaticText](cp.ui.StaticText.md) from the Timeline Titlebar. |
| **Parameters**                                       | <ul><li>None.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.ui.StaticText.md">StaticText</a> containing the title.</li></ul> |

