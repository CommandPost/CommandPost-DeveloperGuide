# [docs](index.md) » plugins.core.touchbar.manager
---

Touch Bar Manager Plugin.
This handles both the Virtual Touch Bar and adding items to the physical Touch Bar.

## Submodules
 * [plugins.core.touchbar.manager.virtual](plugins.core.touchbar.manager.virtual.md)
 * [plugins.core.touchbar.manager.widgets](plugins.core.touchbar.manager.widgets.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_GROUP](#default_group)
 * [FILE_NAME](#file_name)
 * [FOLDER_NAME](#folder_name)
* Variables - Configurable values
 * [closeBox](#closebox)
 * [maxItems](#maxitems)
 * [numberOfSubGroups](#numberofsubgroups)
* Functions - API calls offered directly by the extension
 * [activeGroup](#activegroup)
 * [activeSubGroup](#activesubgroup)
 * [clear](#clear)
 * [getAction](#getaction)
 * [getActionHandlerID](#getactionhandlerid)
 * [getActionTitle](#getactiontitle)
 * [getIcon](#geticon)
 * [getLabel](#getlabel)
 * [groupStatus](#groupstatus)
 * [incrementActiveSubGroup](#incrementactivesubgroup)
 * [start](#start)
 * [stop](#stop)
 * [toggle](#toggle)
 * [touchBar](#touchbar)
 * [update](#update)
 * [updateAction](#updateaction)
 * [updateIcon](#updateicon)
 * [updateLabel](#updatelabel)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [buttons](#buttons)
 * [enabled](#enabled)
 * [supported](#supported)

## API Documentation

### Constants

#### [DEFAULT_GROUP](#default_group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.DEFAULT_GROUP -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default group.                                                                                         |

#### [FILE_NAME](#file_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.FILE_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | File name of settings file.                                                                                         |

#### [FOLDER_NAME](#folder_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.FOLDER_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Folder Name where settings file is contained.                                                                                         |

### Variables

#### [closeBox](#closebox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.closeBox -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | An optional boolean, specifying whether or not the system                                                                                         |

#### [maxItems](#maxitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.maxItems -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The maximum number of Touch Bar items per group.                                                                                         |

#### [numberOfSubGroups](#numberofsubgroups)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.numberOfSubGroups -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The number of Sub Groups per Touch Bar Group.                                                                                         |

### Functions

#### [activeGroup](#activegroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.activeGroup() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the active group.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Returns the active group or `manager.defaultGroup` as a string.                                                |

#### [activeSubGroup](#activesubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.activeSubGroup() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the active sub-group.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Returns the active sub group as string                                                |

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.clear() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Clears the Touch Bar items.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [getAction](#getaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.getAction(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Action.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Action as string                                                |

#### [getActionHandlerID](#getactionhandlerid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.getActionHandlerID(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Action Handler ID.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Action as string                                                |

#### [getActionTitle](#getactiontitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.getActionTitle(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Action Title.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Action as string                                                |

#### [getIcon](#geticon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.getIcon(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Icon.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Icon data as string                                                |

#### [getLabel](#getlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.getLabel(button, group) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a specific Touch Bar Label.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string                                       |
| **Returns**                                          |  * Label as string                                                |

#### [groupStatus](#groupstatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.groupStatus(groupID, status) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a group's visibility status.                                                                                         |
| **Parameters**                                       |  * groupID - the group you want to update as a string. * status - the status of the group as a boolean.                                       |
| **Returns**                                          |  * None                                                |

#### [incrementActiveSubGroup](#incrementactivesubgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.incrementActiveSubGroup() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Increments the active sub-group                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.start() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Starts the CommandPost Touch Bar module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the CommandPost Touch Bar module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.toggle() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles the CommandPost Touch Bar module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [touchBar](#touchbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.touchBar() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the `hs._asm.undocumented.touchbar` object if it exists.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `hs._asm.undocumented.touchbar`                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Touch Bar.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [updateAction](#updateaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.updateAction(button, group, action) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a Touch Bar action.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string * action - Action as string                                       |
| **Returns**                                          |  * None                                                |

#### [updateIcon](#updateicon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.updateIcon(button, group, icon) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a Touch Bar icon.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string * icon - Icon Data as string                                       |
| **Returns**                                          |  * None                                                |

#### [updateLabel](#updatelabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.updateLabel(button, group, label) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates a Touch Bar action.                                                                                         |
| **Parameters**                                       |  * button - Button ID as string * group - Group ID as string * label - Label as string                                       |
| **Returns**                                          |  * None                                                |

### Fields

#### [buttons](#buttons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.buttons <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Contains all the saved Touch Bar Buttons                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Enable or disable Touch Bar Support.                                                                                         |

#### [supported](#supported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.touchbar.manager.supported <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the Touch Bar is supported on this version of macOS.                                                                                         |

