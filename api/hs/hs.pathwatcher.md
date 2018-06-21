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
| **Parameters**                                       | <ul><li>path - A string containing the path to be watched</li></ul><ul><li>fn - A function to be called when changes are detected. It should accept two arguments:</li></ul><ul><li><code>paths</code>: a table containing a list of file paths that have changed</li></ul><ul><li><code>flagTables</code>: a table containing a list of tables denoting how each corresponding file in <code>paths</code> has changed, each containing boolean values indicating which types of events occurred; The possible keys are:</li></ul><pre><code> * mustScanSubDirs</code></pre><pre><code> * userDropped</code></pre><pre><code> * kernelDropped</code></pre><pre><code> * eventIdsWrapped</code></pre><pre><code> * historyDone</code></pre><pre><code> * rootChanged</code></pre><pre><code> * mount</code></pre><pre><code> * unmount</code></pre><pre><code> * itemCreated</code></pre><pre><code> * itemRemoved</code></pre><pre><code> * itemInodeMetaMod</code></pre><pre><code> * itemRenamed</code></pre><pre><code> * itemModified</code></pre><pre><code> * itemFinderInfoMod</code></pre><pre><code> * itemChangeOwner</code></pre><pre><code> * itemXattrMod</code></pre><pre><code> * itemIsFile</code></pre><pre><code> * itemIsDir</code></pre><pre><code> * itemIsSymlink</code></pre><pre><code> * ownEvent (OS X 10.9+)</code></pre><pre><code> * itemIsHardlink (OS X 10.10+)</code></pre><pre><code> * itemIsLastHardlink (OS X 10.10+)</code></pre>   |
| **Returns**                                          | <ul><li>An <code>hs.pathwatcher</code> object</li></ul>            |
| **Notes**                                            | <ul><li>For more information about the event flags, see <a href="https://developer.apple.com/reference/coreservices/1455361-fseventstreameventflags/">the official documentation</a></li></ul>                 |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pathwatcher:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts a path watcher                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.pathwatcher</code> object</li></ul>            |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pathwatcher:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops a path watcher                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

