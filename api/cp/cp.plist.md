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
| **Parameters**                                       |  * base64Data - Binary data encoded in base64 as a string                                       |
| **Returns**                                          |  * A table of the plist data * A error message as string if an error occurs                                                |

#### [binaryFileToTable](#binaryfiletotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.binaryFileToTable(plistFileName) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts the data from a Binary File into a LUA Table.                                                                                         |
| **Parameters**                                       |  * plistFileName - Path & Filename of the Binary File                                       |
| **Returns**                                          |  * data				- A table of plist data, or `nil` if there was a problem. * err				- The error message, or `nil` if there were no problems.                                                |

#### [binaryFileToXML](#binaryfiletoxml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.binaryFileToXML(plistFileName) -> string | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts the data from a Binary plist File into XML as a string.                                                                                         |
| **Parameters**                                       |  * plistFileName - Path & Filename of the Binary File                                       |
| **Returns**                                          |  * data				- A string of XML data * err				- The error message, or `nil` if there were no problems.                                                |

#### [binaryToTable](#binarytotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.binaryToTable(binaryData) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts Binary Data into a LUA Table.                                                                                         |
| **Parameters**                                       |  * binaryData		- Binary data                                       |
| **Returns**                                          |  * data				- A string of XML data * err				- The error message, or `nil` if there were no problems.                                                |

#### [fileToTable](#filetotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.fileToTable(plistFileName) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts plist data from a binary or XML file into a LUA Table.                                                                                         |
| **Parameters**                                       |  * plistFileName	- Path & Filename of the XML File                                       |
| **Returns**                                          |  * data				- A table of plist data, or `nil` if there was a problem. * err				- The error message, or `nil` if there were no problems.                                                |

#### [isBinaryPlist](#isbinaryplist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.isBinaryPlist(plistList) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns true if plistList is a binary plist file otherwise false                                                                                         |
| **Parameters**                                       |  * plistList - Path to the file                                       |
| **Returns**                                          |  * Boolean                                                |

#### [xmlFileToTable](#xmlfiletotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.xmlFileToTable(plistFileName) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts XML data from a file into a LUA Table.                                                                                         |
| **Parameters**                                       |  * plistFileName	- Path & Filename of the XML File                                       |
| **Returns**                                          |  * data				- A table of plist data, or `nil` if there was a problem. * err				- The error message, or `nil` if there were no problems.                                                |

#### [xmlToTable](#xmltotable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.xmlToTable(plistXml) -> table | nil, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts an XML plist string into a LUA Table.                                                                                         |
| **Parameters**                                       |  * plistXml	        - The XML string                                       |
| **Returns**                                          |  * data				- A table of plist data, or `nil` if there was a problem. * err				- The error message, or `nil` if there were no problems.                                                |

