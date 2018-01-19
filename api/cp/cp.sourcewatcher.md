# [docs](index.md) » cp.sourcewatcher
---

Watches folders for specific file extensions and reloads the app if they change.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [filesChanged](#fileschanged)
 * [matchesExtensions](#matchesextensions)
 * [new](#new)
 * [start](#start)
 * [stop](#stop)
 * [watchPath](#watchpath)

## API Documentation

### Methods

#### [filesChanged](#fileschanged)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:filesChanged(files, flagTables) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks that the file that triggered the Path Watcher matches the extension given.                                                                                         |
| **Parameters**                                       | <ul><li>`files`      - Table of files to check as strings</li><li>`flagTables` - Table of flagTables (see: `hs.pathwatcher.new`)</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [matchesExtensions](#matchesextensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:matchesExtensions(file) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks that the file that triggered the Path Watcher matches the extension given.                                                                                         |
| **Parameters**                                       | <ul><li>`file`       - The file as string</li></ul> |
| **Returns**                                          | <ul><li>A boolean value</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher.new(extensions) -> sourcewatcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new `sourcewatcher` instance.                                                                                         |
| **Parameters**                                       | <ul><li>`extensions`     - Extensions</li></ul> |
| **Returns**                                          | <ul><li>A sourcewatcher instance</li></ul>          |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:start() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts a Source Watcher.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops a Source Watcher.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [watchPath](#watchpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:watchPath(path) -> sourcewatcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Watches a path.                                                                                         |
| **Parameters**                                       | <ul><li>`path`       - The path you want to watch as a string.</li></ul> |
| **Returns**                                          | <ul><li>sourcewatcher</li></ul>          |

