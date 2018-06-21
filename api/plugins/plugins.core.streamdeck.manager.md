# [docs](index.md) » plugins.core.streamdeck.manager
---

Elgato Stream Deck Manager Plugin.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_GROUP](#default_group)
 * [FILE_NAME](#file_name)
 * [FOLDER_NAME](#folder_name)
* Variables - Configurable values
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
 * [enabled](#enabled)

## API Documentation

### Constants

#### [DEFAULT_GROUP](#default_group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.DEFAULT_GROUP -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default group.                                                                                         |

#### [FILE_NAME](#file_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.FILE_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | File name of settings file.                                                                                         |

#### [FOLDER_NAME](#folder_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.FOLDER_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Folder Name where settings file is contained.                                                                                         |

### Variables

#### [maxItems](#maxitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.maxItems -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The maximum number of Stream Deck items per group.                                                                                         |

### Functions

#### [activeGroup](#activegroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.activeGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the active group.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Returns the active group or `manager.defaultGroup` as a string.                                                |

#### [appWatcherCallback](#appwatchercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.appWatcherCallback(name, event, app) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stream Deck App Watcher Callback                                                                                         |
| **Parameters**                                       |  * name - A string containing the name of the application * event - An event type * app - An `hs.application` object representing the application, or `nil` if the application couldn't be found                                       |
| **Returns**                                          |  * None                                                |

#### [buttonCallback](#buttoncallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.buttonCallback(object, buttonID, pressed) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stream Deck Button Callback                                                                                         |
| **Parameters**                                       |  * object - The `hs.streamdeck` userdata object * buttonID - A number containing the button that was pressed/released * pressed - A boolean indicating whether the button was pressed (`true`) or released (`false`)                                       |
| **Returns**                                          |  * None                                                |

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.clear() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Clears the Stream Deck items.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [discoveryCallback](#discoverycallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.discoveryCallback(connected, object) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stream Deck Discovery Callback                                                                                         |
| **Parameters**                                       |  * connected - A boolean, `true` if a device was connected, `false` if a device was disconnected * object - An `hs.streamdeck` object, being the device that was connected/disconnected                                       |
| **Returns**                                          |  * None                                                |

#### [getAction](#getaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getAction(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Stream Deck Action.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Action as string                                                |

#### [getActionHandlerID](#getactionhandlerid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getActionHandlerID(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Stream Deck Action Handler ID.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Action as string                                                |

#### [getActionTitle](#getactiontitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getActionTitle(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Stream Deck Action Title.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Action as string                                                |

#### [getIcon](#geticon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getIcon(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Stream Deck Icon.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Icon data as string                                                |

#### [getLabel](#getlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getLabel(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Stream Deck Label.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Label as string                                                |

#### [groupStatus](#groupstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.groupStatus(groupID, status) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a group's visibility status.                                                                                         |
| **Parameters**                                       |  * groupID - the group you want to update as a string. * status - the status of the group as a boolean.                                       |
| **Returns**                                          |  * None                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.init(deps, env) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Stream Deck Plugin                                                                                         |
| **Parameters**                                       |  * deps - Dependencies Table * env - Environment Table                                       |
| **Returns**                                          |  * None                                                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.start() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the Stream Deck Plugin                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Stream Deck.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [updateAction](#updateaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateAction(button, group, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a Stream Deck action.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string * action - Action as string                                       |
| **Returns**                                          |  * None                                                |

#### [updateIcon](#updateicon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateIcon(button, group, icon) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a Stream Deck icon.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string * icon - Icon Data as string                                       |
| **Returns**                                          |  * None                                                |

#### [updateLabel](#updatelabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateLabel(button, group, label) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a Stream Deck action.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string * label - Label as string                                       |
| **Returns**                                          |  * None                                                |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Enable or disable Stream Deck Support.                                                                                         |

