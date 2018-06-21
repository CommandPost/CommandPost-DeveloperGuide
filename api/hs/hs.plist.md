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
| **Parameters**                                       |  * filepath - The path and filename of a plist file to read                                       |
| **Returns**                                          |  * The contents of the plist as a Lua table                                                |

#### [write](#write)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.plist.write(filepath, data[, binary]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Writes a Property List file                                                                                         |
| **Parameters**                                       |  * filepath - The path and filename of the plist file to write * data - A Lua table containing the data to write into the plist * binary - An optional boolean, if true, the plist will be written as a binary file. Defaults to false                                       |
| **Returns**                                          |  * A boolean, true if the plist was written successfully, otherwise false                                                |
| **Notes**                                            |  * Only simple types can be converted to plist items:  * Strings  * Numbers  * Booleans  * Tables * You should be careful when reading a plist, modifying and writing it - Hammerspoon may not be able to preserve all of the datatypes via Lua                                                      |

