# [docs](index.md) » cp.finalcutpro.keycodes
---

Keycodes Module

## API Overview
* Functions - API calls offered directly by the extension
 * [characterStringToKeyCode](#characterStringToKeyCode)
 * [fcpxModifiersToHsModifiers](#fcpxModifiersToHsModifiers)
 * [keypadCharacterToKeyCode](#keypadCharacterToKeyCode)
 * [modifierMaskToModifiers](#modifierMaskToModifiers)

## API Documentation

### Functions

| [characterStringToKeyCode](#characterStringToKeyCode)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.keycodes.characterStringToKeyCode() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Translate Keyboard Character Strings from Command Set Format into Hammerspoon Format.                                                                     |
| **Parameters**                              | <ul><li>input - Character String</li></ul> |
| **Returns**                                 | <ul><li>Keycode as String or ""</li></ul>          |

| [fcpxModifiersToHsModifiers](#fcpxModifiersToHsModifiers)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.keycodes.fcpxModifiersToHsModifiers() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Translate Keyboard Modifiers from Command Set Format into Hammerspoon Format                                                                     |
| **Parameters**                              | <ul><li>input - Modifiers String</li></ul> |
| **Returns**                                 | <ul><li>table</li></ul>          |

| [keypadCharacterToKeyCode](#keypadCharacterToKeyCode)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.keycodes.keypadCharacterToKeyCode() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Translate Keyboard Keypad Character Strings from Command Set Format into Hammerspoon Format.                                                                     |
| **Parameters**                              | <ul><li>input - Character String</li></ul> |
| **Returns**                                 | <ul><li>string or nil</li></ul>          |

| [modifierMaskToModifiers](#modifierMaskToModifiers)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.finalcutpro.keycodes.modifierMaskToModifiers() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Translate Keyboard Modifiers from Command Set Format into Hammerspoon Format                                                                     |
| **Parameters**                              | <ul><li>value - Modifiers String</li></ul> |
| **Returns**                                 | <ul><li>table</li></ul>          |

