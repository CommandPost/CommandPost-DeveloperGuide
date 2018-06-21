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
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new path watcher object                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - A string containing the path to be watched</li><li markdown="1">fn - A function to be called when changes are detected. It should accept two arguments:</li><li markdown="1">  `paths`: a table containing a list of file paths that have changed</li><li markdown="1">  `flagTables`: a table containing a list of tables denoting how each corresponding file in `paths` has changed, each containing boolean values indicating which types of events occurred; The possible keys are:</li><li markdown="1">    mustScanSubDirs</li><li markdown="1">    userDropped</li><li markdown="1">    kernelDropped</li><li markdown="1">    eventIdsWrapped</li><li markdown="1">    historyDone</li><li markdown="1">    rootChanged</li><li markdown="1">    mount</li><li markdown="1">    unmount</li><li markdown="1">    itemCreated</li><li markdown="1">    itemRemoved</li><li markdown="1">    itemInodeMetaMod</li><li markdown="1">    itemRenamed</li><li markdown="1">    itemModified</li><li markdown="1">    itemFinderInfoMod</li><li markdown="1">    itemChangeOwner</li><li markdown="1">    itemXattrMod</li><li markdown="1">    itemIsFile</li><li markdown="1">    itemIsDir</li><li markdown="1">    itemIsSymlink</li><li markdown="1">    ownEvent (OS X 10.9+)</li><li markdown="1">    itemIsHardlink (OS X 10.10+)</li><li markdown="1">    itemIsLastHardlink (OS X 10.10+)</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `hs.pathwatcher` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">For more information about the event flags, see [the official documentation](https://developer.apple.com/reference/coreservices/1455361-fseventstreameventflags/)</li></ul>                |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pathwatcher:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts a path watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `hs.pathwatcher` object</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pathwatcher:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops a path watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

