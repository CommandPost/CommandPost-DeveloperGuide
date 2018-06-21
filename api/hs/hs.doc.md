# [docs](index.md) » hs.doc
---

Create documentation objects for interactive help within Hammerspoon

The documentation object created is a table with tostring metamethods allowing access to a specific functions documentation by appending the path to the method or function to the object created.

From the Hammerspoon console:

      doc = require("hs.doc")
      doc.hs.application

Results in:
      Manipulate running applications

      [submodules]
      hs.application.watcher

      [subitems]
      hs.application:activate([allWindows]) -> bool
      hs.application:allWindows() -> window[]
          ...
      hs.application:visibleWindows() -> win[]

By default, the internal core documentation and portions of the Lua 5.3 manual, located at http://www.lua.org/manual/5.3/manual.html, are already registered for inclusion within this documentation object, but you can register additional documentation from 3rd party modules with `hs.registerJSONFile(...)`.

## Submodules
 * [hs.doc.builder](hs.doc.builder.md)
 * [hs.doc.hsdocs](hs.doc.hsdocs.md)
 * [hs.doc.markdown](hs.doc.markdown.md)
 * [hs.doc.spoonsupport](hs.doc.spoonsupport.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [help](#help)
 * [locateJSONFile](#locatejsonfile)
 * [registeredFiles](#registeredfiles)
 * [registerJSONFile](#registerjsonfile)
 * [unregisterJSONFile](#unregisterjsonfile)
 * [validateJSONFile](#validatejsonfile)

## API Documentation

### Functions

#### [help](#help)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.help(identifier)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Prints the documentation for some part of Hammerspoon's API and Lua 5.3.  This function has also been aliased as `hs.help` and `help` as a shorthand for use within the Hammerspoon console.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">identifier - A string containing the signature of some part of Hammerspoon's API (e.g. `"hs.reload"`)</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This function is mainly for runtime API help while using Hammerspoon's Console</li><li markdown="1">This function only returns information about the core Hammerspoon API and Lua 5.3.  If you register additional files from 3rd party modules, or deregister the initial files for creating your own `hs.doc` objects, it will not affect the results used by this function.</li></ul>                |

#### [locateJSONFile](#locatejsonfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.locateJSONFile(module) -> path | false, message` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Locates the JSON file corresponding to the specified module by searching package.path and package.cpath.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">module - the name of the module to locate a JSON file for</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the path to the JSON file, or `false, error` if unable to locate a corresponding JSON file.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The JSON should be named 'docs.json' and located in the same directory as the `lua` or `so` file which is used when the module is loaded via `require`.</li></ul>                |

#### [registeredFiles](#registeredfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.registeredFiles() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the list of registered JSON files.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a table containing the list of registered JSON files</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The table returned by this function has a metatable including a __tostring method which allows you to see the list of registered files by simply typing `hs.doc.registeredFiles()` in the Hammerspoon Console.</li></ul>                |

#### [registerJSONFile](#registerjsonfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.registerJSONFile(jsonfile) -> status[, message]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Register a JSON file for inclusion when Hammerspoon generates internal documentation.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">jsonfile - A string containing the location of a JSON file</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">status - Boolean flag indicating if the file was registered or not.  If the file was not registered, then a message indicating the error is also returned.</li></ul>          |

#### [unregisterJSONFile](#unregisterjsonfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.unregisterJSONFile(jsonfile, [isSpoon]) -> status[, message]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Remove a JSON file from the list of registered files.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">jsonfile - A string containing the location of a JSON file</li><li markdown="1">isSpoon  - an optional boolean, default false, specifying that the documentation should be added to the `spoons` sub heading in the documentation hierarchy.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">status - Boolean flag indicating if the file was unregistered or not.  If the file was not unregistered, then a message indicating the error is also returned.</li></ul>          |

#### [validateJSONFile](#validatejsonfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.validateJSONFile(jsonfile) -> status, message|table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Validate a JSON file potential inclusion in the Hammerspoon internal documentation.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">jsonfile - A string containing the location of a JSON file</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">status - Boolean flag indicating if the file was validated or not.</li><li markdown="1">message|table - If the file did not contain valid JSON data, then a message indicating the error is returned; otherwise the parsed JSON data is returned as a table.</li></ul>          |

