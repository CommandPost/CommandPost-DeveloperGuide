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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">showHidden - An optional boolean, true to show hidden volumes, false to not show hidden volumes. Defaults to false.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table of information, where the keys are the paths of disk volumes</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This is an alias for `hs.host.volumeInformation()`</li><li markdown="1">The possible keys in the table are:</li><li markdown="1"> NSURLVolumeTotalCapacityKey - Size of the volume in bytes</li><li markdown="1"> NSURLVolumeAvailableCapacityKey - Available space on the volume in bytes</li><li markdown="1"> NSURLVolumeIsAutomountedKey - Boolean indicating if the volume was automounted</li><li markdown="1"> NSURLVolumeIsBrowsableKey - Boolean indicating if the volume can be browsed</li><li markdown="1"> NSURLVolumeIsEjectableKey - Boolean indicating if the volume should be ejected before its media is removed</li><li markdown="1"> NSURLVolumeIsInternalKey - Boolean indicating if the volume is an internal drive or an external drive</li><li markdown="1"> NSURLVolumeIsLocalKey - Boolean indicating if the volume is a local or remote drive</li><li markdown="1"> NSURLVolumeIsReadOnlyKey - Boolean indicating if the volume is read only</li><li markdown="1"> NSURLVolumeIsRemovableKey - Boolean indicating if the volume's media can be physically ejected from the drive (e.g. a DVD)</li><li markdown="1"> NSURLVolumeMaximumFileSizeKey - Maximum file size the volume can support, in bytes</li><li markdown="1"> NSURLVolumeUUIDStringKey - The UUID of volume's filesystem</li><li markdown="1"> NSURLVolumeURLForRemountingKey - For remote volumes, the network URL of the volume</li><li markdown="1"> NSURLVolumeLocalizedNameKey - Localized version of the volume's name</li><li markdown="1"> NSURLVolumeNameKey - The volume's name</li><li markdown="1"> NSURLVolumeLocalizedFormatDescriptionKey - Localized description of the volume</li><li markdown="1">* Not all keys will be present for all volumes</li><li markdown="1">* The meanings of NSURLVolumeIsEjectableKey and NSURLVolumeIsRemovableKey are not generally what they sound like. If you want a simple test as to whether or not a volume is a removable drive (e.g. a USB hard disk), check for NSURLVolumeIsInternalKey being false (this is what Finder does)</li></ul>                |

#### [eject](#eject)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume.eject(path) -> boolean,string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unmounts and ejects a volume                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - An absolute path to the volume you wish to eject</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean, true if the volume was ejected, otherwise false</li><li markdown="1">A string, empty if the volume was ejected, otherwise it will contain the error message</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume.new(fn) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a watcher object for volume events                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">fn - A function that will be called when volume events happen. It should accept two parameters:</li><li markdown="1"> An event type (see the constants defined above)</li><li markdown="1"> A table that will contain relevant information</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `hs.fs.volume` object</li></ul>          |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the volume watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `hs.fs.volume` object</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.volume:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the volume watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `hs.fs.volume` object</li></ul>          |

