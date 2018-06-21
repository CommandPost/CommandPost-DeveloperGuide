# [docs](index.md) » plugins.finalcutpro.fullscreen.shortcuts
---

Fullscreen Shortcuts

## API Overview
* Variables - Configurable values
 * [enabled](#enabled)
* Functions - API calls offered directly by the extension
 * [checkCommand](#checkcommand)
 * [ninjaKeyStroke](#ninjakeystroke)
 * [performCommand](#performcommand)
 * [update](#update)

## API Documentation

### Variables

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.fullscreen.shortcuts.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is the module enabled?                                                                                         |

### Functions

#### [checkCommand](#checkcommand)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.fullscreen.shortcuts.checkCommand(whichModifier, whichKey) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if a shortcut has been pressed, then processes.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">whichModifier - Which modifier key to check.</li><li markdown="1">whichKey - Which key to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [ninjaKeyStroke](#ninjakeystroke)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.fullscreen.shortcuts.ninjaKeyStroke(whichModifier, whichKey) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Ninja Key Stoke.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">whichModifier - Modifier Key</li><li markdown="1">whichKey - Key</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [performCommand](#performcommand)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.fullscreen.shortcuts.performCommand(cmd, whichModifier, whichKey) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a command.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">cmd - The Command.</li><li markdown="1">whichModifier - Which modifier key to check.</li><li markdown="1">whichKey - Which key to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful otherwise `false`</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.fullscreen.shortcuts.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles the watches for monitoring fullscreen playback.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

