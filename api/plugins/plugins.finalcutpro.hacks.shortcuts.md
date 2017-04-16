# [docs](index.md) » plugins.finalcutpro.hacks.shortcuts
---

Plugin that allows the user to customise the CommandPost shortcuts
via the Final Cut Pro Command Editor.

## API Overview
* Functions - API calls offered directly by the extension
 * [disableHacksShortcuts](#disableHacksShortcuts)
 * [editCommands](#editCommands)
 * [enableHacksShortcuts](#enableHacksShortcuts)
 * [enabled](#enabled)
 * [init](#init)
 * [setEditable](#setEditable)
 * [toggleEditable](#toggleEditable)
 * [update](#update)

## API Documentation

### Functions

| [disableHacksShortcuts](#disableHacksShortcuts)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hacks.shortcuts.disableHacksShortcuts() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Disable Hacks Shortcuts                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>Used by Trash Preferences menubar command.</li></ul>                |

| [editCommands](#editCommands)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hacks.shortcuts.editCommands() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Launch the Final Cut Pro Command Editor                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [enableHacksShortcuts](#enableHacksShortcuts)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hacks.shortcuts.enableHacksShortcuts() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Enable Hacks Shortcuts                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [enabled](#enabled)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hacks.shortcuts.enabled() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Are Hacks Shortcuts Enabled?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if Hacks Shortcuts are enabled otherwise `false`</li></ul>          |

| [init](#init)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hacks.shortcuts.init() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialises the module.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [setEditable](#setEditable)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hacks.shortcuts.setEditable() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Enable Hacks Shortcuts                                                                     |
| **Parameters**                              | <ul><li>enabled - True if you want to enable Hacks Shortcuts otherwise false</li><li>skipFCPXupdate - Whether or not you want to skip reloading Final Cut Pro</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [toggleEditable](#toggleEditable)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hacks.shortcuts.toggleEditable() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggle Editable                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [update](#update)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hacks.shortcuts.update() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Read shortcut keys from the Final Cut Pro Preferences.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

