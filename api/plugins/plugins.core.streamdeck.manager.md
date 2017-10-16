# [docs](index.md) » plugins.core.streamdeck.manager
---

Elgato Stream Deck Manager Plugin.

## API Overview
* Variables - Configurable values
 * [defaultGroup](#defaultgroup)
 * [maxItems](#maxitems)
* Functions - API calls offered directly by the extension
 * [activeGroup](#activegroup)
 * [appWatcherCallback](#appwatchercallback)
 * [buttonCallback](#buttoncallback)
 * [clear](#clear)
 * [discoveryCallback](#discoverycallback)
 * [getAction](#getaction)
 * [getActionHandlerID](#getactionhandlerid)
 * [getActionTitle](#getactiontitle)
 * [getIcon](#geticon)
 * [getLabel](#getlabel)
 * [groupStatus](#groupstatus)
 * [init](#init)
 * [start](#start)
 * [update](#update)
 * [updateAction](#updateaction)
 * [updateIcon](#updateicon)
 * [updateLabel](#updatelabel)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [buttons](#buttons)
 * [enabled](#enabled)

## API Documentation

### Variables

#### [defaultGroup](#defaultgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.defaultGroup -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The default group.                                                                                         |

#### [maxItems](#maxitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.maxItems -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The maximum number of Touch Bar items per group.                                                                                         |

### Functions

#### [activeGroup](#activegroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.activeGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the active group.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns the active group or `manager.defaultGroup` as a string.</li></ul>          |

#### [appWatcherCallback](#appwatchercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.appWatcherCallback(name, event, app) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stream Deck App Watcher Callback                                                                                         |
| **Parameters**                                       | <ul><li>name - A string containing the name of the application</li><li>event - An event type</li><li>app - An `hs.application` object representing the application, or `nil` if the application couldn't be found</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [buttonCallback](#buttoncallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.buttonCallback(object, buttonID, pressed) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stream Deck Button Callback                                                                                         |
| **Parameters**                                       | <ul><li>object - The `hs.streamdeck` userdata object</li><li>buttonID - A number containing the button that was pressed/released</li><li>pressed - A boolean indicating whether the button was pressed (`true`) or released (`false`)</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.clear() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Clears the Touch Bar items.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [discoveryCallback](#discoverycallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.discoveryCallback(connected, object) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stream Deck Discovery Callback                                                                                         |
| **Parameters**                                       | <ul><li>connected - A boolean, `true` if a device was connected, `false` if a device was disconnected</li><li>object - An `hs.streamdeck` object, being the device that was connected/disconnected</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [getAction](#getaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getAction(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Action.                                                                                         |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Action as string</li></ul>          |

#### [getActionHandlerID](#getactionhandlerid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getActionHandlerID(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Action Handler ID.                                                                                         |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Action as string</li></ul>          |

#### [getActionTitle](#getactiontitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getActionTitle(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Action Title.                                                                                         |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Action as string</li></ul>          |

#### [getIcon](#geticon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getIcon(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Icon.                                                                                         |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Icon data as string</li></ul>          |

#### [getLabel](#getlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getLabel(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Label.                                                                                         |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Label as string</li></ul>          |

#### [groupStatus](#groupstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.groupStatus(groupID, status) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a group's visibility status.                                                                                         |
| **Parameters**                                       | <ul><li>groupID - the group you want to update as a string.</li><li>status - the status of the group as a boolean.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.init(deps, env) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Stream Deck Plugin                                                                                         |
| **Parameters**                                       | <ul><li>deps - Dependencies Table</li><li>env - Environment Table</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.start() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the Stream Deck Plugin                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Touch Bar.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [updateAction](#updateaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateAction(button, group, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a Touch Bar action.                                                                                         |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li><li>action - Action as string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [updateIcon](#updateicon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateIcon(button, group, icon) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a Touch Bar icon.                                                                                         |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li><li>icon - Icon Data as string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [updateLabel](#updatelabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateLabel(button, group, label) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a Touch Bar action.                                                                                         |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li><li>label - Label as string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

### Fields

#### [buttons](#buttons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.buttons <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Contains all the saved Touch Bar Buttons                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Enable or disable Touch Bar Support.                                                                                         |

