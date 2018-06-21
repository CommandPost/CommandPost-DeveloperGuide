# [docs](index.md) » plugins.finalcutpro.pasteboard.manager
---

Pasteboard Manager.

## API Overview
* Constants - Useful values which cannot be changed
 * [NUMBER_OF_PASTEBOARD_BUFFERS](#number_of_pasteboard_buffers)
 * [RESTART_DELAY](#restart_delay)
* Variables - Configurable values
 * [excludedClassnames](#excludedclassnames)
 * [WATCHER_FREQUENCY](#watcher_frequency)
* Functions - API calls offered directly by the extension
 * [copyWithCustomClipName](#copywithcustomclipname)
 * [getClassname](#getclassname)
 * [isClassnameSupported](#isclassnamesupported)
 * [isTimelineClip](#istimelineclip)
 * [overrideNextClipName](#overridenextclipname)
 * [processArray](#processarray)
 * [processContent](#processcontent)
 * [processObject](#processobject)
 * [readFCPXData](#readfcpxdata)
 * [restoreFromBuffer](#restorefrombuffer)
 * [saveToBuffer](#savetobuffer)
 * [startWatching](#startwatching)
 * [stopWatching](#stopwatching)
 * [supportsContainedItems](#supportscontaineditems)
 * [unarchiveFCPXData](#unarchivefcpxdata)
 * [unwatch](#unwatch)
 * [watch](#watch)
 * [writeFCPXData](#writefcpxdata)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [buffer](#buffer)
 * [watching](#watching)

## API Documentation

### Constants

#### [NUMBER_OF_PASTEBOARD_BUFFERS](#number_of_pasteboard_buffers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.NUMBER_OF_PASTEBOARD_BUFFERS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Number of Pasteboard Buffers.                                                                                         |

#### [RESTART_DELAY](#restart_delay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.RESTART_DELAY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | How long to wait until we restart any Pasteboard Watchers.                                                                                         |

### Variables

#### [excludedClassnames](#excludedclassnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.excludedClassnames -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of data we don't want to count when copying.                                                                                         |

#### [WATCHER_FREQUENCY](#watcher_frequency)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.WATCHER_FREQUENCY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The Pasteboard Watcher Update frequency.                                                                                         |

### Functions

#### [copyWithCustomClipName](#copywithcustomclipname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.copyWithCustomClipName() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Copy with custom label.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [getClassname](#getclassname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.getClassname(data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a class anem from data                                                                                         |
| **Parameters**                                       |  * data - The data object to process                                       |
| **Returns**                                          |  * Class name as string                                                |

#### [isClassnameSupported](#isclassnamesupported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.isClassnameSupported(classname) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Is the class name supported?                                                                                         |
| **Parameters**                                       |  * classname - The class name you want to check                                       |
| **Returns**                                          |  * `true` if the class name is supported otherwise `false`.                                                |

#### [isTimelineClip](#istimelineclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.isTimelineClip(data) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Is the data a timeline clip.                                                                                         |
| **Parameters**                                       |  * data - The pasteboard data you want to check.                                       |
| **Returns**                                          |  * `true` if a timeline clip otherwise `false`.                                                |

#### [overrideNextClipName](#overridenextclipname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.overrideNextClipName(overrideName) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Overrides the name for the next clip which is copied from FCPX to the specified                                                                                         |
| **Parameters**                                       |  * overrideName - The override name.                                       |
| **Returns**                                          |  * None                                                |

#### [processArray](#processarray)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.processArray(data) -> string, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Processes an 'array' table.                                                                                         |
| **Parameters**                                       |  * data - The data object to process                                       |
| **Returns**                                          |  * The primary clip name as a string. * The number of clips as number.                                                |

#### [processContent](#processcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.processContent(fcpxData, default) -> string, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Searches the Pasteboard binary plist data for the first clip name, and returns it.                                                                                         |
| **Parameters**                                       |  * fcpxData - The data object to process * default - The default value                                       |
| **Returns**                                          |  * Returns the 'default' value if the pasteboard contains a media clip but we could not interpret it, otherwise `nil` if the data did not contain Final Cut Pro Clip data.                                                |
| **Notes**                                            |  * Example usage: `local name = mod.findClipName(myFcpxData, "Unknown")`                                                      |

#### [processObject](#processobject)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.processObject(data) -> string, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Processes the provided data object, which should have a '$class' property.                                                                                         |
| **Parameters**                                       |  * data - The pasteboard data you want to check.                                       |
| **Returns**                                          |  * The primary clip name as a string. * The number of clips as number.                                                |

#### [readFCPXData](#readfcpxdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.readFCPXData() -> data | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Reads Final Cut Pro Data from the Pasteboard as a binary Property List, if present.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The pasteboard data or `nil`.                                                |

#### [restoreFromBuffer](#restorefrombuffer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.restoreFromBuffer(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Restore a Pasteboard item from the buffer.                                                                                         |
| **Parameters**                                       |  * id - The ID of the buffer item.                                       |
| **Returns**                                          |  * None                                                |

#### [saveToBuffer](#savetobuffer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.saveToBuffer(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Save a Pasteboard item to the buffer.                                                                                         |
| **Parameters**                                       |  * id - The ID of the buffer item.                                       |
| **Returns**                                          |  * None                                                |

#### [startWatching](#startwatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.startWatching() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Start Watching the Pasteboard.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [stopWatching](#stopwatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.stopWatching() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stop Watching the Pasteboard.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [supportsContainedItems](#supportscontaineditems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.supportsContainedItems(data) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets whether or not the data supports contained items.                                                                                         |
| **Parameters**                                       |  * data - The data object to process                                       |
| **Returns**                                          |  * `true` if supported otherwise `false`.                                                |

#### [unarchiveFCPXData](#unarchivefcpxdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.unarchiveFCPXData(fcpxData) -> data | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unarchive Final Cut Pro data.                                                                                         |
| **Parameters**                                       |  * fcpxData - The data object to process                                       |
| **Returns**                                          |  * The unarchived Final Cut Pro Pasteboard data or `nil`.                                                |

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.unwatch(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stop a watcher.                                                                                         |
| **Parameters**                                       |  * id - The ID of the watcher you want to stop.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.watch(events) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Watch events.                                                                                         |
| **Parameters**                                       |  * events - Table of events                                       |
| **Returns**                                          |  * Table of watchers.                                                |

#### [writeFCPXData](#writefcpxdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.writeFCPXData(fcpxData, quiet) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Write Final Cut Pro data to Pasteboard.                                                                                         |
| **Parameters**                                       |  * fcpxData - The data to write * quiet - Whether or not we should stop/start the watcher.                                       |
| **Returns**                                          |  * `true` if the operation succeeded, otherwise `false` (which most likely means ownership of the pasteboard has changed).                                                |

### Fields

#### [buffer](#buffer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.buffer <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Contains the Pasteboard Buffer.                                                                                         |

#### [watching](#watching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.watching <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Gets whether or not we're watching the pasteboard as a boolean.                                                                                         |

