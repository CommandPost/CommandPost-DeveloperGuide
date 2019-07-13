# [docs](index.md) » plugins.core.loupedeck.prefs
---

Loupedeck Preferences Panel

## Submodules
 * [plugins.core.loupedeck.prefs.default](plugins.core.loupedeck.prefs.default.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [updateAction](#updateaction)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [lastGroup](#lastgroup)
 * [lastIsButton](#lastisbutton)
 * [lastLabel](#lastlabel)
 * [lastNote](#lastnote)

## API Documentation

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeck.prefs.init(deps, env) -> module` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialise the Module. |
| **Parameters**                                       | <ul><li>deps - Dependancies Table</li><li>env - Environment Table</li></ul> |
| **Returns**                                          | <ul><li>The Module</li></ul> |

#### [updateAction](#updateaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeck.prefs.updateAction(button, group, actionTitle, handlerID, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates a Loupedeck action. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li><li>actionTitle - Action Title as string</li><li>handlerID - Handler ID as string</li><li>action - Action in a table</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [lastGroup](#lastgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeck.prefs.lastGroup <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Last group used in the Preferences Drop Down. |

#### [lastIsButton](#lastisbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeck.prefs.lastIsButton <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Whether or not the last selected item in the Preferences was a button. |

#### [lastLabel](#lastlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeck.prefs.lastLabel <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Last label used in the Preferences panel. |

#### [lastNote](#lastnote)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeck.prefs.lastNote <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Last note used in the Preferences panel. |

