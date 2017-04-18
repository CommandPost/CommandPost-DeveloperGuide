# [docs](index.md) » cp.plist
---

Reads & Writes plist data.

## Submodules
 * [cp.plist.archiver](cp.plist.archiver.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [base64ToTable](#base64totable)
 * [binaryFileToTable](#binaryfiletotable)
 * [binaryFileToXML](#binaryfiletoxml)
 * [binaryToTable](#binarytotable)
 * [fileToTable](#filetotable)
 * [xmlFileToTable](#xmlfiletotable)

## API Documentation

### Functions

#### [base64ToTable](#base64totable)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.plist.base64ToTable(base64Data) -> table or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts base64 Data into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>base64Data - Binary data encoded in base64</li></ul> |
| **Returns**                                          | <ul><li>A table of the plist data</li></ul>          |
| **Notes**                                            | <ul><li>None</li></ul>                |

#### [binaryFileToTable](#binaryfiletotable)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.plist.binaryFileToTable(plistFileName) -> table or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts the data from a Binary File into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>plistFileName - Path & Filename of the Binary File</li></ul> |
| **Returns**                                          | <ul><li>A table of the plist data</li></ul>          |
| **Notes**                                            | <ul><li>None</li></ul>                |

#### [binaryFileToXML](#binaryfiletoxml)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.plist.binaryFileToXML(plistFileName) -> string | nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts the data from a Binary plist File into XML as a string.                                                                                         |
| **Parameters**                                       | <ul><li>plistFileName - Path & Filename of the Binary File</li></ul> |
| **Returns**                                          | <ul><li>A string of XML data</li></ul>          |
| **Notes**                                            | <ul><li>None</li></ul>                |

#### [binaryToTable](#binarytotable)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.plist.binaryToTable(binaryData) -> table or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts Binary Data into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>binaryData - Binary data</li></ul> |
| **Returns**                                          | <ul><li>A table of the plist data</li></ul>          |
| **Notes**                                            | <ul><li>None</li></ul>                |

#### [fileToTable](#filetotable)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.plist.fileToTable(plistFileName) -> table or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts plist data from a binary or XML file into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>plistFileName - Path & Filename of the XML File</li></ul> |
| **Returns**                                          | <ul><li>A table of plist data</li></ul>          |
| **Notes**                                            | <ul><li>None</li></ul>                |

#### [xmlFileToTable](#xmlfiletotable)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`cp.plist.xmlFileToTable(plistFileName) -> table or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts XML data from a file into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>plistFileName - Path & Filename of the XML File</li></ul> |
| **Returns**                                          | <ul><li>A table of plist data</li></ul>          |
| **Notes**                                            | <ul><li>None</li></ul>                |

