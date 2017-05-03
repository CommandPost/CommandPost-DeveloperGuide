# [docs](index.md) » cp.tools
---

A collection of handy Lua tools for CommandPost.

## API Overview
* Functions - API calls offered directly by the extension
 * [cleanupButtonText](#cleanupbuttontext)
 * [doesDirectoryExist](#doesdirectoryexist)
 * [doesFileExist](#doesfileexist)
 * [doubleLeftClick](#doubleleftclick)
 * [executeWithAdministratorPrivileges](#executewithadministratorprivileges)
 * [incrementFilename](#incrementfilename)
 * [leftClick](#leftclick)
 * [lines](#lines)
 * [macOSVersion](#macosversion)
 * [modifierMaskToModifiers](#modifiermasktomodifiers)
 * [modifierMatch](#modifiermatch)
 * [ninjaDoubleClick](#ninjadoubleclick)
 * [ninjaMouseAction](#ninjamouseaction)
 * [ninjaMouseClick](#ninjamouseclick)
 * [numberToWord](#numbertoword)
 * [removeFilenameFromPath](#removefilenamefrompath)
 * [safeFilename](#safefilename)
 * [stringMaxLength](#stringmaxlength)
 * [tableCount](#tablecount)
 * [trim](#trim)

## API Documentation

### Functions

#### [cleanupButtonText](#cleanupbuttontext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.cleanupButtonText(value) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes the … symbol and multiple >'s from a string.                                                                                         |
| **Parameters**                                       | <ul><li>value - A string</li></ul> |
| **Returns**                                          | <ul><li>A cleaned string</li></ul>          |

#### [doesDirectoryExist](#doesdirectoryexist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doesDirectoryExist(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether or not a directory exists.                                                                                         |
| **Parameters**                                       | <ul><li>path - Path to the directory</li></ul> |
| **Returns**                                          | <ul><li>`true` if the directory exists otherwise `false`</li></ul>          |

#### [doesFileExist](#doesfileexist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doesFileExist(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether or not a file exists.                                                                                         |
| **Parameters**                                       | <ul><li>path - Path to the file</li></ul> |
| **Returns**                                          | <ul><li>`true` if the file exists otherwise `false`</li></ul>          |

#### [doubleLeftClick](#doubleleftclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doubleLeftClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Left Mouse Double Click.                                                                                         |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [executeWithAdministratorPrivileges](#executewithadministratorprivileges)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.executeWithAdministratorPrivileges(input[, stopOnError]) -> boolean or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes a single or multiple shell commands with Administrator Privileges.                                                                                         |
| **Parameters**                                       | <ul><li>input - either a string or a table of strings of commands you want to execute</li><li>stopOnError - an optional variable that stops processing multiple commands when an individual commands returns an error</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful, `false` if cancelled and a string if there's an error.</li></ul>          |

#### [incrementFilename](#incrementfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.incrementFilename(value) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a table of file names for the given path.                                                                                         |
| **Parameters**                                       | <ul><li>path - A path as string</li></ul> |
| **Returns**                                          | <ul><li>A table containing filenames as strings.</li></ul>          |

#### [leftClick](#leftclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.leftClick(point[, delay, clickNumber]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Left Mouse Click.                                                                                         |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li><li>clickNumber - The optional number of times you want to perform the click.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [lines](#lines)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.lines(string) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Splits a string containing multiple lines of text into a table.                                                                                         |
| **Parameters**                                       | <ul><li>string - the string you want to process</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul>          |

#### [macOSVersion](#macosversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.macOSVersion() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a the macOS Version as a single string.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the macOS version</li></ul>          |

#### [modifierMaskToModifiers](#modifiermasktomodifiers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.modifierMaskToModifiers() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Translate Keyboard Modifiers from Apple's Plist Format into Hammerspoon Format                                                                                         |
| **Parameters**                                       | <ul><li>value - Modifiers String</li></ul> |
| **Returns**                                          | <ul><li>table</li></ul>          |

#### [modifierMatch](#modifiermatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.modifierMatch(inputA, inputB) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Compares two modifier tables.                                                                                         |
| **Parameters**                                       | <ul><li>inputA - table of modifiers</li><li>inputB - table of modifiers</li></ul> |
| **Returns**                                          | <ul><li>`true` if there's a match otherwise `false`</li></ul>          |
| **Notes**                                            | <ul><li>This function only takes into account 'ctrl', 'alt', 'cmd', 'shift'.</li></ul>                |

#### [ninjaDoubleClick](#ninjadoubleclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaDoubleClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a mouse double click, but returns the mouse to the original position without the users knowledge.                                                                                         |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [ninjaMouseAction](#ninjamouseaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaMouseAction(point, fn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves the mouse to a point, performs a function, then returns the mouse to the original point.                                                                                         |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>fn - A function you want to perform</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [ninjaMouseClick](#ninjamouseclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaMouseClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a mouse click, but returns the mouse to the original position without the users knowledge.                                                                                         |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [numberToWord](#numbertoword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.numberToWord(number) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts a number to a string (i.e. 1 becomes "One").                                                                                         |
| **Parameters**                                       | <ul><li>number - A whole number between 0 and 10</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul>          |

#### [removeFilenameFromPath](#removefilenamefrompath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.removeFilenameFromPath(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes the filename from a path.                                                                                         |
| **Parameters**                                       | <ul><li>string - The path</li></ul> |
| **Returns**                                          | <ul><li>A string of the path without the filename.</li></ul>          |

#### [safeFilename](#safefilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.safeFilename(value[, defaultValue]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a Safe Filename.                                                                                         |
| **Parameters**                                       | <ul><li>value - a string you want to make safe</li><li>defaultValue - the optional default filename to use if the value is not valid</li></ul> |
| **Returns**                                          | <ul><li>A string of the safe filename</li></ul>          |
| **Notes**                                            | <ul><li>Returns "filename" is both `value` and `defaultValue` are `nil`.</li></ul>                |

#### [stringMaxLength](#stringmaxlength)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.stringMaxLength(string, maxLength[, optionalEnd]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Trims a string based on a maximum length.                                                                                         |
| **Parameters**                                       | <ul><li>maxLength - The length of the string as a number</li><li>optionalEnd - A string that is applied to the end of the input string if the input string is larger than the maximum length.</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul>          |

#### [tableCount](#tablecount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.tableCount(table) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns how many items are in a table.                                                                                         |
| **Parameters**                                       | <ul><li>table - The table you want to count.</li></ul> |
| **Returns**                                          | <ul><li>The number of items in the table.</li></ul>          |

#### [trim](#trim)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.trim(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Trims the whitespaces from a string                                                                                         |
| **Parameters**                                       | <ul><li>string - the string you want to trim</li></ul> |
| **Returns**                                          | <ul><li>A trimmed string</li></ul>          |

