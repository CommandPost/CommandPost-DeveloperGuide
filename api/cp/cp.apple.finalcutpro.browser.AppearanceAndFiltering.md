# [docs](index.md) » cp.apple.finalcutpro.browser.AppearanceAndFiltering
---

Clip Appearance & Filtering Menu Popover

## API Overview
* Constants - Useful values which cannot be changed
 * [DURATION](#duration)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [AppearanceAndFiltering](#appearanceandfiltering)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [button](#button)
 * [clipHeight](#clipheight)
 * [continuousPlayback](#continuousplayback)
 * [duration](#duration)
 * [groupBy](#groupby)
 * [sortBy](#sortby)
 * [waveforms](#waveforms)
* Methods - API calls which can only be made on an object returned by a constructor
 * [show](#show)

## API Documentation

### Constants

#### [DURATION](#duration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering.DURATION -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A lookup table of the duration values. |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if a GUI element is the "Clip Appearance & Filtering Menu" popover or not. |
| **Parameters**                                       | <ul><li>element - The element you want to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the <code>element</code> is the "Clip Appearance &amp; Filtering Menu" popover otherwise <code>false</code></li></ul> |

### Constructors

#### [AppearanceAndFiltering](#appearanceandfiltering)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering(parent) -> AppearanceAndFiltering` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Constructs a new "Clip Appearance & Filtering Menu" popover. |
| **Parameters**                                       | <ul><li>parent - The parent object</li></ul> |
| **Returns**                                          | <ul><li>The new <code>AppearanceAndFiltering</code> instance.</li></ul> |

### Fields

#### [button](#button)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering.button <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Clip Appearance & Filtering Menu" button. |

#### [clipHeight](#clipheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering.clipHeight <cp.ui.Slider>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Clip Height Slider. |

#### [continuousPlayback](#continuousplayback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering.continuousPlayback <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Continuous Playback checkbox. |

#### [duration](#duration)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering.duration <cp.ui.Slider>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Duration Slider. |

#### [groupBy](#groupby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering.groupBy <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Group By" popup button. |

#### [sortBy](#sortby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering.sortBy <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Sort By" popup button. |

#### [waveforms](#waveforms)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering.waveforms <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Waveforms checkbox. |

### Methods

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.browser.AppearanceAndFiltering:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the "Clip Appearance & Filtering Menu" Popover |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

