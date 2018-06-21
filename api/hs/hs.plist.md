# [docs](index.md) » hs.plist
---

Read and write Property List files

## API Overview
* Functions - API calls offered directly by the extension
 * [read](#read)
 * [write](#write)

## API Documentation

### Functions

#### [read](#read)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.plist.read(filepath) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Loads a Property List file                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">filepath - The path and filename of a plist file to read</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The contents of the plist as a Lua table</li></ul>          |

#### [write](#write)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.plist.write(filepath, data[, binary]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Writes a Property List file                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">filepath - The path and filename of the plist file to write</li><li markdown="1">data - A Lua table containing the data to write into the plist</li><li markdown="1">binary - An optional boolean, if true, the plist will be written as a binary file. Defaults to false</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean, true if the plist was written successfully, otherwise false</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Only simple types can be converted to plist items:</li><li markdown="1"> Strings</li><li markdown="1"> Numbers</li><li markdown="1"> Booleans</li><li markdown="1"> Tables</li><li markdown="1">You should be careful when reading a plist, modifying and writing it - Hammerspoon may not be able to preserve all of the datatypes via Lua</li></ul>                |

