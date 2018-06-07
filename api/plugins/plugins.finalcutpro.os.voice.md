# [docs](index.md) » plugins.finalcutpro.os.voice
---

Voice Command Plugin.

## API Overview
* Variables - Configurable values
 * [active](#active)
 * [announcementsEnabled](#announcementsenabled)
 * [commandsByTitle](#commandsbytitle)
 * [commandTitles](#commandtitles)
 * [enabled](#enabled)
 * [listening](#listening)
 * [visualAlertsEnabled](#visualalertsenabled)
* Functions - API calls offered directly by the extension
 * [activateCommand](#activatecommand)
 * [getCommandTitles](#getcommandtitles)
 * [new](#new)
 * [openDictationSystemPreferences](#opendictationsystempreferences)
 * [pause](#pause)
 * [registerCommands](#registercommands)
 * [start](#start)
 * [stop](#stop)
 * [update](#update)

## API Documentation

### Variables

#### [active](#active)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.active <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Are Voice Commands active? This will be true if they are both [enabled](#enabled) and FCP is frontmost.                                                                                         |

#### [announcementsEnabled](#announcementsenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.announcementsEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Announcements Enabled?                                                                                         |

#### [commandsByTitle](#commandsbytitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.commandsByTitle -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Command By Title                                                                                         |

#### [commandTitles](#commandtitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.commandTitles -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Command Titles                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Are Voice Commands Enabled?                                                                                         |

#### [listening](#listening)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.listening <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is the listener listening?                                                                                         |

#### [visualAlertsEnabled](#visualalertsenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.visualAlertsEnabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Visual Alerts Enabled?                                                                                         |

### Functions

#### [activateCommand](#activatecommand)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.activateCommand(title) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Activate Command                                                                                         |
| **Parameters**                                       | <ul><li>title - The title as a string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [getCommandTitles](#getcommandtitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.getCommandTitles() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the Command Titles                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The command titles as a table.</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.new() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new listener.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful otherwise `false` if an errors occurs.</li></ul>          |

#### [openDictationSystemPreferences](#opendictationsystempreferences)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.openDictationSystemPreferences() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Open Dictation System Preferences                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.pause() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the listener.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [registerCommands](#registercommands)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.registerCommands(commands) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Register Commands.                                                                                         |
| **Parameters**                                       | <ul><li>commands - A table of commands.</li></ul> |
| **Returns**                                          | <ul><li>The command titles as a table.</li></ul>          |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.start() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Starts the listener.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful otherwise `false` if an errors occurs.</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the listener.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.os.voice.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Starts or stops the listener.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

