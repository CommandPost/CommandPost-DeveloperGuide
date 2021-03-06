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
| **Type**                                             | Function |
| **Description**                                      | Unarchives a LUA table which was archived into a plist using the NSKeyedArchiver. |
| **Parameters**                                       | <ul><li><code>archive</code>        - the table containing the archive plist as a table</li><li><code>defrostFn</code>  - (optional) a function which will be passed an object with a '$class' entry</li></ul> |
| **Returns**                                          | <ul><li>The unarchived plist table</li></ul> |
| **Notes**                                            | <ul><li>A 'defrost' function can be provided, which will be called whenever a table with a '$class'   structure is present. It will receive the table and the classname and should either return a modified value   if the class was handled, or <code>nil</code> if it was unable to handle the class. Eg:</li></ul> |

#### [unarchiveFile](#unarchivefile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plist.archiver.unarchiveFile(filename, defrostFn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Unarchives a plist file which was archived into a plist using the NSKeyedArchiver. |
| **Parameters**                                       | <ul><li><code>filename</code>   - the file containing the archive plist</li><li><code>defrostFn</code>  - (optional) a function which will be passed an object with a '$class' entry</li></ul> |
| **Returns**                                          | <ul><li>The unarchived plist.</li></ul> |
| **Notes**                                            | <ul><li>A 'defrost' function can be provided, which will be called whenever a table with a '$class'   structure is present. It will receive the table and the classname and should either return a modified value   if the class was handled, or <code>nil</code> if it was unable to handle the class. Eg:</li></ul> |

