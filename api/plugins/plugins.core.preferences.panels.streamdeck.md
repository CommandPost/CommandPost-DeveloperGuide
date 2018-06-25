# [docs](index.md) » plugins.core.preferences.panels.streamdeck
---

Stream Deck Preferences Panel

## API Overview
* Variables - Configurable values
 * [defaultIconPath](#defaulticonpath)
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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.streamdeck.defaultIconPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Default Path where built-in icons are stored                                                                                         |

#### [supportedExtensions](#supportedextensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.streamdeck.supportedExtensions -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of supported extensions for Stream Deck Icons.                                                                                         |

### Functions

#### [getGroupEditor](#getgroupeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.streamdeck.getGroupEditor(groupId) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the Group Editor                                                                                         |
| **Parameters**                                       | <ul><br /><li>groupId - Group ID</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Group Editor</li><br /></ul>                                           |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.streamdeck.init(deps, env) -> module` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise the Module.                                                                                         |
| **Parameters**                                       | <ul><br /><li>deps - Dependancies Table * env - Environment Table</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The Module</li><br /></ul>                                           |

#### [setGroupEditor](#setgroupeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.streamdeck.setGroupEditor(groupId, editorFn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Group Editor                                                                                         |
| **Parameters**                                       | <ul><br /><li>groupId - Group ID * editorFn - Editor Function</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.streamdeck.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Enable or disable Stream Deck Support.                                                                                         |

#### [lastGroup](#lastgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.preferences.panels.streamdeck.lastGroup <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Last group used in the Preferences Drop Down.                                                                                         |

