# [docs](index.md) » cp.plist
---

Reads & Writes plist data.

## Submodules
 * [cp.plist.archiver](cp.plist.archiver.md)
 * [cp.plist.plistParser](cp.plist.plistParser.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [base64ToTable](#base64totable)
 * [binaryFileToTable](#binaryfiletotable)
 * [binaryFileToXML](#binaryfiletoxml)
 * [binaryToTable](#binarytotable)
 * [fileToTable](#filetotable)
 * [isBinaryPlist](#isbinaryplist)
 * [xmlFileToTable](#xmlfiletotable)
 * [xmlToTable](#xmltotable)

## API Documentation

### Functions

#### [base64ToTable](#base64totable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.base64ToTable(base64Data) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts base64 encoded Property List string into a Table.                                                                                         |
| **Parameters**                                       | <ul><li>base64Data - Binary data encoded in base64 as a string</li></ul> |
| **Returns**                                          | <ul><li>A table of the plist data</li><li>A error message as string if an error occurs</li></ul>          |

#### [binaryFileToTable](#binaryfiletotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.binaryFileToTable(plistFileName) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts the data from a Binary File into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>plistFileName - Path & Filename of the Binary File</li></ul> |
| **Returns**                                          | <ul><li>data				- A table of plist data, or `nil` if there was a problem.</li><li>err				- The error message, or `nil` if there were no problems.</li></ul>          |

#### [binaryFileToXML](#binaryfiletoxml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.binaryFileToXML(plistFileName) -> string | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts the data from a Binary plist File into XML as a string.                                                                                         |
| **Parameters**                                       | <ul><li>plistFileName - Path & Filename of the Binary File</li></ul> |
| **Returns**                                          | <ul><li>data				- A string of XML data</li><li>err				- The error message, or `nil` if there were no problems.</li></ul>          |

#### [binaryToTable](#binarytotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.binaryToTable(binaryData) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts Binary Data into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>binaryData		- Binary data</li></ul> |
| **Returns**                                          | <ul><li>data				- A string of XML data</li><li>err				- The error message, or `nil` if there were no problems.</li></ul>          |

#### [fileToTable](#filetotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.fileToTable(plistFileName) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts plist data from a binary or XML file into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>plistFileName	- Path & Filename of the XML File</li></ul> |
| **Returns**                                          | <ul><li>data				- A table of plist data, or `nil` if there was a problem.</li><li>err				- The error message, or `nil` if there were no problems.</li></ul>          |

#### [isBinaryPlist](#isbinaryplist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.isBinaryPlist(plistList) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns true if plistList is a binary plist file otherwise false                                                                                         |
| **Parameters**                                       | <ul><li>plistList - Path to the file</li></ul> |
| **Returns**                                          | <ul><li>Boolean</li></ul>          |

#### [xmlFileToTable](#xmlfiletotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.xmlFileToTable(plistFileName) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts XML data from a file into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>plistFileName	- Path & Filename of the XML File</li></ul> |
| **Returns**                                          | <ul><li>data				- A table of plist data, or `nil` if there was a problem.</li><li>err				- The error message, or `nil` if there were no problems.</li></ul>          |

#### [xmlToTable](#xmltotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.xmlToTable(plistXml) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts an XML plist string into a LUA Table.                                                                                         |
| **Parameters**                                       | <ul><li>plistXml	        - The XML string</li></ul> |
| **Returns**                                          | <ul><li>data				- A table of plist data, or `nil` if there was a problem.</li><li>err				- The error message, or `nil` if there were no problems.</li></ul>          |

