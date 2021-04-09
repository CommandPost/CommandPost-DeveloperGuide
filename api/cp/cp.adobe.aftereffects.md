# [docs](index.md) » cp.adobe.aftereffects
---

Adobe After Effects Extension

## Submodules
 * [cp.adobe.aftereffects.app](cp.adobe.aftereffects.app.md)
 * [cp.adobe.aftereffects.shortcuts](cp.adobe.aftereffects.shortcuts.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [preferences](#preferences)
* Functions - API calls offered directly by the extension
 * [allowScriptsToWriteFilesAndAccessNetwork](#allowscriptstowritefilesandaccessnetwork)
 * [preferencesFilePath](#preferencesfilepath)
 * [preferencesPath](#preferencespath)
 * [refreshPreferences](#refreshpreferences)
 * [shortcutsPreferences](#shortcutspreferences)
 * [shortcutsPreferencesPath](#shortcutspreferencespath)

## API Documentation

### Constants

#### [preferences](#preferences)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.adobe.aftereffects.preferences <cp.app.prefs>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The `cp.app.prefs` for After Effects. |

### Functions

#### [allowScriptsToWriteFilesAndAccessNetwork](#allowscriptstowritefilesandaccessnetwork)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.adobe.aftereffects:allowScriptsToWriteFilesAndAccessNetwork() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Is "Allow Scripts to Write Files and Access Network" enabled in After Effects Preferences? |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean</li></ul> |

#### [preferencesFilePath](#preferencesfilepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.adobe.aftereffects:preferencesFilePath() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | The path to the main Preferences file. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [preferencesPath](#preferencespath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.adobe.aftereffects:preferencesPath() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | The path to After Effects Preferences folder. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string or <code>nil</code> if no path can be found.</li></ul> |

#### [refreshPreferences](#refreshpreferences)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.adobe.aftereffects:refreshPreferences() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | If After Effects is running, this forces the preferences file to be saved to disk. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [shortcutsPreferences](#shortcutspreferences)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.adobe.aftereffects:shortcutsPreferences() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a table of all the active After Effects keyboard shortcuts. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [shortcutsPreferencesPath](#shortcutspreferencespath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.adobe.aftereffects:shortcutsPreferencesPath() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the active shortcut key preferences file path. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

