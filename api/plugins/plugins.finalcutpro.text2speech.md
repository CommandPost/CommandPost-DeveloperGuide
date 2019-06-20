# [docs](index.md) » plugins.finalcutpro.text2speech
---

Text to Speech Plugin.

## API Overview
* Constants - Useful values which cannot be changed
 * [copyToMediaFolder](#copytomediafolder)
* Variables - Configurable values
 * [addTextToNotesFieldAfterImport](#addtexttonotesfieldafterimport)
 * [createRoleForVoice](#createroleforvoice)
 * [currentIncrementalNumber](#currentincrementalnumber)
 * [customPrefix](#customprefix)
 * [deleteFileAfterImport](#deletefileafterimport)
 * [enableCustomPrefix](#enablecustomprefix)
 * [includeTextInFilename](#includetextinfilename)
 * [insertIntoTimeline](#insertintotimeline)
 * [path](#path)
 * [recentText](#recenttext)
 * [replaceSpaceWithUnderscore](#replacespacewithunderscore)
 * [tag](#tag)
 * [useUnderscore](#useunderscore)
 * [voice](#voice)
* Functions - API calls offered directly by the extension
 * [chooseFolder](#choosefolder)
 * [insertFromPasteboard](#insertfrompasteboard)
 * [show](#show)

## API Documentation

### Constants

#### [copyToMediaFolder](#copytomediafolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.copyToMediaFolder <cp.prop: boolean; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Copy to Media Folder Preferences Key. |

### Variables

#### [addTextToNotesFieldAfterImport](#addtexttonotesfieldafterimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.addTextToNotesFieldAfterImport` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Option to Add Text to Notes Field After Importing |

#### [createRoleForVoice](#createroleforvoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.createRoleForVoice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Boolean that sets whether or not a tag should be added for the voice. |

#### [currentIncrementalNumber](#currentincrementalnumber)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.currentIncrementalNumber` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Current Incremental Number as number |

#### [customPrefix](#customprefix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.customPrefix` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | String which contains the custom prefix. |

#### [deleteFileAfterImport](#deletefileafterimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.deleteFileAfterImport` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Delete File After Import |

#### [enableCustomPrefix](#enablecustomprefix)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.enableCustomPrefix` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Boolean that sets whether or not a custom prefix for the generated filename is enabled. |

#### [includeTextInFilename](#includetextinfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.includeTextInFilename` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Includes the entered text in the filename |

#### [insertIntoTimeline](#insertintotimeline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.insertIntoTimeline` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Boolean that sets whether or not new generated voice file are automatically added to the timeline or not. |

#### [path](#path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.path` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Text to Speech Path for generated files. |

#### [recentText](#recenttext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.recentText` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table of recent items in Text to Speech Search. |

#### [replaceSpaceWithUnderscore](#replacespacewithunderscore)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.replaceSpaceWithUnderscore` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Replace Space with Underscore |

#### [tag](#tag)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.tag` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Tag that will be added to generated voice overs. |

#### [useUnderscore](#useunderscore)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.useUnderscore` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | If `true` then an underscore will be used in the Custom Prefix filename otherwise a dash will be used. |

#### [voice](#voice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.voice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Text to Speech Voice. |

### Functions

#### [chooseFolder](#choosefolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.chooseFolder() -> string or false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Prompts the user to choose a folder for the Text to Speech Tool. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string of the selected path or <code>false</code> if cancelled.</li></ul> |

#### [insertFromPasteboard](#insertfrompasteboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.insertFromPasteboard() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Inserts Text to Speech by reading the Pasteboard. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.text2speech.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Shows the Text to Speech Chooser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

