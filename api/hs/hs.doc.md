# [docs](index.md) » hs.doc
---

Create documentation objects for interactive help within Hammerspoon

The documentation object created is a table with tostring metamethods allowing access to a specific functions documentation by appending the path to the method or function to the object created.

From the Hammerspoon console:

      doc = require("hs.doc").fromRegisteredFiles()
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

By default, the internal core documentation and portions of the Lua 5.3 manual, located at http://www.lua.org/manual/5.3/manual.html, are already registered for inclusion within this documentation object, but you can register additional documentation from 3rd party modules with `hs.registerJSONFile(...)` or limit the documentation to a single specific file with `hs.fromJSONFile(...)`.

## Submodules
 * [hs.doc.hsdocs](hs.doc.hsdocs.md)
 * [hs.doc.markdown](hs.doc.markdown.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [fromJSONFile](#fromJSONFile)
 * [fromRegisteredFiles](#fromRegisteredFiles)
 * [help](#help)
 * [locateJSONFile](#locateJSONFile)
 * [registerJSONFile](#registerJSONFile)
 * [registeredFiles](#registeredFiles)
 * [unregisterJSONFile](#unregisterJSONFile)
 * [validateJSONFile](#validateJSONFile)

## API Documentation

### Functions

#### [fromJSONFile](#fromJSONFile)
| **Signature**                               | `hs.doc.fromJSONFile(jsonfile) -> doc-array`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Builds a doc array construct from the JSON file provided.                                                                     |
| **Parameters**                              | <ul><li>jsonfile - A string containing the location of a JSON file</li></ul> |
| **Returns**                                 | <ul><li>A table containing the documentation data loaded from the JSON file</li></ul>          |

#### [fromRegisteredFiles](#fromRegisteredFiles)
| **Signature**                               | `hs.doc.fromRegisteredFiles() -> doc-array`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Builds a doc array construct from the registered JSON files.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing the documentation data loaded from the registered JSON files</li></ul>          |
| **Notes**                                   | <ul><li>By default, the internal core documentation is already registered.  If you wish to remove it from the list of registered sources, issue the command `hs.doc.unregisterJSONFile(hs.docstrings_json_file)`.</li><li>The documentation object is created from the sources that are registered at the time of its invocation. If you register additional files later, you will need to reissue this command to build the updated documentation object.</li></ul>                |

#### [help](#help)
| **Signature**                               | `hs.doc.help(identifier)`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Prints the documentation for some part of Hammerspoon's API and Lua 5.3.  This function has also been aliased as `hs.help` and `help` as a shorthand for use within the Hammerspoon console.                                                                     |
| **Parameters**                              | <ul><li>identifier - A string containing the signature of some part of Hammerspoon's API (e.g. `"hs.reload"`)</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>This function is mainly for runtime API help while using Hammerspoon's Console</li><li>This function only returns information about the core Hammerspoon API and Lua 5.3.  If you register additional files from 3rd party modules, or deregister the initial files for creating your own `hs.doc` objects, it will not affect the results used by this function.</li></ul>                |

#### [locateJSONFile](#locateJSONFile)
| **Signature**                               | `hs.doc.locateJSONFile(module) -> path | false, message`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Locates the JSON file corresponding to the specified module by searching package.path and package.cpath.                                                                     |
| **Parameters**                              | <ul><li>module - the name of the module to locate a JSON file for</li></ul> |
| **Returns**                                 | <ul><li>the path to the JSON file, or `false, error` if unable to locate a corresponding JSON file.</li></ul>          |
| **Notes**                                   | <ul><li>The JSON should be named 'full.module.name.json' and located in the same directory as the `lua` or `so` file which is used when the module is loaded via `require`.</li></ul>                |

#### [registerJSONFile](#registerJSONFile)
| **Signature**                               | `hs.doc.registerJSONFile(jsonfile) -> status[, message]`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Register a JSON file for inclusion when Hammerspoon generates internal documentation.                                                                     |
| **Parameters**                              | <ul><li>jsonfile - A string containing the location of a JSON file</li></ul> |
| **Returns**                                 | <ul><li>status - Boolean flag indicating if the file was registered or not.  If the file was not registered, then a message indicating the error is also returned.</li></ul>          |

#### [registeredFiles](#registeredFiles)
| **Signature**                               | `hs.doc.registeredFiles() -> table`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the list of registered JSON files.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a table containing the list of registered JSON files</li></ul>          |
| **Notes**                                   | <ul><li>The table returned by this function has a metatable including a __tostring method which allows you to see the list of registered files by simply typing `hs.doc.registeredFiles()` in the Hammerspoon Console.</li></ul>                |

#### [unregisterJSONFile](#unregisterJSONFile)
| **Signature**                               | `hs.doc.unregisterJSONFile(jsonfile) -> status[, message]`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Remove a JSON file from the list of registered files.                                                                     |
| **Parameters**                              | <ul><li>jsonfile - A string containing the location of a JSON file</li></ul> |
| **Returns**                                 | <ul><li>status - Boolean flag indicating if the file was unregistered or not.  If the file was not unregistered, then a message indicating the error is also returned.</li></ul>          |

#### [validateJSONFile](#validateJSONFile)
| **Signature**                               | `hs.doc.validateJSONFile(jsonfile) -> status, message|table`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Validate a JSON file potential inclusion in the Hammerspoon internal documentation.                                                                     |
| **Parameters**                              | <ul><li>jsonfile - A string containing the location of a JSON file</li></ul> |
| **Returns**                                 | <ul><li>status - Boolean flag indicating if the file was validated or not.</li><li>message|table - If the file did not contain valid JSON data, then a message indicating the error is returned; otherwise the parsed JSON data is returned as a table.</li></ul>          |

