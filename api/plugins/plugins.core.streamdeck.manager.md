# [docs](index.md) » plugins.core.streamdeck.manager
---

Elgato Stream Deck Manager Plugin.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_GROUP](#default_group)
* Variables - Configurable values
 * [maxItems](#maxitems)
 * [numberOfSubGroups](#numberofsubgroups)
* Functions - API calls offered directly by the extension
 * [activeGroup](#activegroup)
 * [activeSubGroup](#activesubgroup)
 * [appWatcherCallback](#appwatchercallback)
 * [buttonCallback](#buttoncallback)
 * [clear](#clear)
 * [discoveryCallback](#discoverycallback)
 * [forceGroupChange](#forcegroupchange)
 * [getAction](#getaction)
 * [getActionHandlerID](#getactionhandlerid)
 * [getActionTitle](#getactiontitle)
 * [getBankLabel](#getbanklabel)
 * [getIcon](#geticon)
 * [getLabel](#getlabel)
 * [gotoSubGroup](#gotosubgroup)
 * [groupStatus](#groupstatus)
 * [incrementActiveSubGroup](#incrementactivesubgroup)
 * [nextSubGroup](#nextsubgroup)
 * [previousSubGroup](#previoussubgroup)
 * [start](#start)
 * [update](#update)
 * [updateAction](#updateaction)
 * [updateBankLabel](#updatebanklabel)
 * [updateIcon](#updateicon)
 * [updateLabel](#updatelabel)
 * [updateOrder](#updateorder)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)

## API Documentation

### Constants

#### [DEFAULT_GROUP](#default_group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.DEFAULT_GROUP -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The default group. |

### Variables

#### [maxItems](#maxitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.maxItems -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The maximum number of Stream Deck items per group. |

#### [numberOfSubGroups](#numberofsubgroups)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.numberOfSubGroups -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The number of Sub Groups per Touch Bar Group. |

### Functions

#### [activeGroup](#activegroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.activeGroup() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the active group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns the active group or <code>manager.defaultGroup</code> as a string.</li></ul> |

#### [activeSubGroup](#activesubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.activeSubGroup() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the active sub-group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns the active sub group as string</li></ul> |

#### [appWatcherCallback](#appwatchercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.appWatcherCallback(name, event, app) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stream Deck App Watcher Callback |
| **Parameters**                                       | <ul><li>name - A string containing the name of the application</li><li>event - An event type</li><li>app - An <code>hs.application</code> object representing the application, or <code>nil</code> if the application couldn't be found</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [buttonCallback](#buttoncallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.buttonCallback(object, buttonID, pressed) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stream Deck Button Callback |
| **Parameters**                                       | <ul><li>object - The <code>hs.streamdeck</code> userdata object</li><li>buttonID - A number containing the button that was pressed/released</li><li>pressed - A boolean indicating whether the button was pressed (<code>true</code>) or released (<code>false</code>)</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.clear() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Clears the Stream Deck items. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [discoveryCallback](#discoverycallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.discoveryCallback(connected, object) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stream Deck Discovery Callback |
| **Parameters**                                       | <ul><li>connected - A boolean, <code>true</code> if a device was connected, <code>false</code> if a device was disconnected</li><li>object - An <code>hs.streamdeck</code> object, being the device that was connected/disconnected</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [forceGroupChange](#forcegroupchange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.forceGroupChange(combinedGroupAndSubGroupID) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Loads a specific sub-group. |
| **Parameters**                                       | <ul><li>combinedGroupAndSubGroupID - The group and subgroup as a single string.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getAction](#getaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getAction(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a specific Touch Bar Action. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Action as string</li></ul> |

#### [getActionHandlerID](#getactionhandlerid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getActionHandlerID(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a specific Touch Bar Action Handler ID. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Action as string</li></ul> |

#### [getActionTitle](#getactiontitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getActionTitle(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a specific Touch Bar Action Title. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Action as string</li></ul> |

#### [getBankLabel](#getbanklabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getBankLabel(group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a specific Touch Bar Bank Label. |
| **Parameters**                                       | <ul><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Label as string</li></ul> |

#### [getIcon](#geticon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getIcon(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a specific Touch Bar Icon. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Icon data as string</li></ul> |

#### [getLabel](#getlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getLabel(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a specific Touch Bar Label. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>Label as string</li></ul> |

#### [gotoSubGroup](#gotosubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.gotoSubGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Loads a specific sub-group. |
| **Parameters**                                       | <ul><li>id - The ID of the sub-group.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [groupStatus](#groupstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.groupStatus(groupID, status) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates a group's visibility status. |
| **Parameters**                                       | <ul><li>groupID - the group you want to update as a string.</li><li>status - the status of the group as a boolean.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [incrementActiveSubGroup](#incrementactivesubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.incrementActiveSubGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Increments the active sub-group |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [nextSubGroup](#nextsubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.nextSubGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Goes to the next sub-group for the active group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [previousSubGroup](#previoussubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.previousSubGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Goes to the previous sub-group for the active group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.start() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stops the Stream Deck Plugin |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the Stream Deck. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateAction](#updateaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateAction(button, group, action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates a Touch Bar action. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li><li>actionTitle - Action Title as string</li><li>handlerID - Handler ID as string</li><li>action - Action as table</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully updated, or <code>false</code> if a duplicate entry was found</li></ul> |

#### [updateBankLabel](#updatebanklabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateBankLabel(group, label) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates a Touch Bar Bank Label. |
| **Parameters**                                       | <ul><li>group - Group ID as string</li><li>label - Label as string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateIcon](#updateicon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateIcon(button, group, icon) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates a Touch Bar icon. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li><li>icon - Icon Data as string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateLabel](#updatelabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateLabel(button, group, label) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates a Touch Bar label. |
| **Parameters**                                       | <ul><li>button - Button ID as string</li><li>group - Group ID as string</li><li>label - Label as string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateOrder](#updateorder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.updateOrder(direction, button, group) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Shifts a Touch Bar button either up or down. |
| **Parameters**                                       | <ul><li>direction - Either "up" or "down"</li><li>button - Button ID as string</li><li>group - Group ID as string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable Stream Deck Support. |

