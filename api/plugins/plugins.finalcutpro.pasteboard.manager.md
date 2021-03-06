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
 * [doDecodeBuffer](#dodecodebuffer)
 * [doRestoreFromBuffer](#dorestorefrombuffer)
 * [doSaveToBuffer](#dosavetobuffer)
 * [doWaitForData](#dowaitfordata)
 * [doWaitForFreshData](#dowaitforfreshdata)
 * [getClassname](#getclassname)
 * [isTimelineClip](#istimelineclip)
 * [ninjaPasteboardCopy](#ninjapasteboardcopy)
 * [overrideNextClipName](#overridenextclipname)
 * [processArray](#processarray)
 * [processContent](#processcontent)
 * [processObject](#processobject)
 * [readFCPXData](#readfcpxdata)
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
| **Type**                                             | Constant |
| **Description**                                      | Number of Pasteboard Buffers. |

#### [RESTART_DELAY](#restart_delay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.RESTART_DELAY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | How long to wait until we restart any Pasteboard Watchers in milliseconds. |

### Variables

#### [excludedClassnames](#excludedclassnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.excludedClassnames -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table of data we don't want to count when copying. |

#### [WATCHER_FREQUENCY](#watcher_frequency)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.WATCHER_FREQUENCY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The Pasteboard Watcher Update frequency. |

### Functions

#### [copyWithCustomClipName](#copywithcustomclipname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.copyWithCustomClipName() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Copy with custom label. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [doDecodeBuffer](#dodecodebuffer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.doDecodeBuffer(id) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which decodes the buffer with the specified ID. |
| **Parameters**                                       | <ul><li>id        - The ID to decode</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a> that sends the decoded buffer, or throws an error if not available.</li></ul> |

#### [doRestoreFromBuffer](#dorestorefrombuffer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.doRestoreFromBuffer(id) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which restore a Pasteboard item from the buffer. |
| **Parameters**                                       | <ul><li>id - The ID of the buffer item.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |

#### [doSaveToBuffer](#dosavetobuffer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.doSaveToBuffer(id) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which saves a Pasteboard item to the buffer. |
| **Parameters**                                       | <ul><li>id - The ID of the buffer item.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |

#### [doWaitForData](#dowaitfordata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.doWaitForData(newData) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which waits for up to 10 seconds for new data to appear |
| **Parameters**                                       | <ul><li>newData - The new Pasteboard data.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |

#### [doWaitForFreshData](#dowaitforfreshdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.doWaitForFreshData(oldData) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which waits for up to 10 seconds for new data to copy |
| **Parameters**                                       | <ul><li>oldData - The original Pasteboard data.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |

#### [getClassname](#getclassname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.getClassname(data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a class anem from data |
| **Parameters**                                       | <ul><li>data - The data object to process</li></ul> |
| **Returns**                                          | <ul><li>Class name as string</li></ul> |

#### [isTimelineClip](#istimelineclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.isTimelineClip(data) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Is the data a timeline clip. |
| **Parameters**                                       | <ul><li>data - The pasteboard data you want to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if a timeline clip otherwise <code>false</code>.</li></ul> |

#### [ninjaPasteboardCopy](#ninjapasteboardcopy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.ninjaPasteboardCopy() -> boolean, data` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Ninja Pasteboard Copy. Copies something to the pasteboard, then restores the original pasteboard item. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code></li><li>The pasteboard data</li></ul> |

#### [overrideNextClipName](#overridenextclipname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.overrideNextClipName(overrideName) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Overrides the name for the next clip which is copied from FCPX to the specified |
| **Parameters**                                       | <ul><li>overrideName - The override name.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [processArray](#processarray)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.processArray(data) -> string, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Processes an 'array' table. |
| **Parameters**                                       | <ul><li>data - The data object to process</li></ul> |
| **Returns**                                          | <ul><li>The primary clip name as a string.</li><li>The number of clips as number.</li></ul> |

#### [processContent](#processcontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.processContent(fcpxData, default) -> string, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Searches the Pasteboard binary plist data for the first clip name, and returns it. |
| **Parameters**                                       | <ul><li>fcpxData - The data object to process</li><li>default - The default value</li></ul> |
| **Returns**                                          | <ul><li>Returns the 'default' value if the pasteboard contains a media clip but we could not interpret it, otherwise <code>nil</code> if the data did not contain Final Cut Pro Clip data.</li></ul> |
| **Notes**                                            | <ul><li>Example usage: <code>local name = mod.findClipName(myFcpxData, "Unknown")</code></li></ul> |

#### [processObject](#processobject)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.processObject(data) -> string, number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Processes the provided data object, which should have a '$class' property. |
| **Parameters**                                       | <ul><li>data - The pasteboard data you want to check.</li></ul> |
| **Returns**                                          | <ul><li>The primary clip name as a string.</li><li>The number of clips as number.</li></ul> |

#### [readFCPXData](#readfcpxdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.readFCPXData() -> data | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Reads Final Cut Pro Data from the Pasteboard as a binary Property List, if present. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The pasteboard data or <code>nil</code>.</li></ul> |

#### [startWatching](#startwatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.startWatching() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Start Watching the Pasteboard. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [stopWatching](#stopwatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.stopWatching() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stop Watching the Pasteboard. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [supportsContainedItems](#supportscontaineditems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.supportsContainedItems(data) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets whether or not the data supports contained items. |
| **Parameters**                                       | <ul><li>data - The data object to process</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if supported otherwise <code>false</code>.</li></ul> |

#### [unarchiveFCPXData](#unarchivefcpxdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.unarchiveFCPXData(fcpxData) -> data | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Unarchive Final Cut Pro data. |
| **Parameters**                                       | <ul><li>fcpxData - The data object to process</li></ul> |
| **Returns**                                          | <ul><li>The unarchived Final Cut Pro Pasteboard data or <code>nil</code>.</li></ul> |

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.unwatch(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stop a watcher. |
| **Parameters**                                       | <ul><li>id - The ID of the watcher you want to stop.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.watch(events) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Watch events. |
| **Parameters**                                       | <ul><li>events - Table of events</li></ul> |
| **Returns**                                          | <ul><li>Table of watchers.</li></ul> |

#### [writeFCPXData](#writefcpxdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.writeFCPXData(fcpxData, quiet) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Write Final Cut Pro data to Pasteboard. |
| **Parameters**                                       | <ul><li>fcpxData - The data to write</li><li>quiet - Whether or not we should stop/start the watcher.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the operation succeeded, otherwise <code>false</code> (which most likely means ownership of the pasteboard has changed).</li></ul> |

### Fields

#### [buffer](#buffer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.buffer <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains the Pasteboard Buffer. |

#### [watching](#watching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.pasteboard.manager.watching <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets whether or not we're watching the pasteboard as a boolean. |

