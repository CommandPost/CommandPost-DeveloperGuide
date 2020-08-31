# [docs](index.md) » plugins.core.tourbox.manager
---

Loupedeck CT Manager Plugin.

## API Overview
* Variables - Configurable values
 * [defaultLayout](#defaultlayout)
* Functions - API calls offered directly by the extension
 * [connectToTourBox](#connecttotourbox)
 * [reset](#reset)
 * [resetTimers](#resettimers)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activeBanks](#activebanks)
 * [automaticallySwitchApplications](#automaticallyswitchapplications)
 * [displayMessageWhenChangingBanks](#displaymessagewhenchangingbanks)
 * [enabled](#enabled)
 * [items](#items)

## API Documentation

### Variables

#### [defaultLayout](#defaultlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tourbox.manager.defaultLayout -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Default Loupedeck CT Layout |

### Functions

#### [connectToTourBox](#connecttotourbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tourbox.manager.connectToTourBox() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Attempts to establish the TourBox serial connection. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tourbox.manager.reset()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Resets the config back to the default layout. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [resetTimers](#resettimers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tourbox.manager.resetTimers() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Resets all the various timers and memories. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [activeBanks](#activebanks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tourbox.manager.activeBanks <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Table of active banks for each application. |

#### [automaticallySwitchApplications](#automaticallyswitchapplications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tourbox.manager.automaticallySwitchApplications <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable the automatic switching of applications. |

#### [displayMessageWhenChangingBanks](#displaymessagewhenchangingbanks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tourbox.manager.displayMessageWhenChangingBanks <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Display message when changing banks? |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tourbox.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is Loupedeck CT support enabled? |

#### [items](#items)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.tourbox.manager.items <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains all the saved TourBox layouts. |

