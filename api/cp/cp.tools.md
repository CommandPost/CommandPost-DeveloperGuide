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
| **Parameters**                                       | <ul><br /><li>value - A string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A cleaned string</li><br /></ul>                                           |

#### [dirFiles](#dirfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.dirFiles(path) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all the files in a directory                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - A path as string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing filenames as strings.</li><br /></ul>                                           |

#### [doesDirectoryExist](#doesdirectoryexist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doesDirectoryExist(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether or not a directory exists.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - Path to the directory</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the directory exists otherwise <code>false</code></li><br /></ul>                                           |

#### [doesFileExist](#doesfileexist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doesFileExist(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether or not a file exists.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - Path to the file</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the file exists otherwise <code>false</code></li><br /></ul>                                           |

#### [doubleLeftClick](#doubleleftclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doubleLeftClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Left Mouse Double Click.                                                                                         |
| **Parameters**                                       | <ul><br /><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * delay - The optional delay between multiple mouse clicks</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [endsWith](#endswith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.endsWith(str, ending) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if `str` has the same ending as `ending`.                                                                                         |
| **Parameters**                                       | <ul><br /><li>str       - String to analysis * ending    - End of string to compare against</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>table</li><br /></ul>                                           |

#### [ensureDirectoryExists](#ensuredirectoryexists)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ensureDirectoryExists(rootPath, ...) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Ensures all steps on a provided path exist. If not, attempts to create them.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>rootPath</code> - The root path (should already exist). * <code>...</code>      - The list of path steps to create</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The full path, if it exists, or <code>nil</code> if unable to create the directory for some reason.</li><br /></ul>                                           |

#### [executeWithAdministratorPrivileges](#executewithadministratorprivileges)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.executeWithAdministratorPrivileges(input[, stopOnError]) -> boolean or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Executes a single or multiple shell commands with Administrator Privileges.                                                                                         |
| **Parameters**                                       | <ul><br /><li>input - either a string or a table of strings of commands you want to execute * stopOnError - an optional variable that stops processing multiple commands when an individual commands returns an error</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if successful, <code>false</code> if cancelled and a string if there's an error.</li><br /></ul>                                           |

#### [firstToUpper](#firsttoupper)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.firstToUpper(str) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Makes the first letter of a string uppercase.                                                                                         |
| **Parameters**                                       | <ul><br /><li>str - The string you want to manipulate</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string</li><br /></ul>                                           |

#### [getEmail](#getemail)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getEmail() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current users Email, otherwise an empty string.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String</li><br /></ul>                                           |

#### [getExternalDevices](#getexternaldevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getExternalDevices() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a string of USB & Thunderbolt Devices.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String</li><br /></ul>                                           |

#### [getFilenameFromPath](#getfilenamefrompath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getFilenameFromPath(input[, removeExtension]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the filename component of a path.                                                                                         |
| **Parameters**                                       | <ul><br /><li>input - The path * removeExtension - (optional) set to <code>true</code> if the file extension should be removed</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string of the filename.</li><br /></ul>                                           |

#### [getFullname](#getfullname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getFullname() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current users Full Name, otherwise an empty string.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String</li><br /></ul>                                           |

#### [getKeysSortedByValue](#getkeyssortedbyvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getKeysSortedByValue(tbl, sortFunction) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sorts table keys by a value                                                                                         |
| **Parameters**                                       | <ul><br /><li>tbl - the table you want to sort * sortFunction - the function you want to use to sort the table</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A sorted table</li><br /></ul>                                           |

#### [getmacOSVersion](#getmacosversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getmacOSVersion() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the macOS Version in the format that Apple's Feedback Form expects.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The macOS version as a string or "" if unknown.</li><br /></ul>                                           |

#### [getModelName](#getmodelname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getModelName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns Model Name of Hardware.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String</li><br /></ul>                                           |

#### [getRAMSize](#getramsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getRAMSize() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns RAM Size in a format Apple's Feedback form expects.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The RAM size as a string, or "" if unknown.</li><br /></ul>                                           |

#### [getScreenshotsAsBase64](#getscreenshotsasbase64)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getScreenshotsAsBase64() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Captures all available screens and saves them as base64 encodes in a table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing base64 images of all available screens.</li><br /></ul>                                           |

#### [getThunderboltDevices](#getthunderboltdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getThunderboltDevices() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a string of Thunderbolt Devices.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String</li><br /></ul>                                           |

#### [getUSBDevices](#getusbdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getUSBDevices() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a string of USB Devices.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String</li><br /></ul>                                           |

#### [getVRAMSize](#getvramsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getVRAMSize() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the VRAM size in format suitable for Apple's Final Cut Pro feedback form or "" if unknown.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String</li><br /></ul>                                           |

#### [iconFallback](#iconfallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.iconFallback(paths) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Excepts one or more paths to an icon, checks to see if they exist (in the order that they're given), and if none exist, returns the CommandPost icon path.                                                                                         |
| **Parameters**                                       | <ul><br /><li>paths - One or more paths to an icon</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string</li><br /></ul>                                           |

#### [incrementFilename](#incrementfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.incrementFilename(value) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Increments the filename.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value - A string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string</li><br /></ul>                                           |

#### [isNumberString](#isnumberstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.isNumberString(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns whether or not value is a number string.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value - the string you want to check</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if value is a number string, otherwise <code>false</code>.</li><br /></ul>                                           |

#### [isOffScreen](#isoffscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.isOffScreen(rect) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Determines if the given rect is off screen or not.                                                                                         |
| **Parameters**                                       | <ul><br /><li>rect - the rect you want to check</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if offscreen otherwise <code>false</code></li><br /></ul>                                           |

#### [leftClick](#leftclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.leftClick(point[, delay, clickNumber]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a Left Mouse Click.                                                                                         |
| **Parameters**                                       | <ul><br /><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * delay - The optional delay between multiple mouse clicks * clickNumber - The optional number of times you want to perform the click.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [lines](#lines)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.lines(string) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Splits a string containing multiple lines of text into a table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>string - the string you want to process</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table or <code>nil</code> if the parameter is not a string.</li><br /></ul>                                           |

#### [macOSVersion](#macosversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.macOSVersion() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a the macOS Version as a single string.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string containing the macOS version</li><br /></ul>                                           |

#### [mergeTable](#mergetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.mergeTable(target, ...) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Merges multiple tables into a target table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>target   - The target table * ...      - Any other tables you want to merge into target</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table</li><br /></ul>                                           |

#### [ninjaDoubleClick](#ninjadoubleclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaDoubleClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a mouse double click, but returns the mouse to the original position without the users knowledge.                                                                                         |
| **Parameters**                                       | <ul><br /><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * delay - The optional delay between multiple mouse clicks</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [ninjaMouseAction](#ninjamouseaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaMouseAction(point, fn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves the mouse to a point, performs a function, then returns the mouse to the original point.                                                                                         |
| **Parameters**                                       | <ul><br /><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * fn - A function you want to perform</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [ninjaMouseClick](#ninjamouseclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaMouseClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs a mouse click, but returns the mouse to the original position without the users knowledge.                                                                                         |
| **Parameters**                                       | <ul><br /><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to * delay - The optional delay between multiple mouse clicks</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [numberToWord](#numbertoword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.numberToWord(number) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts a number to a string (i.e. 1 becomes "One").                                                                                         |
| **Parameters**                                       | <ul><br /><li>number - A whole number between 0 and 10</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string</li><br /></ul>                                           |

#### [playErrorSound](#playerrorsound)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.playErrorSound() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Plays the "Funk" error sound.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [removeFilenameFromPath](#removefilenamefrompath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.removeFilenameFromPath(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes the filename from a path.                                                                                         |
| **Parameters**                                       | <ul><br /><li>string - The path</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string of the path without the filename.</li><br /></ul>                                           |

#### [removeFromTable](#removefromtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.removeFromTable(table, element) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes a string from a table of strings                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - the table you want to check * element - the string you want to remove</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table</li><br /></ul>                                           |

#### [rmdir](#rmdir)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.rmdir(path[, recursive]) -> true | nil, err` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Attempts to remove the directory at the specified path, optionally removing                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>path</code>        - The absolute path to remove * <code>recursive</code>   - If <code>true</code>, the contents of the directory will be removed first.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if successful, or <code>nil, err</code> if there was a problem.</li><br /></ul>                                           |

#### [round](#round)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.round(num, numDecimalPlaces) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Rounds a number to a set number of decimal places                                                                                         |
| **Parameters**                                       | <ul><br /><li>num - The number you want to round * numDecimalPlaces - How many numbers of decimal places (defaults to 0)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A rounded number</li><br /></ul>                                           |

#### [safeFilename](#safefilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.safeFilename(value[, defaultValue]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a Safe Filename.                                                                                         |
| **Parameters**                                       | <ul><br /><li>value - a string you want to make safe * defaultValue - the optional default filename to use if the value is not valid</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string of the safe filename</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Returns "filename" is both <code>value</code> and <code>defaultValue</code> are <code>nil</code>.</li><br /></ul>                                             |

#### [spairs](#spairs)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.spairs(t, order) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | A customised version of pairs, called `spairs` because it iterates over the table in a sorted order.                                                                                         |
| **Parameters**                                       | <ul><br /><li>t     - The table to process * order - The function of how to sort the table.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A iterator function.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Author: <a href="https://stackoverflow.com/a/15706820">Michal Kottman</a></li><br /></ul>                                             |

#### [split](#split)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.split(str, pat) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Splits a string with a pattern.                                                                                         |
| **Parameters**                                       | <ul><br /><li>str - The string to split * pat - The pattern</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table</li><br /></ul>                                           |

#### [splitOnColumn](#splitoncolumn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.splitOnColumn() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Splits a string on a column.                                                                                         |
| **Parameters**                                       | <ul><br /><li>Input</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String</li><br /></ul>                                           |

#### [stringMaxLength](#stringmaxlength)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.stringMaxLength(string, maxLength[, optionalEnd]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Trims a string based on a maximum length.                                                                                         |
| **Parameters**                                       | <ul><br /><li>maxLength - The length of the string as a number * optionalEnd - A string that is applied to the end of the input string if the input string is larger than the maximum length.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string</li><br /></ul>                                           |

#### [tableContains](#tablecontains)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.tableContains(table, element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Does a element exist in a table?                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - the table you want to check * element - the element you want to check for</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Boolean</li><br /></ul>                                           |

#### [tableCount](#tablecount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.tableCount(table) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns how many items are in a table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - The table you want to count.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The number of items in the table.</li><br /></ul>                                           |

#### [trim](#trim)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.trim(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Trims the whitespaces from a string                                                                                         |
| **Parameters**                                       | <ul><br /><li>string - the string you want to trim</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A trimmed string</li><br /></ul>                                           |

#### [unescape](#unescape)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.unescape(str) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes any URL encoding in the provided string.                                                                                         |
| **Parameters**                                       | <ul><br /><li>str - the string to decode</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string with all "+" characters converted to spaces and all percent encoded sequences converted to their ASCII equivalents.</li><br /></ul>                                           |

#### [urlQueryStringDecode](#urlquerystringdecode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.urlQueryStringDecode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Decodes a URL Query String                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Decoded URL Query String as string</li><br /></ul>                                           |

#### [volumeFormat](#volumeformat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.volumeFormat(path) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gives you the file system volume format of a path.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - the path you want to check as a string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The <code>NSURLVolumeLocalizedFormatDescriptionKey</code> as a string, otherwise <code>nil</code>.</li><br /></ul>                                           |

