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

## API Overview
* Functions - API calls offered directly by the extension
 * [help](#help)
 * [locateJSONFile](#locatejsonfile)
 * [preloadSpoonDocs](#preloadspoondocs)
 * [registeredFiles](#registeredfiles)
 * [registerJSONFile](#registerjsonfile)
 * [unregisterJSONFile](#unregisterjsonfile)

## API Documentation

### Functions

#### [help](#help)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.help(identifier)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Prints the documentation for some part of Hammerspoon's API and Lua 5.3.  This function has also been aliased as `hs.help` and `help` as a shorthand for use within the Hammerspoon console. |
| **Parameters**                                       | <ul><li>identifier - A string containing the signature of some part of Hammerspoon's API (e.g. <code>"hs.reload"</code>)</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This function is mainly for runtime API help while using Hammerspoon's Console</li></ul> |

#### [locateJSONFile](#locatejsonfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.locateJSONFile(module) -> path | false, message` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Locates the JSON file corresponding to the specified third-party module or Spoon by searching package.path and package.cpath. |
| **Parameters**                                       | <ul><li>module - the name of the module to locate a JSON file for</li></ul> |
| **Returns**                                          | <ul><li>the path to the JSON file, or <code>false, error</code> if unable to locate a corresponding JSON file.</li></ul> |
| **Notes**                                            | <ul><li>The JSON should be named 'docs.json' and located in the same directory as the <code>lua</code> or <code>so</code> file which is used when the module is loaded via <code>require</code>.</li></ul> |

#### [preloadSpoonDocs](#preloadspoondocs)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.preloadSpoonDocs()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Locates all installed Spoon documentation files and and marks them for loading the next time the [hs.doc.help](#help) function is invoked. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [registeredFiles](#registeredfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.registeredFiles() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the list of registered JSON files. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table containing the list of registered JSON files</li></ul> |
| **Notes**                                            | <ul><li>The table returned by this function has a metatable including a __tostring method which allows you to see the list of registered files by simply typing <code>hs.doc.registeredFiles()</code> in the Hammerspoon Console.</li></ul> |

#### [registerJSONFile](#registerjsonfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.registerJSONFile(jsonfile, [isSpoon]) -> status[, message]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Register a JSON file for inclusion when Hammerspoon generates internal documentation. |
| **Parameters**                                       | <ul><li>jsonfile - A string containing the location of a JSON file</li><li>isSpoon  - an optional boolean, default false, specifying that the documentation should be added to the <code>spoons</code> sub heading in the documentation hierarchy.</li></ul> |
| **Returns**                                          | <ul><li>status - Boolean flag indicating if the file was registered or not.  If the file was not registered, then a message indicating the error is also returned.</li></ul> |
| **Notes**                                            | <ul><li>this function just registers the documentation file; it won't actually be loaded and parsed until <a href="#help">hs.doc.help</a> is invoked.</li></ul> |

#### [unregisterJSONFile](#unregisterjsonfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.unregisterJSONFile(jsonfile) -> status[, message]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Remove a JSON file from the list of registered files. |
| **Parameters**                                       | <ul><li>jsonfile - A string containing the location of a JSON file</li></ul> |
| **Returns**                                          | <ul><li>status - Boolean flag indicating if the file was unregistered or not.  If the file was not unregistered, then a message indicating the error is also returned.</li></ul> |
| **Notes**                                            | <ul><li>This function requires the rebuilding of the entire documentation tree for all remaining registered files, so the next time help is queried with <a href="#help">hs.doc.help</a>, there may be a slight one-time delay.</li></ul> |

