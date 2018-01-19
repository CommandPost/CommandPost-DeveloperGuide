# [docs](index.md) » plugins.finalcutpro.text2speech
---

Text to Speech Plugin.

## API Overview
* Variables - Configurable values
 * [createRoleForVoice](#createroleforvoice)
 * [currentIncrementalNumber](#currentincrementalnumber)
 * [customPrefix](#customprefix)
 * [enableCustomPrefix](#enablecustomprefix)
 * [insertIntoTimeline](#insertintotimeline)
 * [path](#path)
 * [recentText](#recenttext)
 * [replaceSpaceWithUnderscore](#replacespacewithunderscore)
 * [tag](#tag)
 * [useUnderscore](#useunderscore)
 * [voice](#voice)
* Functions - API calls offered directly by the extension
 * [chooseFolder](#choosefolder)
 * [show](#show)

## API Documentation

### Variables

#### [createRoleForVoice](#createroleforvoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.createRoleForVoice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Boolean that sets whether or not a tag should be added for the voice.                                                                                         |

#### [currentIncrementalNumber](#currentincrementalnumber)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.currentIncrementalNumber` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Current Incremental Number as number                                                                                         |

#### [customPrefix](#customprefix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.customPrefix` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | String which contains the custom prefix.                                                                                         |

#### [enableCustomPrefix](#enablecustomprefix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.enableCustomPrefix` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Boolean that sets whether or not a custom prefix for the generated filename is enabled.                                                                                         |

#### [insertIntoTimeline](#insertintotimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.insertIntoTimeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Boolean that sets whether or not new generated voice file are automatically added to the timeline or not.                                                                                         |

#### [path](#path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.path` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Text to Speech Path for generated files.                                                                                         |

#### [recentText](#recenttext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.recentText` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of recent items in Text to Speech Search.                                                                                         |

#### [replaceSpaceWithUnderscore](#replacespacewithunderscore)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.replaceSpaceWithUnderscore` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Replace Space with Underscore                                                                                         |

#### [tag](#tag)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.tag` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Tag that will be added to generated voice overs.                                                                                         |

#### [useUnderscore](#useunderscore)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.useUnderscore` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | If `true` then an underscore will be used in the Custom Prefix filename otherwise a dash will be used.                                                                                         |

#### [voice](#voice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.voice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Text to Speech Voice.                                                                                         |

### Functions

#### [chooseFolder](#choosefolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.chooseFolder() -> string or false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Prompts the user to choose a folder for the Text to Speech Tool.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string of the selected path or `false` if cancelled.</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the Text to Speech Chooser.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

