# [docs](index.md) » plugins.finalcutpro.text2speech
---

Text to Speech Plugin.

## API Overview
* Variables - Configurable values
 * [path](#path)
 * [recentText](#recenttext)
 * [voice](#voice)
* Functions - API calls offered directly by the extension
 * [chooseFolder](#choosefolder)
 * [show](#show)

## API Documentation

### Variables

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

