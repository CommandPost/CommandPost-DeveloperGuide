# [docs](index.md) » cp.plist.archiver
---

Supports 'defrosting' a table which is made up from an 'NSKeyArchiver' record.

## API Overview
* Functions - API calls offered directly by the extension
 * [unarchive](#unarchive)
 * [unarchiveFile](#unarchivefile)

## API Documentation

### Functions

#### [unarchive](#unarchive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.archiver.unarchive(archive, defrostFn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unarchives a LUA table which was archived into a plist using the NSKeyedArchiver.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`archive`		- the table containing the archive plist as a table</li><li markdown="1">`defrostFn`	- (optional) a function which will be passed an object with a '$class' entry</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The unarchived plist table</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">A 'defrost' function can be provided, which will be called whenever a table with a '$class'</li><li markdown="1">   structure is present. It will receive the table and the classname and should either return a modified value</li><li markdown="1">   if the class was handled, or `nil` if it was unable to handle the class. Eg:</li></ul>                |

#### [unarchiveFile](#unarchivefile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.archiver.unarchiveFile(filename, defrostFn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unarchives a plist file which was archived into a plist using the NSKeyedArchiver.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`filename`	- the file containing the archive plist</li><li markdown="1">`defrostFn`	- (optional) a function which will be passed an object with a '$class' entry</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The unarchived plist.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">A 'defrost' function can be provided, which will be called whenever a table with a '$class'</li><li markdown="1">   structure is present. It will receive the table and the classname and should either return a modified value</li><li markdown="1">   if the class was handled, or `nil` if it was unable to handle the class. Eg:</li></ul>                |

