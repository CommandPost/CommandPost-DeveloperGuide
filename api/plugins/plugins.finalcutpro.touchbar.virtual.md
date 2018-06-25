# [docs](index.md) » plugins.finalcutpro.touchbar.virtual
---

Virtual Touch Bar Plugin.

## API Overview
* Constants - Useful values which cannot be changed
 * [LOCATION_TIMELINE](#location_timeline)
 * [VISIBILITY_ALWAYS](#visibility_always)
 * [VISIBILITY_DEFAULT](#visibility_default)
 * [VISIBILITY_FCP](#visibility_fcp)
* Functions - API calls offered directly by the extension
 * [updateLocation](#updatelocation)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)
 * [location](#location)
 * [visibility](#visibility)

## API Documentation

### Constants

#### [LOCATION_TIMELINE](#location_timeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.touchbar.virtual.LOCATION_TIMELINE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Virtual Touch Bar is displayed in the top centre of the Final Cut Pro timeline                                                                                         |

#### [VISIBILITY_ALWAYS](#visibility_always)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.touchbar.virtual.VISIBILITY_ALWAYS -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Virtual Touch Bar is Always Visible                                                                                         |

#### [VISIBILITY_DEFAULT](#visibility_default)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.touchbar.virtual.VISIBILITY_DEFAULT -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default visibility.                                                                                         |

#### [VISIBILITY_FCP](#visibility_fcp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.touchbar.virtual.VISIBILITY_FCP -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Virtual Touch Bar is only visible when Final Cut Pro is active.                                                                                         |

### Functions

#### [updateLocation](#updatelocation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.touchbar.virtual.updateLocation() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Location of the Virtual Touch Bar                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.touchbar.virtual.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the plugin is enabled.                                                                                         |

#### [location](#location)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.touchbar.virtual.location <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The Virtual Touch Bar Location Setting                                                                                         |

#### [visibility](#visibility)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.touchbar.virtual.visibility <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | When should the Virtual Touch Bar be visible?                                                                                         |

