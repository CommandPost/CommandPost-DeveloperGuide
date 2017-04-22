# [docs](index.md) » cp.apple.finalcutpro.keycodes
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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.keycodes.characterStringToKeyCode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Character Strings from Command Set Format into Hammerspoon Format.                                                                                         |
| **Parameters**                                       | <ul><li>input - Character String</li></ul> |
| **Returns**                                          | <ul><li>Keycode as String or ""</li></ul>          |

#### [fcpxModifiersToHsModifiers](#fcpxmodifierstohsmodifiers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.keycodes.fcpxModifiersToHsModifiers() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Modifiers from Command Set Format into Hammerspoon Format                                                                                         |
| **Parameters**                                       | <ul><li>input - Modifiers String</li></ul> |
| **Returns**                                          | <ul><li>table</li></ul>          |

#### [keypadCharacterToKeyCode](#keypadcharactertokeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.keycodes.keypadCharacterToKeyCode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Keypad Character Strings from Command Set Format into Hammerspoon Format.                                                                                         |
| **Parameters**                                       | <ul><li>input - Character String</li></ul> |
| **Returns**                                          | <ul><li>string or nil</li></ul>          |

#### [modifierMaskToModifiers](#modifiermasktomodifiers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.keycodes.modifierMaskToModifiers() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Modifiers from Command Set Format into Hammerspoon Format                                                                                         |
| **Parameters**                                       | <ul><li>value - Modifiers String</li></ul> |
| **Returns**                                          | <ul><li>table</li></ul>          |

