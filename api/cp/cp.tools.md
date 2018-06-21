# [docs](index.md) » cp.tools
---

A collection of handy miscellaneous tools for Lua development.

## API Overview
* Functions - API calls offered directly by the extension
 * [cleanupButtonText](#cleanupbuttontext)
 * [dirFiles](#dirfiles)
 * [doesDirectoryExist](#doesdirectoryexist)
 * [doesFileExist](#doesfileexist)
 * [doubleLeftClick](#doubleleftclick)
 * [endsWith](#endswith)
 * [ensureDirectoryExists](#ensuredirectoryexists)
 * [executeWithAdministratorPrivileges](#executewithadministratorprivileges)
 * [firstToUpper](#firsttoupper)
 * [getEmail](#getemail)
 * [getExternalDevices](#getexternaldevices)
 * [getFilenameFromPath](#getfilenamefrompath)
 * [getFullname](#getfullname)
 * [getKeysSortedByValue](#getkeyssortedbyvalue)
 * [getmacOSVersion](#getmacosversion)
 * [getModelName](#getmodelname)
 * [getRAMSize](#getramsize)
 * [getScreenshotsAsBase64](#getscreenshotsasbase64)
 * [getThunderboltDevices](#getthunderboltdevices)
 * [getUSBDevices](#getusbdevices)
 * [getVRAMSize](#getvramsize)
 * [iconFallback](#iconfallback)
 * [incrementFilename](#incrementfilename)
 * [isNumberString](#isnumberstring)
 * [isOffScreen](#isoffscreen)
 * [leftClick](#leftclick)
 * [lines](#lines)
 * [macOSVersion](#macosversion)
 * [mergeTable](#mergetable)
 * [ninjaDoubleClick](#ninjadoubleclick)
 * [ninjaMouseAction](#ninjamouseaction)
 * [ninjaMouseClick](#ninjamouseclick)
 * [numberToWord](#numbertoword)
 * [playErrorSound](#playerrorsound)
 * [removeFilenameFromPath](#removefilenamefrompath)
 * [removeFromTable](#removefromtable)
 * [rmdir](#rmdir)
 * [round](#round)
 * [safeFilename](#safefilename)
 * [spairs](#spairs)
 * [split](#split)
 * [splitOnColumn](#splitoncolumn)
 * [stringMaxLength](#stringmaxlength)
 * [tableContains](#tablecontains)
 * [tableCount](#tablecount)
 * [trim](#trim)
 * [unescape](#unescape)
 * [urlQueryStringDecode](#urlquerystringdecode)
 * [volumeFormat](#volumeformat)

## API Documentation

### Functions

#### [cleanupButtonText](#cleanupbuttontext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.cleanupButtonText(value) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes the … symbol and multiple >'s from a string.                                                                                         |
| **Parameters**                                       |  * value - A string                                       |
| **Returns**                                          |  * A cleaned string                                                |

#### [dirFiles](#dirfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.dirFiles(path) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all the files in a directory                                                                                         |
| **Parameters**                                       |  * path - A path as string                                       |
| **Returns**                                          |  * A table containing filenames as strings.                                                |

#### [doesDirectoryExist](#doesdirectoryexist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doesDirectoryExist(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether or not a directory exists.                                                                                         |
| **Parameters**                                       |  * path - Path to the directory                                       |
| **Returns**                                          |  * `true` if the directory exists otherwise `false`                                                |

#### [doesFileExist](#doesfileexist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doesFileExist(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether or not a file exists.                                                                                         |
| **Parameters**                                       |  * path - Path to the file                                       |
| **Returns**                                          |  * `true` if the file exists otherwise `false`                                                |

#### [doubleLeftClick](#doubleleftclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doubleLeftClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Left Mouse Double Click.                                                                                         |
| **Parameters**                                       |  * point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * delay - The optional delay between multiple mouse clicks                                       |
| **Returns**                                          |  * None                                                |

#### [endsWith](#endswith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.endsWith(str, ending) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if `str` has the same ending as `ending`.                                                                                         |
| **Parameters**                                       |  * str       - String to analysis * ending    - End of string to compare against                                       |
| **Returns**                                          |  * table                                                |

#### [ensureDirectoryExists](#ensuredirectoryexists)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ensureDirectoryExists(rootPath, ...) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Ensures all steps on a provided path exist. If not, attempts to create them.                                                                                         |
| **Parameters**                                       |  * `rootPath` - The root path (should already exist). * `...`      - The list of path steps to create                                       |
| **Returns**                                          |  * The full path, if it exists, or `nil` if unable to create the directory for some reason.                                                |

#### [executeWithAdministratorPrivileges](#executewithadministratorprivileges)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.executeWithAdministratorPrivileges(input[, stopOnError]) -> boolean or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes a single or multiple shell commands with Administrator Privileges.                                                                                         |
| **Parameters**                                       |  * input - either a string or a table of strings of commands you want to execute * stopOnError - an optional variable that stops processing multiple commands when an individual commands returns an error                                       |
| **Returns**                                          |  * `true` if successful, `false` if cancelled and a string if there's an error.                                                |

#### [firstToUpper](#firsttoupper)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.firstToUpper(str) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Makes the first letter of a string uppercase.                                                                                         |
| **Parameters**                                       |  * str - The string you want to manipulate                                       |
| **Returns**                                          |  * A string                                                |

#### [getEmail](#getemail)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getEmail() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current users Email, otherwise an empty string.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * String                                                |

#### [getExternalDevices](#getexternaldevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getExternalDevices() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a string of USB & Thunderbolt Devices.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * String                                                |

#### [getFilenameFromPath](#getfilenamefrompath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getFilenameFromPath(input[, removeExtension]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the filename component of a path.                                                                                         |
| **Parameters**                                       |  * input - The path * removeExtension - (optional) set to `true` if the file extension should be removed                                       |
| **Returns**                                          |  * A string of the filename.                                                |

#### [getFullname](#getfullname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getFullname() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current users Full Name, otherwise an empty string.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * String                                                |

#### [getKeysSortedByValue](#getkeyssortedbyvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getKeysSortedByValue(tbl, sortFunction) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sorts table keys by a value                                                                                         |
| **Parameters**                                       |  * tbl - the table you want to sort * sortFunction - the function you want to use to sort the table                                       |
| **Returns**                                          |  * A sorted table                                                |

#### [getmacOSVersion](#getmacosversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getmacOSVersion() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the macOS Version in the format that Apple's Feedback Form expects.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The macOS version as a string or "" if unknown.                                                |

#### [getModelName](#getmodelname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getModelName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns Model Name of Hardware.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * String                                                |

#### [getRAMSize](#getramsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getRAMSize() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns RAM Size in a format Apple's Feedback form expects.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The RAM size as a string, or "" if unknown.                                                |

#### [getScreenshotsAsBase64](#getscreenshotsasbase64)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getScreenshotsAsBase64() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Captures all available screens and saves them as base64 encodes in a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing base64 images of all available screens.                                                |

#### [getThunderboltDevices](#getthunderboltdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getThunderboltDevices() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a string of Thunderbolt Devices.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * String                                                |

#### [getUSBDevices](#getusbdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getUSBDevices() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a string of USB Devices.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * String                                                |

#### [getVRAMSize](#getvramsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getVRAMSize() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the VRAM size in format suitable for Apple's Final Cut Pro feedback form or "" if unknown.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * String                                                |

#### [iconFallback](#iconfallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.iconFallback(paths) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Excepts one or more paths to an icon, checks to see if they exist (in the order that they're given), and if none exist, returns the CommandPost icon path.                                                                                         |
| **Parameters**                                       |  * paths - One or more paths to an icon                                       |
| **Returns**                                          |  * A string                                                |

#### [incrementFilename](#incrementfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.incrementFilename(value) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Increments the filename.                                                                                         |
| **Parameters**                                       |  * value - A string                                       |
| **Returns**                                          |  * A string                                                |

#### [isNumberString](#isnumberstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.isNumberString(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether or not value is a number string.                                                                                         |
| **Parameters**                                       |  * value - the string you want to check                                       |
| **Returns**                                          |  * `true` if value is a number string, otherwise `false`.                                                |

#### [isOffScreen](#isoffscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.isOffScreen(rect) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Determines if the given rect is off screen or not.                                                                                         |
| **Parameters**                                       |  * rect - the rect you want to check                                       |
| **Returns**                                          |  * `true` if offscreen otherwise `false`                                                |

#### [leftClick](#leftclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.leftClick(point[, delay, clickNumber]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Left Mouse Click.                                                                                         |
| **Parameters**                                       |  * point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * delay - The optional delay between multiple mouse clicks * clickNumber - The optional number of times you want to perform the click.                                       |
| **Returns**                                          |  * None                                                |

#### [lines](#lines)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.lines(string) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Splits a string containing multiple lines of text into a table.                                                                                         |
| **Parameters**                                       |  * string - the string you want to process                                       |
| **Returns**                                          |  * A table or `nil` if the parameter is not a string.                                                |

#### [macOSVersion](#macosversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.macOSVersion() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a the macOS Version as a single string.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A string containing the macOS version                                                |

#### [mergeTable](#mergetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.mergeTable(target, ...) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Merges multiple tables into a target table.                                                                                         |
| **Parameters**                                       |  * target   - The target table * ...      - Any other tables you want to merge into target                                       |
| **Returns**                                          |  * Table                                                |

#### [ninjaDoubleClick](#ninjadoubleclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaDoubleClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a mouse double click, but returns the mouse to the original position without the users knowledge.                                                                                         |
| **Parameters**                                       |  * point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * delay - The optional delay between multiple mouse clicks                                       |
| **Returns**                                          |  * None                                                |

#### [ninjaMouseAction](#ninjamouseaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaMouseAction(point, fn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves the mouse to a point, performs a function, then returns the mouse to the original point.                                                                                         |
| **Parameters**                                       |  * point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * fn - A function you want to perform                                       |
| **Returns**                                          |  * None                                                |

#### [ninjaMouseClick](#ninjamouseclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaMouseClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a mouse click, but returns the mouse to the original position without the users knowledge.                                                                                         |
| **Parameters**                                       |  * point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * delay - The optional delay between multiple mouse clicks                                       |
| **Returns**                                          |  * None                                                |

#### [numberToWord](#numbertoword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.numberToWord(number) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts a number to a string (i.e. 1 becomes "One").                                                                                         |
| **Parameters**                                       |  * number - A whole number between 0 and 10                                       |
| **Returns**                                          |  * A string                                                |

#### [playErrorSound](#playerrorsound)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.playErrorSound() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Plays the "Funk" error sound.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [removeFilenameFromPath](#removefilenamefrompath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.removeFilenameFromPath(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes the filename from a path.                                                                                         |
| **Parameters**                                       |  * string - The path                                       |
| **Returns**                                          |  * A string of the path without the filename.                                                |

#### [removeFromTable](#removefromtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.removeFromTable(table, element) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes a string from a table of strings                                                                                         |
| **Parameters**                                       |  * table - the table you want to check * element - the string you want to remove                                       |
| **Returns**                                          |  * A table                                                |

#### [rmdir](#rmdir)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.rmdir(path[, recursive]) -> true | nil, err` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Attempts to remove the directory at the specified path, optionally removing                                                                                         |
| **Parameters**                                       |  * `path`        - The absolute path to remove * `recursive`   - If `true`, the contents of the directory will be removed first.                                       |
| **Returns**                                          |  * `true` if successful, or `nil, err` if there was a problem.                                                |

#### [round](#round)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.round(num, numDecimalPlaces) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Rounds a number to a set number of decimal places                                                                                         |
| **Parameters**                                       |  * num - The number you want to round * numDecimalPlaces - How many numbers of decimal places (defaults to 0)                                       |
| **Returns**                                          |  * A rounded number                                                |

#### [safeFilename](#safefilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.safeFilename(value[, defaultValue]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a Safe Filename.                                                                                         |
| **Parameters**                                       |  * value - a string you want to make safe * defaultValue - the optional default filename to use if the value is not valid                                       |
| **Returns**                                          |  * A string of the safe filename                                                |
| **Notes**                                            |  * Returns "filename" is both `value` and `defaultValue` are `nil`.                                                      |

#### [spairs](#spairs)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.spairs(t, order) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | A customised version of pairs, called `spairs` because it iterates over the table in a sorted order.                                                                                         |
| **Parameters**                                       |  * t     - The table to process * order - The function of how to sort the table.                                       |
| **Returns**                                          |  * A iterator function.                                                |
| **Notes**                                            |  * Author: [Michal Kottman](https://stackoverflow.com/a/15706820)                                                      |

#### [split](#split)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.split(str, pat) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Splits a string with a pattern.                                                                                         |
| **Parameters**                                       |  * str - The string to split * pat - The pattern                                       |
| **Returns**                                          |  * Table                                                |

#### [splitOnColumn](#splitoncolumn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.splitOnColumn() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Splits a string on a column.                                                                                         |
| **Parameters**                                       |  * Input                                       |
| **Returns**                                          |  * String                                                |

#### [stringMaxLength](#stringmaxlength)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.stringMaxLength(string, maxLength[, optionalEnd]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Trims a string based on a maximum length.                                                                                         |
| **Parameters**                                       |  * maxLength - The length of the string as a number * optionalEnd - A string that is applied to the end of the input string if the input string is larger than the maximum length.                                       |
| **Returns**                                          |  * A string                                                |

#### [tableContains](#tablecontains)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.tableContains(table, element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Does a element exist in a table?                                                                                         |
| **Parameters**                                       |  * table - the table you want to check * element - the element you want to check for                                       |
| **Returns**                                          |  * Boolean                                                |

#### [tableCount](#tablecount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.tableCount(table) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns how many items are in a table.                                                                                         |
| **Parameters**                                       |  * table - The table you want to count.                                       |
| **Returns**                                          |  * The number of items in the table.                                                |

#### [trim](#trim)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.trim(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Trims the whitespaces from a string                                                                                         |
| **Parameters**                                       |  * string - the string you want to trim                                       |
| **Returns**                                          |  * A trimmed string                                                |

#### [unescape](#unescape)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.unescape(str) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes any URL encoding in the provided string.                                                                                         |
| **Parameters**                                       |  * str - the string to decode                                       |
| **Returns**                                          |  * A string with all "+" characters converted to spaces and all percent encoded sequences converted to their ASCII equivalents.                                                |

#### [urlQueryStringDecode](#urlquerystringdecode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.urlQueryStringDecode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Decodes a URL Query String                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Decoded URL Query String as string                                                |

#### [volumeFormat](#volumeformat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.volumeFormat(path) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gives you the file system volume format of a path.                                                                                         |
| **Parameters**                                       |  * path - the path you want to check as a string                                       |
| **Returns**                                          |  * The `NSURLVolumeLocalizedFormatDescriptionKey` as a string, otherwise `nil`.                                                |

