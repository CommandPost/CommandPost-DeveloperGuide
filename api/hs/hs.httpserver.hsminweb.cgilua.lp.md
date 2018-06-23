# [docs](index.md) » hs.httpserver.hsminweb.cgilua.lp
---

Support functions for the CGILua compatibility module for including and translating Lua template pages into Lua code for execution within the Hammerspoon environment to provide dynamic content for http requests.

The most commonly used function is likely to be [cgilua.lp.include](#include), which allows including a template driven file during rendering so that common code can be reused more easily.  While passing in your own environment table for upvalues is possible, this is not recommended for general use because the default environment passed to each included file ensures that all server variables and the CGILua compatibility functions are available with the same names, and any new non-local (i.e. "global") variable defined are shared with the calling environment and not shared with the Hammerspoon global environment.

If your template file requires the ability to create variables in the Hammerspoon global environment, access the global environment directly through `_G`.

Note that the above considerations only apply to creating new "global" variables.  Any currently defined global variables (for example, the `hs` table where Hammerspoon module functions are stored) are available within the template file as long as no local or CGILua environment variable shares the same name (e.g. `_G["hs"]` and `hs` refer to the same table.

See the documentation for the [cgilua.lp.include](#include) for more information.

## API Overview
* Functions - API calls offered directly by the extension
 * [compile](#compile)
 * [include](#include)
 * [translate](#translate)

## API Documentation

### Functions

#### [compile](#compile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.cgilua.lp.compile(source, name, [env]) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts the specified Lua template source into a Lua function.                                                                                         |
| **Parameters**                                       | <ul><li>source - a string containing the contents of a Lua/HTML template to be converted into a function</li></ul><ul><li>name   - a label used in an error message if execution of the returned function results in a run-time error</li></ul><ul><li>env    - an optional table specifying the environment to be used by the lua builtin function <code>load</code> when converting the source into a function.  By default, the function will inherit its caller's environment.</li></ul>   |
| **Returns**                                          | <ul><li>A lua function which should take no arguments.</li></ul>            |
| **Notes**                                            | <ul><li>The source provided is first compared to a stored cache of previously translated templates and will re-use an existing translation if the template has been seen before.  If the source is unique, <a href="#translate">cgilua.lp.translate</a> is called on the template source.</li></ul><ul><li>This function is used internally by <a href="#include">cgilua.lp.include</a>, and probably won't be useful unless you want to translate a dynamically generated template -- which has security implications, depending upon what inputs you use to generate this template, because the resulting Lua code will execute within your Hammerspoon environment.  Be very careful about your inputs if you choose to ignore this warning.</li></ul>                 |

#### [include](#include)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.cgilua.lp.include(file, [env]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Includes the template specified by the `file` parameter.                                                                                         |
| **Parameters**                                       | <ul><li>file - a string containing the file system path to the template to include.</li></ul><ul><li>env  - an optional table specifying the environment to be used by the included template.  By default, the template will inherit its caller's environment.</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>This function is called by the web server to process the template specified by the requested URL.  Subsequent invocations of this function can be used to include common or re-used code from other template files and will be included in-line where the <code>cgilua.lp.include</code> function is invoked in the originating template.</li></ul><ul><li>During the processing of a web request, the local directory is temporarily changed to match the local directory of the path of the file being served, as determined by the URL of the request.  This is usually different than the Hammerspoon default directory which corresponds to the directory which contains the <code>init.lua</code> file for Hammerspoon.</li></ul>                 |

#### [translate](#translate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.httpserver.hsminweb.cgilua.lp.translate(source) -> luaCode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts the specified Lua template source into Lua code executable within the Hammerspoon environment.                                                                                         |
| **Parameters**                                       | <ul><li>source - a string containing the contents of a Lua/HTML template to be converted into true Lua code</li></ul>   |
| **Returns**                                          | <ul><li>The lua code corresponding to the provided source which can be fed into the <code>load</code> lua builtin to generate a Lua function.</li></ul>            |
| **Notes**                                            | <ul><li>This function is used internally by <a href="#include">cgilua.lp.include</a>, and probably won't be useful unless you want to translate a dynamically generated template -- which has security implications, depending upon what inputs you use to generate this template, because the resulting Lua code will execute within your Hammerspoon environment.  Be very careful about your inputs if you choose to ignore this warning.</li></ul><ul><li>To ensure that the translated code has access to the <code>cgilua</code> support functions, pass <code>_ENV</code> as the environment argument to the <code>load</code> lua builtin; otherwise any output generated by the resulting function will be sent to the Hammerspoon console and not included in the HTTP response sent back to the client.</li></ul>                 |

