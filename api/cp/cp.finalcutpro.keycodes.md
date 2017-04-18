# [docs](index.md) » cp.finalcutpro.keycodes
---

Keycodes Module

## API Overview
* Functions - API calls offered directly by the extension
 * [characterStringToKeyCode](#characterstringtokeycode)
 * [fcpxModifiersToHsModifiers](#fcpxmodifierstohsmodifiers)
 * [keypadCharacterToKeyCode](#keypadcharactertokeycode)
 * [modifierMaskToModifiers](#modifiermasktomodifiers)

## API Documentation

### Functions

#### [characterStringToKeyCode](#characterstringtokeycode)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.finalcutpro.keycodes.characterStringToKeyCode() -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Character Strings from Command Set Format into Hammerspoon Format.                                                                                         |
| **Parameters**                                       | <ul><li>input - Character String</li></ul> |
| **Returns**                                          | <ul><li>Keycode as String or ""</li></ul>          |

#### [fcpxModifiersToHsModifiers](#fcpxmodifierstohsmodifiers)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.finalcutpro.keycodes.fcpxModifiersToHsModifiers() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Modifiers from Command Set Format into Hammerspoon Format                                                                                         |
| **Parameters**                                       | <ul><li>input - Modifiers String</li></ul> |
| **Returns**                                          | <ul><li>table</li></ul>          |

#### [keypadCharacterToKeyCode](#keypadcharactertokeycode)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.finalcutpro.keycodes.keypadCharacterToKeyCode() -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Keypad Character Strings from Command Set Format into Hammerspoon Format.                                                                                         |
| **Parameters**                                       | <ul><li>input - Character String</li></ul> |
| **Returns**                                          | <ul><li>string or nil</li></ul>          |

#### [modifierMaskToModifiers](#modifiermasktomodifiers)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.finalcutpro.keycodes.modifierMaskToModifiers() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Modifiers from Command Set Format into Hammerspoon Format                                                                                         |
| **Parameters**                                       | <ul><li>value - Modifiers String</li></ul> |
| **Returns**                                          | <ul><li>table</li></ul>          |

