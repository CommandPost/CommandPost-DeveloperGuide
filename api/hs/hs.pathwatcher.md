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
| **Parameters**                                       | <ul><br /><li>path - A string containing the path to be watched * fn - A function to be called when changes are detected. It should accept two arguments:   * <code>paths</code>: a table containing a list of file paths that have changed   * <code>flagTables</code>: a table containing a list of tables denoting how each corresponding file in <code>paths</code> has changed, each containing boolean values indicating which types of events occurred; The possible keys are:     * mustScanSubDirs     * userDropped     * kernelDropped     * eventIdsWrapped     * historyDone     * rootChanged     * mount     * unmount     * itemCreated     * itemRemoved     * itemInodeMetaMod     * itemRenamed     * itemModified     * itemFinderInfoMod     * itemChangeOwner     * itemXattrMod     * itemIsFile     * itemIsDir     * itemIsSymlink     * ownEvent (OS X 10.9+)     * itemIsHardlink (OS X 10.10+)     * itemIsLastHardlink (OS X 10.10+)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An <code>hs.pathwatcher</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>For more information about the event flags, see <a href="https://developer.apple.com/reference/coreservices/1455361-fseventstreameventflags/">the official documentation</a></li><br /></ul>                                             |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pathwatcher:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts a path watcher                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>hs.pathwatcher</code> object</li><br /></ul>                                           |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pathwatcher:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops a path watcher                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

