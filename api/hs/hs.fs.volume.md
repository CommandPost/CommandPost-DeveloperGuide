# [docs](index.md) » hs.fs.volume
---

Interact with OS X filesystem volumes

This is distinct from hs.fs in that hs.fs deals with UNIX filesystem operations, while hs.fs.volume interacts with the higher level OS X concept of volumes

## API Overview
* Constants - Useful values which cannot be changed
 * [didMount](#didmount)
 * [didRename](#didrename)
 * [didUnmount](#didunmount)
 * [willUnmount](#willunmount)
* Functions - API calls offered directly by the extension
 * [allVolumes](#allvolumes)
 * [eject](#eject)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constants

#### [didMount](#didmount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume.didMount` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A volume was mounted                                                                                         |

#### [didRename](#didrename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume.didRename` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A volume changed either its name or mountpoint (or more likely, both)                                                                                         |

#### [didUnmount](#didunmount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume.didUnmount` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A volume was unmounted                                                                                         |

#### [willUnmount](#willunmount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume.willUnmount` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A volume is about to be unmounted                                                                                         |

### Functions

#### [allVolumes](#allvolumes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume.allVolumes([showHidden]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table of information about disk volumes attached to the system                                                                                         |
| **Parameters**                                       |  * showHidden - An optional boolean, true to show hidden volumes, false to not show hidden volumes. Defaults to false.                                       |
| **Returns**                                          |  * A table of information, where the keys are the paths of disk volumes                                                |
| **Notes**                                            |  * This is an alias for `hs.host.volumeInformation()` * The possible keys in the table are:  * NSURLVolumeTotalCapacityKey - Size of the volume in bytes  * NSURLVolumeAvailableCapacityKey - Available space on the volume in bytes  * NSURLVolumeIsAutomountedKey - Boolean indicating if the volume was automounted  * NSURLVolumeIsBrowsableKey - Boolean indicating if the volume can be browsed  * NSURLVolumeIsEjectableKey - Boolean indicating if the volume should be ejected before its media is removed  * NSURLVolumeIsInternalKey - Boolean indicating if the volume is an internal drive or an external drive  * NSURLVolumeIsLocalKey - Boolean indicating if the volume is a local or remote drive  * NSURLVolumeIsReadOnlyKey - Boolean indicating if the volume is read only  * NSURLVolumeIsRemovableKey - Boolean indicating if the volume's media can be physically ejected from the drive (e.g. a DVD)  * NSURLVolumeMaximumFileSizeKey - Maximum file size the volume can support, in bytes  * NSURLVolumeUUIDStringKey - The UUID of volume's filesystem  * NSURLVolumeURLForRemountingKey - For remote volumes, the network URL of the volume  * NSURLVolumeLocalizedNameKey - Localized version of the volume's name  * NSURLVolumeNameKey - The volume's name  * NSURLVolumeLocalizedFormatDescriptionKey - Localized description of the volume* Not all keys will be present for all volumes* The meanings of NSURLVolumeIsEjectableKey and NSURLVolumeIsRemovableKey are not generally what they sound like. If you want a simple test as to whether or not a volume is a removable drive (e.g. a USB hard disk), check for NSURLVolumeIsInternalKey being false (this is what Finder does)                                                      |

#### [eject](#eject)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume.eject(path) -> boolean,string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unmounts and ejects a volume                                                                                         |
| **Parameters**                                       |  * path - An absolute path to the volume you wish to eject                                       |
| **Returns**                                          |  * A boolean, true if the volume was ejected, otherwise false * A string, empty if the volume was ejected, otherwise it will contain the error message                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume.new(fn) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a watcher object for volume events                                                                                         |
| **Parameters**                                       |  * fn - A function that will be called when volume events happen. It should accept two parameters:  * An event type (see the constants defined above)  * A table that will contain relevant information                                       |
| **Returns**                                          |  * An `hs.fs.volume` object                                                |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the volume watcher                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An `hs.fs.volume` object                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the volume watcher                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An `hs.fs.volume` object                                                |

