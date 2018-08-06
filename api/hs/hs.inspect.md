# [docs](index.md) » hs.inspect
---

Produce human-readable representations of Lua variables (particularly tables)

This extension is based on inspect.lua by Enrique García Cota
https://github.com/kikito/inspect.lua

## API Overview
* Functions - API calls offered directly by the extension
 * [inspect](#inspect)

## API Documentation

### Functions

#### [inspect](#inspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.inspect.inspect(variable[, options]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets a human readable version of the supplied Lua variable |
| **Parameters**                                       | <ul><li>variable - A lua variable of some kind</li><li>options - An optional table which can be used to influence the inspector. Valid keys are as follows:</li><li>depth - A number representing the maximum depth to recurse into <code>variable</code>. Below that depth, data will be displayed as <code>{...}</code></li><li>newline - A string to use for line breaks. Defaults to <code>\n</code></li><li>indent - A string to use for indentation. Defaults to <code></code> (two spaces)</li><li>process - A function that will be called for each item. It should accept two arguments, <code>item</code> (the current item being processed) and <code>path</code> (the item's position in the variable being inspected. The function should either return a processed form of the variable, the original variable itself if it requires no processing, or <code>nil</code> to remove the item from the inspected output.</li><li>metatables - If <code>true</code>, include (and traverse) metatables</li></ul> |
| **Returns**                                          | <ul><li>A string containing the human readable version of <code>variable</code></li></ul> |
| **Notes**                                            | <ul><li>For convenience, you can call this function as <code>hs.inspect(variable)</code></li><li>For more information on the options, and some examples, see <a href="https://github.com/kikito/inspect.lua">the upstream docs</a></li></ul> |

