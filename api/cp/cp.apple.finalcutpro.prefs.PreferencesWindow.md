# [docs](index.md) » cp.apple.finalcutpro.prefs.PreferencesWindow
---

Preferences Window Module.

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [editingPanel](#editingpanel)
 * [generalPanel](#generalpanel)
 * [importPanel](#importpanel)
 * [playbackPanel](#playbackpanel)
 * [title](#title)
 * [toolbar](#toolbar)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doHide](#dohide)
 * [doShow](#doshow)
 * [hide](#hide)
 * [show](#show)

## API Documentation

### Fields

#### [editingPanel](#editingpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.editingPanel <EditingPanel>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `EditingPanel` for the Preferences Window. |

#### [generalPanel](#generalpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.generalPanel <GeneralPanel>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `GeneralPanel` for the Preferences Window. |

#### [importPanel](#importpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.importPanel <ImportPanel>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `ImportPanel` for the Preferences Window. |

#### [playbackPanel](#playbackpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.playbackPanel <PlaybackPanel>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `PlaybackPanel` for the Preferences Window. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.title <cp.ui.StaticText>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `StaticText` for the Preferences Window title. |

#### [toolbar](#toolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow.toolbar <cp.ui.Toolbar>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `Toolbar` for the Preferences Window. |

### Methods

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A `Statement` that attempts to hide the Preferences window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>.</li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A `Statement` that attempts to show the Preferences window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow:hide() -> PreferencesWindow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to hide the Preferences window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The same <code>PreferencesWindow</code>, for chaining.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.PreferencesWindow:show() -> PreferencesWindow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to show the Preferences window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The same <code>PreferencesWindow</code>, for chaining.</li></ul> |

