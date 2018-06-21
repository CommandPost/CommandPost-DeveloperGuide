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
| **Parameters**                                       |  * whichModifier - Which modifier key to check. * whichKey - Which key to check.                                       |
| **Returns**                                          |  * None                                                |

#### [ninjaKeyStroke](#ninjakeystroke)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.fullscreen.shortcuts.ninjaKeyStroke(whichModifier, whichKey) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Ninja Key Stoke.                                                                                         |
| **Parameters**                                       |  * whichModifier - Modifier Key * whichKey - Key                                       |
| **Returns**                                          |  * None                                                |

#### [performCommand](#performcommand)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.fullscreen.shortcuts.performCommand(cmd, whichModifier, whichKey) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a command.                                                                                         |
| **Parameters**                                       |  * cmd - The Command. * whichModifier - Which modifier key to check. * whichKey - Which key to check.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.fullscreen.shortcuts.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles the watches for monitoring fullscreen playback.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

