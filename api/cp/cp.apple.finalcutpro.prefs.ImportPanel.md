# [docs](index.md) » cp.apple.finalcutpro.prefs.ImportPanel
---

Import Panel Module.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [ImportPanel](#importpanel)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [analyzeAudioProblems](#analyzeaudioproblems)
 * [analyzeBalanceColor](#analyzebalancecolor)
 * [assignAudioRole](#assignaudiorole)
 * [copyToMediaFolder](#copytomediafolder)
 * [createOptimizedMedia](#createoptimizedmedia)
 * [createProxyMedia](#createproxymedia)
 * [findPeople](#findpeople)
 * [findPeopleConsolidatedResults](#findpeopleconsolidatedresults)
 * [findPeopleSmartCollections](#findpeoplesmartcollections)
 * [iXMLRoles](#ixmlroles)
 * [keywordsFromFinderTags](#keywordsfromfindertags)
 * [keywordsFromFolders](#keywordsfromfolders)
 * [leaveInPlace](#leaveinplace)
 * [mediaLocationGroup](#medialocationgroup)
 * [removeSilentChannels](#removesilentchannels)
 * [separateMonoGroupStereoAudio](#separatemonogroupstereoaudio)
* Methods - API calls which can only be made on an object returned by a constructor
 * [toggleMediaLocation](#togglemedialocation)

## API Documentation

### Constructors

#### [ImportPanel](#importpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel(preferencesDialog) -> ImportPanel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ImportPanel` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>ImportPanel</code> object.</li></ul> |

### Fields

#### [analyzeAudioProblems](#analyzeaudioproblems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.analyzeAudioProblems <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Analyze and fix audio problems" `CheckBox`. |

#### [analyzeBalanceColor](#analyzebalancecolor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.analyzeBalanceColor <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Analyze video for balance color" `CheckBox`. |

#### [assignAudioRole](#assignaudiorole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.assignAudioRole <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Assign Role" `PopUpButton`. |

#### [copyToMediaFolder](#copytomediafolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.copyToMediaFolder <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Copy to library storage location" `RadioButton`. |

#### [createOptimizedMedia](#createoptimizedmedia)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.createOptimizedMedia <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Create optimized media" `CheckBox`. |

#### [createProxyMedia](#createproxymedia)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.createProxyMedia <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Create proxy media" `CheckBox`. |

#### [findPeople](#findpeople)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.findPeople <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Find people" `CheckBox`. |

#### [findPeopleConsolidatedResults](#findpeopleconsolidatedresults)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.findPeopleConsolidatedResults <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Consolidate find people results" `CheckBox`. |

#### [findPeopleSmartCollections](#findpeoplesmartcollections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.findPeopleSmartCollections <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Create Smart Collections after analysis" `CheckBox`. |

#### [iXMLRoles](#ixmlroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.iXMLRoles <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Assign iXML track names if available" `CheckBox`. |

#### [keywordsFromFinderTags](#keywordsfromfindertags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.keywordsFromFinderTags <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Keywords from Finder tags" `CheckBox`. |

#### [keywordsFromFolders](#keywordsfromfolders)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.keywordsFromFolders <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Keywords from folders" `CheckBox`. |

#### [leaveInPlace](#leaveinplace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.leaveInPlace <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Leave files in place" `RadioButton`. |

#### [mediaLocationGroup](#medialocationgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.mediaLocationGroup <cp.ui.RadioGroup>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `RadioGroup` containing the "Copy to library storage location" and "Leave files in place" options. |

#### [removeSilentChannels](#removesilentchannels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.removeSilentChannels <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Remove silent channels" `CheckBox`. |

#### [separateMonoGroupStereoAudio](#separatemonogroupstereoaudio)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel.separateMonoGroupStereoAudio <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Separate mono and group stereo audio" `CheckBox`. |

### Methods

#### [toggleMediaLocation](#togglemedialocation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.ImportPanel:toggleMediaLocation() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A `Statement` that toggles between the "Copy to library storage location" and "Leave files in place" options. |

