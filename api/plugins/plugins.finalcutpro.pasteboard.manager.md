# [docs](index.md) » plugins.finalcutpro.pasteboard.manager
---

Pasteboard Manager.

## API Overview
* Variables - Configurable values
 * [excludedClassnames](#excludedclassnames)
 * [watcherFrequency](#watcherfrequency)
* Functions - API calls offered directly by the extension
 * [copyWithCustomClipName](#copywithcustomclipname)
 * [getClassname](#getclassname)
 * [isClassnameSupported](#isclassnamesupported)
 * [isTimelineClip](#istimelineclip)
 * [overrideNextClipName](#overridenextclipname)
 * [processArray](#processarray)
 * [processContent](#processcontent)
 * [processObject](#processobject)
 * [startWatching](#startwatching)
 * [stopWatching](#stopwatching)
 * [supportsContainedItems](#supportscontaineditems)
 * [unarchiveFCPXData](#unarchivefcpxdata)
 * [unwatch](#unwatch)
 * [watch](#watch)
 * [writeFCPXData](#writefcpxdata)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [watching](#watching)

## API Documentation

### Variables

#### [excludedClassnames](#excludedclassnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.excludedClassnames -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table of data we don't want to count when copying.                                                                                         |

#### [watcherFrequency](#watcherfrequency)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.watcherFrequency -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The Pasteboard Watcher Update frequency.                                                                                         |

### Functions

#### [copyWithCustomClipName](#copywithcustomclipname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.copyWithCustomClipName() -> data | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Reads FCPX Data from the Pasteboard as a binary Plist, if present.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The pasteboard data or `nil`.</li></ul>          |

#### [getClassname](#getclassname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.getClassname(data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a class anem from data                                                                                         |
| **Parameters**                                       | <ul><li>data - The data object to process</li></ul> |
| **Returns**                                          | <ul><li>Class name as string</li></ul>          |

#### [isClassnameSupported](#isclassnamesupported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.isClassnameSupported(classname) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Is the class name supported?                                                                                         |
| **Parameters**                                       | <ul><li>classname - The class name you want to check</li></ul> |
| **Returns**                                          | <ul><li>`true` if the class name is supported otherwise `false`.</li></ul>          |

#### [isTimelineClip](#istimelineclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.isTimelineClip(data) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Is the data a timeline clip.                                                                                         |
| **Parameters**                                       | <ul><li>data - The pasteboard data you want to check.</li></ul> |
| **Returns**                                          | <ul><li>`true` if a timeline clip otherwise `false`.</li></ul>          |

#### [overrideNextClipName](#overridenextclipname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.overrideNextClipName(overrideName) -> None` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Overrides the name for the next clip which is copied from FCPX to the specified                                                                                         |
| **Parameters**                                       | <ul><li>overrideName - The override name.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [processArray](#processarray)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.processArray(data) -> string, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Processes an 'array' table.                                                                                         |
| **Parameters**                                       | <ul><li>data - The data object to process</li></ul> |
| **Returns**                                          | <ul><li>The primary clip name as a string.</li><li>The number of clips as number.</li></ul>          |

#### [processContent](#processcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.processContent(fcpxData, default) -> string, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Searches the Pasteboard binary plist data for the first clip name, and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>fcpxData - The data object to process</li><li>default - The default value</li></ul> |
| **Returns**                                          | <ul><li>Returns the 'default' value if the pasteboard contains a media clip but we could not interpret it, otherwise `nil` if the data did not contain Final Cut Pro Clip data.</li></ul>          |
| **Notes**                                            | <ul><li>Example usage: `local name = mod.findClipName(myFcpxData, "Unknown")`</li></ul>                |

#### [processObject](#processobject)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.processObject(data) -> string, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Processes the provided data object, which should have a '$class' property.                                                                                         |
| **Parameters**                                       | <ul><li>data - The pasteboard data you want to check.</li></ul> |
| **Returns**                                          | <ul><li>The primary clip name as a string.</li><li>The number of clips as number.</li></ul>          |

#### [startWatching](#startwatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.startWatching() -> None` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Start Watching the Pasteboard.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [stopWatching](#stopwatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.stopWatching() -> None` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stop Watching the Pasteboard.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [supportsContainedItems](#supportscontaineditems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.supportsContainedItems(data) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets whether or not the data supports contained items.                                                                                         |
| **Parameters**                                       | <ul><li>data - The data object to process</li></ul> |
| **Returns**                                          | <ul><li>`true` if supported otherwise `false`.</li></ul>          |

#### [unarchiveFCPXData](#unarchivefcpxdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.unarchiveFCPXData(fcpxData) -> data | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unarchive Final Cut Pro data.                                                                                         |
| **Parameters**                                       | <ul><li>fcpxData - The data object to process</li></ul> |
| **Returns**                                          | <ul><li>The unarchived Final Cut Pro Pasteboard data or `nil`.</li></ul>          |

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.unwatch(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stop a watcher.                                                                                         |
| **Parameters**                                       | <ul><li>id - The ID of the watcher you want to stop.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful otherwise `false`.</li></ul>          |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.watch(events) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Watch events.                                                                                         |
| **Parameters**                                       | <ul><li>events - Table of events</li></ul> |
| **Returns**                                          | <ul><li>Table of watchers.</li></ul>          |

#### [writeFCPXData](#writefcpxdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.writeFCPXData(fcpxData, quiet) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Write Final Cut Pro data to Pasteboard.                                                                                         |
| **Parameters**                                       | <ul><li>fcpxData - The data to write</li><li>quiet - Whether or not we should stop/start the watcher.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the operation succeeded, otherwise `false` (which most likely means ownership of the pasteboard has changed).</li></ul>          |

### Fields

#### [watching](#watching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.watching <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Gets whether or not we're watching the pasteboard as a boolean.                                                                                         |

