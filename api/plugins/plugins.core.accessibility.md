# [docs](index.md) » plugins.core.accessibility
---

Accessibility Plugin.

## API Overview
* Constants - Useful values which cannot be changed
 * [enabled](#enabled)
* Variables - Configurable values
 * [systemPreferencesAlreadyOpen](#systempreferencesalreadyopen)
* Functions - API calls offered directly by the extension
 * [completeSetupPanel](#completesetuppanel)
 * [init](#init)
 * [showSetupPanel](#showsetuppanel)

## API Documentation

### Constants

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.accessibility.enabled <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Is `true` if Accessibility permissions have been enabled for CommandPost. |

### Variables

#### [systemPreferencesAlreadyOpen](#systempreferencesalreadyopen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.accessibility.systemPreferencesAlreadyOpen -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Was System Preferences already open? |

### Functions

#### [completeSetupPanel](#completesetuppanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.accessibility.completeSetupPanel() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Called when the setup panel for accessibility was shown and is ready to complete. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.accessibility.init(setup) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the module. |
| **Parameters**                                       | <ul><li>setup - Dependancies setup</li></ul> |
| **Returns**                                          | <ul><li>The module as a table</li></ul> |

#### [showSetupPanel](#showsetuppanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.accessibility.showSetupPanel() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Called when the Setup Panel should be shown to prompt the user about enabling Accessbility. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

