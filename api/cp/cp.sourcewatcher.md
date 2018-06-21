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
| **Parameters**                                       |  * `files`      - Table of files to check as strings * `flagTables` - Table of flagTables (see: `hs.pathwatcher.new`)                                       |
| **Returns**                                          |  * None                                                |

#### [matchesExtensions](#matchesextensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:matchesExtensions(file) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks that the file that triggered the Path Watcher matches the extension given.                                                                                         |
| **Parameters**                                       |  * `file`       - The file as string                                       |
| **Returns**                                          |  * A boolean value                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher.new(extensions) -> sourcewatcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new `sourcewatcher` instance.                                                                                         |
| **Parameters**                                       |  * `extensions`     - Extensions                                       |
| **Returns**                                          |  * A sourcewatcher instance                                                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:start() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts a Source Watcher.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops a Source Watcher.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [watchPath](#watchpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:watchPath(path) -> sourcewatcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Watches a path.                                                                                         |
| **Parameters**                                       |  * `path`       - The path you want to watch as a string.                                       |
| **Returns**                                          |  * sourcewatcher                                                |

