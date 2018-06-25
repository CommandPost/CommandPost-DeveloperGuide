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
| **Parameters**                                       | <ul><br /><li><code>files</code>      - Table of files to check as strings * <code>flagTables</code> - Table of flagTables (see: <code>hs.pathwatcher.new</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [matchesExtensions](#matchesextensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:matchesExtensions(file) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks that the file that triggered the Path Watcher matches the extension given.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>file</code>       - The file as string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A boolean value</li><br /></ul>                                           |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher.new(extensions) -> sourcewatcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new `sourcewatcher` instance.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>extensions</code>     - Extensions</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A sourcewatcher instance</li><br /></ul>                                           |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:start() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts a Source Watcher.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:stop() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops a Source Watcher.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [watchPath](#watchpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.sourcewatcher:watchPath(path) -> sourcewatcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Watches a path.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>path</code>       - The path you want to watch as a string.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>sourcewatcher</li><br /></ul>                                           |

