# [docs](index.md) » hs.pathwatcher
---

Watch paths recursively for changes

This simple example watches your Hammerspoon directory for changes, and when it sees a change, reloads your configs:

    local myWatcher = hs.pathwatcher.new(os.getenv("HOME") .. "/.hammerspoon/", hs.reload):start()

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pathwatcher.new(path, fn) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new path watcher object |
| **Parameters**                                       | <ul><li>path - A string containing the path to be watched</li><li>fn - A function to be called when changes are detected. It should accept two arguments:</li><li><code>paths</code>: a table containing a list of file paths that have changed</li><li><code>flagTables</code>: a table containing a list of tables denoting how each corresponding file in <code>paths</code> has changed, each containing boolean values indicating which types of events occurred; The possible keys are:<ul><li>mustScanSubDirs</li><li>userDropped</li><li>kernelDropped</li><li>eventIdsWrapped</li><li>historyDone</li><li>rootChanged</li><li>mount</li><li>unmount</li><li>itemCreated</li><li>itemRemoved</li><li>itemInodeMetaMod</li><li>itemRenamed</li><li>itemModified</li><li>itemFinderInfoMod</li><li>itemChangeOwner</li><li>itemXattrMod</li><li>itemIsFile</li><li>itemIsDir</li><li>itemIsSymlink</li><li>ownEvent (OS X 10.9+)</li><li>itemIsHardlink (OS X 10.10+)</li><li>itemIsLastHardlink (OS X 10.10+)</li></ul></li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.pathwatcher</code> object</li></ul> |
| **Notes**                                            | <ul><li>For more information about the event flags, see <a href="https://developer.apple.com/reference/coreservices/1455361-fseventstreameventflags/">the official documentation</a></li></ul> |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pathwatcher:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Starts a path watcher |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.pathwatcher</code> object</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pathwatcher:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops a path watcher |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

