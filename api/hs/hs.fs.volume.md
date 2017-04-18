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
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.fs.volume.didMount` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A volume was mounted                                                                                         |

#### [didRename](#didrename)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.fs.volume.didRename` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A volume changed either its name or mountpoint (or more likely, both)                                                                                         |

#### [didUnmount](#didunmount)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.fs.volume.didUnmount` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A volume was unmounted                                                                                         |

#### [willUnmount](#willunmount)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.fs.volume.willUnmount` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A volume is about to be unmounted                                                                                         |

### Functions

#### [allVolumes](#allvolumes)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.fs.volume.allVolumes([showHidden]) -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table of information about disk volumes attached to the system                                                                                         |
| **Parameters**                                       | <ul><li>showHidden - An optional boolean, true to show hidden volumes, false to not show hidden volumes. Defaults to false.</li></ul> |
| **Returns**                                          | <ul><li>A table of information, where the keys are the paths of disk volumes</li></ul>          |
| **Notes**                                            | <ul><li>This is an alias for `hs.host.volumeInformation()`</li><li>The possible keys in the table are:</li><li> NSURLVolumeTotalCapacityKey - Size of the volume in bytes</li><li> NSURLVolumeAvailableCapacityKey - Available space on the volume in bytes</li><li> NSURLVolumeIsAutomountedKey - Boolean indicating if the volume was automounted</li><li> NSURLVolumeIsBrowsableKey - Boolean indicating if the volume can be browsed</li><li> NSURLVolumeIsEjectableKey - Boolean indicating if the volume can be ejected</li><li> NSURLVolumeIsInternalKey - Boolean indicating if the volume is an internal drive or an external drive</li><li> NSURLVolumeIsLocalKey - Boolean indicating if the volume is a local or remote drive</li><li> NSURLVolumeIsReadOnlyKey - Boolean indicating if the volume is read only</li><li> NSURLVolumeIsRemovableKey - Boolean indicating if the volume is removable</li><li> NSURLVolumeMaximumFileSizeKey - Maximum file size the volume can support, in bytes</li><li> NSURLVolumeUUIDStringKey - The UUID of volume's filesystem</li><li> NSURLVolumeURLForRemountingKey - For remote volumes, the network URL of the volume</li><li> NSURLVolumeLocalizedNameKey - Localized version of the volume's name</li><li> NSURLVolumeNameKey - The volume's name</li><li> NSURLVolumeLocalizedFormatDescriptionKey - Localized description of the volume</li><li>* Not all keys will be present for all volumes</li></ul>                |

#### [eject](#eject)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.fs.volume.eject(path) -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unmounts and ejects a volume                                                                                         |
| **Parameters**                                       | <ul><li>path - An absolute path to the volume you wish to eject</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the volume was ejected, otherwise false</li></ul>          |

### Constructors

#### [new](#new)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.fs.volume.new(fn) -> watcher` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a watcher object for volume events                                                                                         |
| **Parameters**                                       | <ul><li>fn - A function that will be called when volume events happen. It should accept two parameters:</li><li> An event type (see the constants defined above)</li><li> A table that will contain relevant information</li></ul> |
| **Returns**                                          | <ul><li>An `hs.fs.volume` object</li></ul>          |

### Methods

#### [start](#start)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.fs.volume:start()` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the volume watcher                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `hs.fs.volume` object</li></ul>          |

#### [stop](#stop)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`hs.fs.volume:stop()` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the volume watcher                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `hs.fs.volume` object</li></ul>          |

