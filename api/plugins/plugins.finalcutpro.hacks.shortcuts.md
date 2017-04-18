# [docs](index.md) » plugins.finalcutpro.hacks.shortcuts
---

Plugin that allows the user to customise the CommandPost shortcuts
via the Final Cut Pro Command Editor.

## API Overview
* Functions - API calls offered directly by the extension
 * [disableHacksShortcuts](#disablehacksshortcuts)
 * [editCommands](#editcommands)
 * [enableHacksShortcuts](#enablehacksshortcuts)
 * [enabled](#enabled)
 * [init](#init)
 * [setEditable](#seteditable)
 * [toggleEditable](#toggleeditable)
 * [update](#update)

## API Documentation

### Functions

#### [disableHacksShortcuts](#disablehacksshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.disableHacksShortcuts() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disable Hacks Shortcuts                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>Used by Trash Preferences menubar command.</li></ul>                |

#### [editCommands](#editcommands)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.editCommands() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Launch the Final Cut Pro Command Editor                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [enableHacksShortcuts](#enablehacksshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.enableHacksShortcuts() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enable Hacks Shortcuts                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.enabled() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Are Hacks Shortcuts Enabled?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if Hacks Shortcuts are enabled otherwise `false`</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setEditable](#seteditable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.setEditable() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enable Hacks Shortcuts                                                                                         |
| **Parameters**                                       | <ul><li>enabled - True if you want to enable Hacks Shortcuts otherwise false</li><li>skipFCPXupdate - Whether or not you want to skip reloading Final Cut Pro</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [toggleEditable](#toggleeditable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.toggleEditable() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggle Editable                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Read shortcut keys from the Final Cut Pro Preferences.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

