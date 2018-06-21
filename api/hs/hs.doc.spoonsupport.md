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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">two tables:</li><li markdown="1">  an array containing the paths from `package.path` which can contain Hammerspoon Spoon bundles.</li><li markdown="1">  a table with key-value pairs where the key matches an installed (but not necessarily loaded) spoon name and the value is a table containing the following keys:</li><li markdown="1">    path    - the path to the directory which contains the contents of the Spoon bundle</li><li markdown="1">    docPath - the expected path for documentation for this Spoon bundle</li><li markdown="1">    hasDocs - a boolean indicating whether or not the file referred to by `docPath` exists and is readable</li></ul>          |

#### [makeDocsFile](#makedocsfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.spoonsupport.makeDocsFile(spoonPath, [force]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Create the docs.json file for the Spoon bundle at the specified path.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">spoonPath - the path of the Spoon bundle to generate the documentation for</li><li markdown="1">force     - an optional boolean, default false, indicating whether or not an existing `docs.json` file within the Spoon bundle should be overwritten.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [updateDocFiles](#updatedocfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.spoonsupport.updateDocFiles() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates and updates the included documentation for the installed Spoon bundles if the documentation file is not present or the init.lua file for the Spoon has been modified more recently then the documentation file.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The Spoon documentation is expected to be in a file named `docs.json` at the root level of the Spoon bundle.</li></ul>                |

