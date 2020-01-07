# [docs](index.md) » hs.plist
---

Read and write Property List files

## API Overview
* Functions - API calls offered directly by the extension
 * [read](#read)
 * [readString](#readstring)
 * [write](#write)

## API Documentation

### Functions

#### [read](#read)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.plist.read(filepath) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Loads a Property List file |
| **Parameters**                                       | <ul><li>filepath - The path and filename of a plist file to read</li></ul> |
| **Returns**                                          | <ul><li>The contents of the plist as a Lua table</li></ul> |

#### [readString](#readstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.plist.readString(value) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Interpretes a property list file within a string into a table. |
| **Parameters**                                       | <ul><li>value - The contents of the property list as a string</li></ul> |
| **Returns**                                          | <ul><li>The contents of the property list as a Lua table or <code>nil</code> if an error occurs</li></ul> |

#### [write](#write)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.plist.write(filepath, data[, binary]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Writes a Property List file |
| **Parameters**                                       | <ul><li>filepath - The path and filename of the plist file to write</li><li>data - A Lua table containing the data to write into the plist</li><li>binary - An optional boolean, if true, the plist will be written as a binary file. Defaults to false</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the plist was written successfully, otherwise false</li></ul> |
| **Notes**                                            | <ul><li>Only simple types can be converted to plist items:</li><li>Strings</li><li>Numbers</li><li>Booleans</li><li>Tables</li><li>You should be careful when reading a plist, modifying and writing it - Hammerspoon may not be able to preserve all of the datatypes via Lua</li></ul> |

