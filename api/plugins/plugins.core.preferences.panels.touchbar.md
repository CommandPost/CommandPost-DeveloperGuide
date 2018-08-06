# [docs](index.md) » plugins.core.preferences.panels.touchbar
---

Touch Bar Preferences Panel

## API Overview
* Variables - Configurable values
 * [defaultIconPath](#defaulticonpath)
 * [maxItems](#maxitems)
 * [supportedExtensions](#supportedextensions)
* Functions - API calls offered directly by the extension
 * [getGroupEditor](#getgroupeditor)
 * [init](#init)
 * [setGroupEditor](#setgroupeditor)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)
 * [lastGroup](#lastgroup)

## API Documentation

### Variables

#### [defaultIconPath](#defaulticonpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.touchbar.defaultIconPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Default Path where built-in icons are stored |

#### [maxItems](#maxitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.touchbar.maxItems -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The maximum number of Touch Bar items per group. |

#### [supportedExtensions](#supportedextensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.touchbar.supportedExtensions -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table of supported extensions for Touch Bar Icons. |

### Functions

#### [getGroupEditor](#getgroupeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.touchbar.getGroupEditor(groupId) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the Group Editor |
| **Parameters**                                       | <ul><li>groupId - Group ID</li></ul> |
| **Returns**                                          | <ul><li>Group Editor</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.touchbar.init(deps, env) -> module` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialise the Module. |
| **Parameters**                                       | <ul><li>deps - Dependancies Table</li><li>env - Environment Table</li></ul> |
| **Returns**                                          | <ul><li>The Module</li></ul> |

#### [setGroupEditor](#setgroupeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.touchbar.setGroupEditor(groupId, editorFn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets the Group Editor |
| **Parameters**                                       | <ul><li>groupId - Group ID</li><li>editorFn - Editor Function</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.touchbar.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable Touch Bar Support. |

#### [lastGroup](#lastgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.touchbar.lastGroup <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Last group used in the Preferences Drop Down. |

