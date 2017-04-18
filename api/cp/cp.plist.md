# [docs](index.md) » cp.plist
---

Reads & Writes plist data.

## Submodules
 * [cp.plist.archiver](cp.plist.archiver.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [base64ToTable](#base64ToTable)
 * [binaryFileToTable](#binaryFileToTable)
 * [binaryFileToXML](#binaryFileToXML)
 * [binaryToTable](#binaryToTable)
 * [fileToTable](#fileToTable)
 * [xmlFileToTable](#xmlFileToTable)

## API Documentation

### Functions

#### [base64ToTable](#base64ToTable)
| **Signature**                               | `cp.plist.base64ToTable(base64Data) -> table or nil`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Converts base64 Data into a LUA Table.                                                                     |
| **Parameters**                              | <ul><li>base64Data - Binary data encoded in base64</li></ul> |
| **Returns**                                 | <ul><li>A table of the plist data</li></ul>          |
| **Notes**                                   | <ul><li>None</li></ul>                |

#### [binaryFileToTable](#binaryFileToTable)
| **Signature**                               | `cp.plist.binaryFileToTable(plistFileName) -> table or nil`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Converts the data from a Binary File into a LUA Table.                                                                     |
| **Parameters**                              | <ul><li>plistFileName - Path & Filename of the Binary File</li></ul> |
| **Returns**                                 | <ul><li>A table of the plist data</li></ul>          |
| **Notes**                                   | <ul><li>None</li></ul>                |

#### [binaryFileToXML](#binaryFileToXML)
| **Signature**                               | `cp.plist.binaryFileToXML(plistFileName) -> string | nil`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Converts the data from a Binary plist File into XML as a string.                                                                     |
| **Parameters**                              | <ul><li>plistFileName - Path & Filename of the Binary File</li></ul> |
| **Returns**                                 | <ul><li>A string of XML data</li></ul>          |
| **Notes**                                   | <ul><li>None</li></ul>                |

#### [binaryToTable](#binaryToTable)
| **Signature**                               | `cp.plist.binaryToTable(binaryData) -> table or nil`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Converts Binary Data into a LUA Table.                                                                     |
| **Parameters**                              | <ul><li>binaryData - Binary data</li></ul> |
| **Returns**                                 | <ul><li>A table of the plist data</li></ul>          |
| **Notes**                                   | <ul><li>None</li></ul>                |

#### [fileToTable](#fileToTable)
| **Signature**                               | `cp.plist.fileToTable(plistFileName) -> table or nil`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Converts plist data from a binary or XML file into a LUA Table.                                                                     |
| **Parameters**                              | <ul><li>plistFileName - Path & Filename of the XML File</li></ul> |
| **Returns**                                 | <ul><li>A table of plist data</li></ul>          |
| **Notes**                                   | <ul><li>None</li></ul>                |

#### [xmlFileToTable](#xmlFileToTable)
| **Signature**                               | `cp.plist.xmlFileToTable(plistFileName) -> table or nil`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Converts XML data from a file into a LUA Table.                                                                     |
| **Parameters**                              | <ul><li>plistFileName - Path & Filename of the XML File</li></ul> |
| **Returns**                                 | <ul><li>A table of plist data</li></ul>          |
| **Notes**                                   | <ul><li>None</li></ul>                |

