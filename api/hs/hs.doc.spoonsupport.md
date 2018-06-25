# [docs](index.md) » hs.doc.spoonsupport
---

Provides run-time support for generating and including documentation for installed Hammerspoon Spoon bundles.

This module provides support for building (if necessary) and loading the documentation for installed Spoon bundles.  In general, it is not expected that most users will have a need to access these functions directly.

## API Overview
* Functions - API calls offered directly by the extension
 * [findSpoons](#findspoons)
 * [makeDocsFile](#makedocsfile)
 * [updateDocFiles](#updatedocfiles)

## API Documentation

### Functions

#### [findSpoons](#findspoons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.spoonsupport.findSpoons() -> pathTable, spoonsTable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns tables describing where spoons are installed and what spoons are currently available.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>two tables:   * an array containing the paths from <code>package.path</code> which can contain Hammerspoon Spoon bundles.   * a table with key-value pairs where the key matches an installed (but not necessarily loaded) spoon name and the value is a table containing the following keys:     * path    - the path to the directory which contains the contents of the Spoon bundle     * docPath - the expected path for documentation for this Spoon bundle     * hasDocs - a boolean indicating whether or not the file referred to by <code>docPath</code> exists and is readable</li><br /></ul>                                           |

#### [makeDocsFile](#makedocsfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.spoonsupport.makeDocsFile(spoonPath, [force]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Create the docs.json file for the Spoon bundle at the specified path.                                                                                         |
| **Parameters**                                       | <ul><br /><li>spoonPath - the path of the Spoon bundle to generate the documentation for * force     - an optional boolean, default false, indicating whether or not an existing <code>docs.json</code> file within the Spoon bundle should be overwritten.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [updateDocFiles](#updatedocfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.spoonsupport.updateDocFiles() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates and updates the included documentation for the installed Spoon bundles if the documentation file is not present or the init.lua file for the Spoon has been modified more recently then the documentation file.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The Spoon documentation is expected to be in a file named <code>docs.json</code> at the root level of the Spoon bundle.</li><br /></ul>                                             |

