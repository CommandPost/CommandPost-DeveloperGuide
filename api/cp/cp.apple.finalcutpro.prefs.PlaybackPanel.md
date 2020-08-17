# [docs](index.md) » cp.apple.finalcutpro.prefs.PlaybackPanel
---

Playback Panel Module.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [PlaybackPanel](#playbackpanel)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [avOutput](#avoutput)
 * [backgroundRender](#backgroundrender)
 * [backgroundRenderDelay](#backgroundrenderdelay)
 * [createMulticamOptimizedMedia](#createmulticamoptimizedmedia)
 * [playerBackground](#playerbackground)
 * [postRollDuration](#postrollduration)
 * [preRollDuration](#prerollduration)
 * [renderShareGPU](#rendersharegpu)
 * [showHDRAsToneMapped](#showhdrastonemapped)
 * [warnAfterPlaybackOnDiskFrameDrop](#warnafterplaybackondiskframedrop)
 * [warnAfterPlaybackOnVRFrameDrop](#warnafterplaybackonvrframedrop)
 * [warnOnFrameDrop](#warnonframedrop)

## API Documentation

### Constructors

#### [PlaybackPanel](#playbackpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel(preferencesDialog) -> PlaybackPanel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `PlaybackPanel` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>PlaybackPanel</code> object.</li></ul> |

### Fields

#### [avOutput](#avoutput)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.avOutput <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `PopUpButton` for "A/V Output". |

#### [backgroundRender](#backgroundrender)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.backgroundRender <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` for "Background render". |

#### [backgroundRenderDelay](#backgroundrenderdelay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.backgroundRenderDelay <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `TextField` for "Background render". |

#### [createMulticamOptimizedMedia](#createmulticamoptimizedmedia)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.createMulticamOptimizedMedia <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` for "Create optimized media for multicam clips". |

#### [playerBackground](#playerbackground)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.playerBackground <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `PopUpButton` for "Player Background". |

#### [postRollDuration](#postrollduration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.postRollDuration <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `TextField` for "Post-Roll Duration" in seconds. |

#### [preRollDuration](#prerollduration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.preRollDuration <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `TextField` for "Pre-Roll Duration" in seconds. |

#### [renderShareGPU](#rendersharegpu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.renderShareGPU <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `PopUpButton` for "Render/Share GPU". |

#### [showHDRAsToneMapped](#showhdrastonemapped)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.showHDRAsToneMapped <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` for "Show HDR as Tone Mapped". |

#### [warnAfterPlaybackOnDiskFrameDrop](#warnafterplaybackondiskframedrop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.warnAfterPlaybackOnDiskFrameDrop <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` for "If frames drop due to disk performance, warn after playback". |

#### [warnAfterPlaybackOnVRFrameDrop](#warnafterplaybackonvrframedrop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.warnAfterPlaybackOnVRFrameDrop <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` for "If frames drop on VR headset, warn after playback". |

#### [warnOnFrameDrop](#warnonframedrop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PlaybackPanel.warnOnFrameDrop <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` for "If a frame drops, stop playback and warn". |

