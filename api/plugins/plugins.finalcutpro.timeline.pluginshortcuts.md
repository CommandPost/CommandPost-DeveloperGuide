# [docs](index.md) » plugins.finalcutpro.timeline.pluginshortcuts
---

Controls for Final Cut Pro's Plugin Shortcuts (for use with Hack Shortcuts).

## API Overview
* Functions - API calls offered directly by the extension
 * [applyShortcut](#applyshortcut)
 * [assignShortcut](#assignshortcut)
 * [getShortcut](#getshortcut)
 * [init](#init)
 * [setShortcut](#setshortcut)

## API Documentation

### Functions

#### [applyShortcut](#applyshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.pluginshortcuts.applyShortcut(handlerId, shortcutNumber) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Applies a shortcut.                                                                                         |
| **Parameters**                                       | <ul><li>* `handlerId`		- The action handler ID.</li><li>* `shortcutNumber`	- The shortcut number, between 1 and 5, which is being assigned.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if successful otherwise `false`</li></ul>          |

#### [assignShortcut](#assignshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.pluginshortcuts.assignShortcut(shortcutNumber, handlerId) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Asks the user to assign the specified video effect shortcut number to a selected effect.                                                                                         |
| **Parameters**                                       | <ul><li>* `handlerId`		- The action handler ID.</li><li>* `shortcutNumber`	- The shortcut number, between 1 and 5, which is being assigned.</li></ul> |
| **Returns**                                          | <ul><li>* Nothing</li></ul>          |

#### [getShortcut](#getshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.pluginshortcuts.getShortcut(handlerId, shortcutNumber) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a shortcut.                                                                                         |
| **Parameters**                                       | <ul><li>* `handlerId`		- The action handler ID.</li><li>* `shortcutNumber`	- The shortcut number, between 1 and 5, which is being assigned.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if successful otherwise `false`</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.pluginshortcuts.init(handlerId, action, shortcutNumber) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise the module.                                                                                         |
| **Parameters**                                       | <ul><li>* `deps` - Dependancies</li></ul> |
| **Returns**                                          | <ul><li>* The module</li></ul>          |

#### [setShortcut](#setshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.timeline.pluginshortcuts.setShortcut(handlerId, action, shortcutNumber) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets a shortcut.                                                                                         |
| **Parameters**                                       | <ul><li>* `handlerId`		- The action handler ID.</li><li>* `action`			- The action.</li><li>* `shortcutNumber`	- The shortcut number, between 1 and 5, which is being assigned.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if successful otherwise `false`</li></ul>          |

