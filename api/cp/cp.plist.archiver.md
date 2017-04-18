# [docs](index.md) » cp.plist.archiver
---

Supports 'defrosting' a table which is made up from an 'NSKeyArchiver' record.

## API Overview
* Functions - API calls offered directly by the extension
 * [unarchive](#unarchive)

## API Documentation

### Functions

#### [unarchive](#unarchive)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.plist.archiver.unarchive(archive) -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unarchives a LUA table which was archived into a plist using the NSKeyedArchiver.                                                                                         |
| **Parameters**                                       | <ul><li>`archive`		- the table containing the archive plist as a table</li><li>`defrostFn`	- (optional) a function which will be passed an object with a '$class' entry</li></ul> |
| **Returns**                                          | <ul><li>The unarchived</li></ul>          |
| **Notes**                                            | <ul><li>A 'defrost' function can be provided, which will be called whenever a table with a '$class'</li><li>   structure is present. It will receive the table and the classname and should either return a modified value</li><li>   if the class was handled, or `nil` if it was unable to handle the class. Eg:</li></ul>                |

