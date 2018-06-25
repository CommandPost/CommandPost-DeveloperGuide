# [docs](index.md) » cp.apple.commandeditor
---

Functions to control and manage Apple's Command Editor - used in Final Cut Pro,
Motion and Compressor.

## API Overview
* Variables - Configurable values
 * [padKeys](#padkeys)
* Functions - API calls offered directly by the extension
 * [characterStringToKeyCode](#characterstringtokeycode)
 * [keypadCharacterToKeyCode](#keypadcharactertokeycode)
 * [modifierMaskToModifiers](#modifiermasktomodifiers)
 * [modifierMatch](#modifiermatch)
 * [shortcutsFromCommandSet](#shortcutsfromcommandset)
 * [translateModifiers](#translatemodifiers)

## API Documentation

### Variables

#### [padKeys](#padkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.commandeditor.padKeys -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table of Pad Keys |

### Functions

#### [characterStringToKeyCode](#characterstringtokeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.commandeditor.characterStringToKeyCode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Translate Keyboard Character Strings from Command Set Format into Hammerspoon Format. |
| **Parameters**                                       | <ul><li>input - Character String</li></ul> |
| **Returns**                                          | <ul><li>Keycode as String or ""</li></ul> |

#### [keypadCharacterToKeyCode](#keypadcharactertokeycode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.commandeditor.keypadCharacterToKeyCode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Translate Keyboard Keypad Character Strings from Command Set Format into Hammerspoon Format. |
| **Parameters**                                       | <ul><li>input - Character String</li></ul> |
| **Returns**                                          | <ul><li>string or nil</li></ul> |

#### [modifierMaskToModifiers](#modifiermasktomodifiers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.commandeditor.modifierMaskToModifiers() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Translate Keyboard Modifiers from Apple's Property List Format into Hammerspoon Format. |
| **Parameters**                                       | <ul><li>value - Modifiers String</li></ul> |
| **Returns**                                          | <ul><li>A table of modifier strings.</li></ul> |

#### [modifierMatch](#modifiermatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.commandeditor.modifierMatch(inputA, inputB) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Compares two modifier tables. |
| **Parameters**                                       | <ul><li>inputA - table of modifiers * inputB - table of modifiers</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if there's a match otherwise <code>false</code></li></ul> |
| **Notes**                                            | <ul><li>This function only takes into account 'ctrl', 'alt', 'cmd', 'shift'.</li></ul> |

#### [shortcutsFromCommandSet](#shortcutsfromcommandset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.commandeditor.shortcutsFromCommandSet(id, commandSet) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a specific command from a specified Command Set and returns a table of Shortcuts. |
| **Parameters**                                       | <ul><li>id - The ID of the command you want to get. * commandSet - A table containing an entire Command Set.</li></ul> |
| **Returns**                                          | <ul><li>A table of shortcuts for a specific command.</li></ul> |

#### [translateModifiers](#translatemodifiers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.commandeditor.translateModifiers() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Translate Keyboard Modifiers from Command Set Format into Hammerspoon Format. |
| **Parameters**                                       | <ul><li>input - Modifiers String</li></ul> |
| **Returns**                                          | <ul><li>table</li></ul> |

