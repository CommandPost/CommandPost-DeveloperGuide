# [docs](index.md) » plugins.core.loupedeckct.manager
---

Loupedeck CT Manager Plugin.

## API Overview
* Variables - Configurable values
 * [defaultLayout](#defaultlayout)
* Functions - API calls offered directly by the extension
 * [refresh](#refresh)
 * [reset](#reset)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activeBanks](#activebanks)
 * [automaticallySwitchApplications](#automaticallyswitchapplications)
 * [connected](#connected)
 * [enabled](#enabled)
 * [enableFlashDrive](#enableflashdrive)
 * [items](#items)
 * [loadSettingsFromDevice](#loadsettingsfromdevice)
 * [screensBacklightLevel](#screensbacklightlevel)

## API Documentation

### Variables

#### [defaultLayout](#defaultlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.defaultLayout -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Default Loupedeck CT Layout |

### Functions

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.refresh()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Refreshes the Loupedeck CT screens and LED buttons. |
| **Parameters**                                       | <ul><li>dueToAppChange - A optional boolean to specify whether the refresh is due to                    an application focus change.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.reset()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Resets the config back to the default layout. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [activeBanks](#activebanks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.activeBanks <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Table of active banks for each application. |

#### [automaticallySwitchApplications](#automaticallyswitchapplications)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.automaticallySwitchApplications <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable the automatic switching of applications. |

#### [connected](#connected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.connected <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is Loupedeck CT connected? |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is Loupedeck CT support enabled? |

#### [enableFlashDrive](#enableflashdrive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.enableFlashDrive <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable the Loupedeck CT Flash Drive. |

#### [items](#items)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.items <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains all the saved Loupedeck CT layouts. |

#### [loadSettingsFromDevice](#loadsettingsfromdevice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.loadSettingsFromDevice <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Load settings from device. |

#### [screensBacklightLevel](#screensbacklightlevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckct.manager.screensBacklightLevel <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Screens Backlight Level |

