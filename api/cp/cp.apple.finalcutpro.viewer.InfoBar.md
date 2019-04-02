# [docs](index.md) » cp.apple.finalcutpro.viewer.InfoBar
---

Represents the bar of information about the [Viewer](cp.apple.finalcutpro.viewer.Viewer.md) (format, title, viewing options).

See also [ControlBar](cp.apple.finalcutpro.viewer.ControlBar.md).

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [InfoBar](#infobar)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [format](#format)
 * [formatField](#formatfield)
 * [framerate](#framerate)
 * [title](#title)
 * [titleField](#titlefield)
 * [viewMenu](#viewmenu)
 * [zoomwMenu](#zoomwmenu)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.InfoBar.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is an `InfoBar` instance. |
| **Parameters**                                       | <ul><li>element       - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches the pattern for a <code>Viewer</code> <code>InfoBar</code>.</li></ul> |

### Constructors

#### [InfoBar](#infobar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.InfoBar(viewer)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `InfoBar` instance. |
| **Parameters**                                       | <ul><li>viewer       - The <a href="cp.apple.finalcutpro.viewer.Viewer.md">Viewer</a> instance.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>InfoBar</code>.</li></ul> |

### Fields

#### [format](#format)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.InfoBar.format <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Provides the full format text value, or `nil` if not available. |

#### [formatField](#formatfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.InfoBar.formatField <cp.ui.StaticText>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Field" value for the current clip, as a [StaticText](cp.ui.StaticText.md) |

#### [framerate](#framerate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.InfoBar.framerate <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Provides the framerate as a number, or `nil` if not available. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.InfoBar.title <cp.prop: string; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Provides the Title of the clip in the Viewer as a [StaticText](cp.ui.StaticText.md). |

#### [titleField](#titlefield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.InfoBar.titleField <cp.ui.StaticText>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Provides the Title of the clip in the Viewer as a [StaticText](cp.ui.StaticText.md). |

#### [viewMenu](#viewmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.InfoBar:viewMenu <cp.ui.MenuButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [MenuButton](cp.ui.MenuButton.md) for the "View" menu. |

#### [zoomwMenu](#zoomwmenu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.viewer.InfoBar:zoomwMenu <cp.ui.MenuButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [MenuButton](cp.ui.MenuButton.md) for the "Zoom Level" menu. |

