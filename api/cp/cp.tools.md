# [docs](index.md) » cp.tools
---

A collection of handy miscellaneous tools for Lua development.

## API Overview
* Functions - API calls offered directly by the extension
 * [camelCase](#camelcase)
 * [centre](#centre)
 * [cleanupButtonText](#cleanupbuttontext)
 * [contentsInsideBrackets](#contentsinsidebrackets)
 * [convertSingleHexStringToDecimalString](#convertsinglehexstringtodecimalstring)
 * [dirFiles](#dirfiles)
 * [doesDirectoryExist](#doesdirectoryexist)
 * [doesFileExist](#doesfileexist)
 * [doubleLeftClick](#doubleleftclick)
 * [endsWith](#endswith)
 * [ensureDirectoryExists](#ensuredirectoryexists)
 * [exactMatch](#exactmatch)
 * [executeWithAdministratorPrivileges](#executewithadministratorprivileges)
 * [findCommonWordWithinTwoStrings](#findcommonwordwithintwostrings)
 * [firstToUpper](#firsttoupper)
 * [getEmail](#getemail)
 * [getExternalDevices](#getexternaldevices)
 * [getFileExtensionFromPath](#getfileextensionfrompath)
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
 * [hexStringToString](#hexstringtostring)
 * [iconFallback](#iconfallback)
 * [incrementFilename](#incrementfilename)
 * [incrementFilenameInPath](#incrementfilenameinpath)
 * [isNumberString](#isnumberstring)
 * [isOffScreen](#isoffscreen)
 * [leftClick](#leftclick)
 * [lines](#lines)
 * [lower](#lower)
 * [macOSVersion](#macosversion)
 * [mergeTable](#mergetable)
 * [ninjaDoubleClick](#ninjadoubleclick)
 * [ninjaMouseAction](#ninjamouseaction)
 * [ninjaMouseClick](#ninjamouseclick)
 * [ninjaRightMouseClick](#ninjarightmouseclick)
 * [numberToWord](#numbertoword)
 * [optionPressed](#optionpressed)
 * [playErrorSound](#playerrorsound)
 * [readFromFile](#readfromfile)
 * [removeFilenameFromPath](#removefilenamefrompath)
 * [removeFromTable](#removefromtable)
 * [replace](#replace)
 * [rescale](#rescale)
 * [rightClick](#rightclick)
 * [rmdir](#rmdir)
 * [round](#round)
 * [safeFilename](#safefilename)
 * [shiftPressed](#shiftpressed)
 * [spairs](#spairs)
 * [split](#split)
 * [splitOnColumn](#splitoncolumn)
 * [startsWith](#startswith)
 * [stringMaxLength](#stringmaxlength)
 * [stringToHexString](#stringtohexstring)
 * [tableContains](#tablecontains)
 * [tableCount](#tablecount)
 * [tableFilter](#tablefilter)
 * [tableMatch](#tablematch)
 * [toRegionalNumber](#toregionalnumber)
 * [toRegionalNumberString](#toregionalnumberstring)
 * [trim](#trim)
 * [unescape](#unescape)
 * [upper](#upper)
 * [urlQueryStringDecode](#urlquerystringdecode)
 * [volumeFormat](#volumeformat)
 * [writeToFile](#writetofile)
* Methods - API calls which can only be made on an object returned by a constructor
 * [escapeTilda](#escapetilda)
 * [keyStroke](#keystroke)
 * [pressSystemKey](#presssystemkey)

## API Documentation

### Functions

#### [camelCase](#camelcase)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.camelCase(str) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Converts the supplied string to camelcase. |
| **Parameters**                                       | <ul><li>str - The string you want to manipulate</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [centre](#centre)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.centre(frame) -> hs.geometry point` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the centre point of a frame. |
| **Parameters**                                       | <ul><li>frame - an <code>hs.geometry</code> rect</li></ul> |
| **Returns**                                          | <ul><li>A hs.geometry point</li></ul> |

#### [cleanupButtonText](#cleanupbuttontext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.cleanupButtonText(value) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes the … symbol and multiple >'s from a string. |
| **Parameters**                                       | <ul><li>value - A string</li></ul> |
| **Returns**                                          | <ul><li>A cleaned string</li></ul> |

#### [contentsInsideBrackets](#contentsinsidebrackets)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.contentsInsideBrackets(value) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the contents of any text inside the first bracket set. |
| **Parameters**                                       | <ul><li>value - The string to process</li></ul> |
| **Returns**                                          | <ul><li>The contents as a string or <code>nil</code></li></ul> |

#### [convertSingleHexStringToDecimalString](#convertsinglehexstringtodecimalstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.convertSingleHexStringToDecimalString(hex) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Converts a single hex string (i.e. "3") to a binary string (i.e. "0011") |
| **Parameters**                                       | <ul><li>hex - A single string character</li></ul> |
| **Returns**                                          | <ul><li>A four character string</li></ul> |

#### [dirFiles](#dirfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.dirFiles(path) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets all the files in a directory |
| **Parameters**                                       | <ul><li>path - A path as string</li></ul> |
| **Returns**                                          | <ul><li>A table containing filenames as strings, or <code>nil</code> followed by the error message if an error occurs.</li></ul> |

#### [doesDirectoryExist](#doesdirectoryexist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doesDirectoryExist(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns whether or not a directory exists. |
| **Parameters**                                       | <ul><li>path - Path to the directory</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the directory exists otherwise <code>false</code></li></ul> |

#### [doesFileExist](#doesfileexist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doesFileExist(path) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns whether or not a file exists. |
| **Parameters**                                       | <ul><li>path - Path to the file</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the file exists otherwise <code>false</code></li></ul> |

#### [doubleLeftClick](#doubleleftclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.doubleLeftClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Performs a Left Mouse Double Click. |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [endsWith](#endswith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.endsWith(str, ending) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if `str` has the same ending as `ending`. |
| **Parameters**                                       | <ul><li>str       - String to analysis</li><li>ending    - End of string to compare against</li></ul> |
| **Returns**                                          | <ul><li>table</li></ul> |

#### [ensureDirectoryExists](#ensuredirectoryexists)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ensureDirectoryExists(rootPath, ...) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Ensures all steps on a provided path exist. If not, attempts to create them. |
| **Parameters**                                       | <ul><li><code>rootPath</code> - The root path</li><li><code>...</code>      - The list of path steps to create</li></ul> |
| **Returns**                                          | <ul><li>The full path, if it exists, or <code>nil</code> if unable to create the directory for some reason.</li></ul> |

#### [exactMatch](#exactmatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.exactMatch(value, pattern, plain) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Compares two strings to see if they're an exact match. |
| **Parameters**                                       | <ul><li>value - The first string</li><li>pattern - The second string, including any patterns</li><li>plain - Whether or not to ignore patterns. Defaults to <code>false</code>.</li><li>ignoreCase - Ignore the case of the value &amp; pattern.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if there's an exact match, otherwise <code>false</code>.</li></ul> |

#### [executeWithAdministratorPrivileges](#executewithadministratorprivileges)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.executeWithAdministratorPrivileges(input[, stopOnError]) -> boolean or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Executes a single or multiple shell commands with Administrator Privileges. |
| **Parameters**                                       | <ul><li>input - either a string or a table of strings of commands you want to execute</li><li>stopOnError - an optional variable that stops processing multiple commands when an individual commands returns an error</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, <code>false</code> if cancelled and a string if there's an error.</li></ul> |

#### [findCommonWordWithinTwoStrings](#findcommonwordwithintwostrings)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.findCommonWordWithinTwoStrings(a, b) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Finds a common word within two strings. |
| **Parameters**                                       | <ul><li>a - The first string</li><li>b - The second string</li></ul> |
| **Returns**                                          | <ul><li>The first common word that's found or <code>nil</code> if something goes wrong.</li></ul> |

#### [firstToUpper](#firsttoupper)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.firstToUpper(str) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Makes the first letter of a string uppercase. |
| **Parameters**                                       | <ul><li>str - The string you want to manipulate</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [getEmail](#getemail)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getEmail() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the current users Email, otherwise an empty string. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>String</li></ul> |

#### [getExternalDevices](#getexternaldevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getExternalDevices() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a string of USB & Thunderbolt Devices. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>String</li></ul> |

#### [getFileExtensionFromPath](#getfileextensionfrompath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getFileExtensionFromPath(input) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the file extension from a path. |
| **Parameters**                                       | <ul><li>input - The path</li></ul> |
| **Returns**                                          | <ul><li>A string of the file extension.</li></ul> |

#### [getFilenameFromPath](#getfilenamefrompath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getFilenameFromPath(input[, removeExtension]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the filename component of a path. |
| **Parameters**                                       | <ul><li>input - The path</li><li>removeExtension - (optional) set to <code>true</code> if the file extension should be removed</li></ul> |
| **Returns**                                          | <ul><li>A string of the filename.</li></ul> |

#### [getFullname](#getfullname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getFullname() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the current users Full Name, otherwise an empty string. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>String</li></ul> |

#### [getKeysSortedByValue](#getkeyssortedbyvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getKeysSortedByValue(tbl, sortFunction) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sorts table keys by a value |
| **Parameters**                                       | <ul><li>tbl - the table you want to sort</li><li>sortFunction - the function you want to use to sort the table</li></ul> |
| **Returns**                                          | <ul><li>A sorted table</li></ul> |

#### [getmacOSVersion](#getmacosversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getmacOSVersion() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the macOS Version in the format that Apple's Feedback Form expects. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The macOS version as a string or "" if unknown.</li></ul> |

#### [getModelName](#getmodelname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getModelName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns Model Name of Hardware. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>String</li></ul> |

#### [getRAMSize](#getramsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getRAMSize() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns RAM Size in a format Apple's Feedback form expects. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The RAM size as a string, or "" if unknown.</li></ul> |

#### [getScreenshotsAsBase64](#getscreenshotsasbase64)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getScreenshotsAsBase64() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Captures all available screens and saves them as base64 encodes in a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing base64 images of all available screens.</li></ul> |

#### [getThunderboltDevices](#getthunderboltdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getThunderboltDevices() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a string of Thunderbolt Devices. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>String</li></ul> |

#### [getUSBDevices](#getusbdevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getUSBDevices() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a string of USB Devices. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>String</li></ul> |

#### [getVRAMSize](#getvramsize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.getVRAMSize() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the VRAM size in format suitable for Apple's Final Cut Pro feedback form or "" if unknown. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>String</li></ul> |

#### [hexStringToString](#hexstringtostring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.hexStringToString(value) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Converts a hex string to a string. |
| **Parameters**                                       | <ul><li>value - The string to convert</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [iconFallback](#iconfallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.iconFallback(paths) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Excepts one or more paths to an icon, checks to see if they exist (in the order that they're given), and if none exist, returns the CommandPost icon path. |
| **Parameters**                                       | <ul><li>paths - One or more paths to an icon</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [incrementFilename](#incrementfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.incrementFilename(value) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Increments the filename. |
| **Parameters**                                       | <ul><li>value - A string</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [incrementFilenameInPath](#incrementfilenameinpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.incrementFilenameInPath(path) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Increments the filename as it appears in a path. |
| **Parameters**                                       | <ul><li>path - A path to a file.</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [isNumberString](#isnumberstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.isNumberString(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns whether or not value is a number string. |
| **Parameters**                                       | <ul><li>value - the string you want to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if value is a number string, otherwise <code>false</code>.</li></ul> |

#### [isOffScreen](#isoffscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.isOffScreen(rect) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Determines if the given rect is off screen or not. |
| **Parameters**                                       | <ul><li>rect - the rect you want to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if offscreen otherwise <code>false</code></li></ul> |

#### [leftClick](#leftclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.leftClick(point[, delay, clickNumber]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Performs a Left Mouse Click. |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li><li>clickNumber - The optional number of times you want to perform the click.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [lines](#lines)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.lines(string) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Splits a string containing multiple lines of text into a table. |
| **Parameters**                                       | <ul><li>string - the string you want to process</li></ul> |
| **Returns**                                          | <ul><li>A table or <code>nil</code> if the parameter is not a string.</li></ul> |

#### [lower](#lower)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.lower(str) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Converts the supplied string to lowercase. |
| **Parameters**                                       | <ul><li>str - The string you want to manipulate</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [macOSVersion](#macosversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.macOSVersion() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a the macOS Version as a single string. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the macOS version</li></ul> |

#### [mergeTable](#mergetable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.mergeTable(target, ...) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Merges multiple tables into a target table. |
| **Parameters**                                       | <ul><li>target   - The target table</li><li>...      - Any other tables you want to merge into target</li></ul> |
| **Returns**                                          | <ul><li>Table</li></ul> |

#### [ninjaDoubleClick](#ninjadoubleclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaDoubleClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Performs a mouse double click, but returns the mouse to the original position without the users knowledge. |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [ninjaMouseAction](#ninjamouseaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaMouseAction(point, fn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Moves the mouse to a point, performs a function, then returns the mouse to the original point. |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>fn - A function you want to perform</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [ninjaMouseClick](#ninjamouseclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaMouseClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Performs a mouse click, but returns the mouse to the original position without the users knowledge. |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [ninjaRightMouseClick](#ninjarightmouseclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.ninjaRightMouseClick(point[, delay]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Performs a right mouse click, but returns the mouse to the original position without the users knowledge. |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [numberToWord](#numbertoword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.numberToWord(number) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Converts a number to a string (i.e. 1 becomes "One"). |
| **Parameters**                                       | <ul><li>number - A whole number between 0 and 10</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [optionPressed](#optionpressed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.optionPressed() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Is the Option Key being pressed? |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the option key is being pressed, otherwise <code>false</code>.</li></ul> |

#### [playErrorSound](#playerrorsound)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.playErrorSound() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Plays the "Funk" error sound. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [readFromFile](#readfromfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.readFromFile(path) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Read data from file. |
| **Parameters**                                       | <ul><li>path - The path of where you want to load the file.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [removeFilenameFromPath](#removefilenamefrompath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.removeFilenameFromPath(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes the filename from a path. |
| **Parameters**                                       | <ul><li>string - The path</li></ul> |
| **Returns**                                          | <ul><li>A string of the path without the filename.</li></ul> |

#### [removeFromTable](#removefromtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.removeFromTable(table, element) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes a string from a table of strings |
| **Parameters**                                       | <ul><li>table - the table you want to check</li><li>element - the string you want to remove</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [replace](#replace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.replace(text, old, new) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | A find and replace feature that doesn't use patterns. |
| **Parameters**                                       | <ul><li>text - The string you want to process</li><li>old - The string you want to find</li><li>new - The new string you want to replace the old string with</li></ul> |
| **Returns**                                          | <ul><li>A new string</li></ul> |

#### [rescale](#rescale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.rescale(value, inMin, inMax, outMin, outMax) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Takes an input, rescales it, and provides a new output. |
| **Parameters**                                       | <ul><li>value - The value you want to process as a number</li><li>inMin - The minimum value of the input as a number</li><li>inMax - The maximum value of the input as a number</li><li>outMin - The minimum value of the output as a number</li><li>outMax - The maximum value of the output as a number</li></ul> |
| **Returns**                                          | <ul><li>The rescaled value as a number or <code>nil</code>.</li></ul> |

#### [rightClick](#rightclick)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.rightClick(point[, delay, clickNumber]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Performs a Right Mouse Click. |
| **Parameters**                                       | <ul><li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li><li>delay - The optional delay between multiple mouse clicks</li><li>clickNumber - The optional number of times you want to perform the click.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [rmdir](#rmdir)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.rmdir(path[, recursive]) -> true | nil, err` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Attempts to remove the directory at the specified path, optionally removing |
| **Parameters**                                       | <ul><li><code>path</code>        - The absolute path to remove</li><li><code>recursive</code>   - If <code>true</code>, the contents of the directory will be removed first.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>nil, err</code> if there was a problem.</li></ul> |

#### [round](#round)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.round(num, numDecimalPlaces) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Rounds a number to a set number of decimal places |
| **Parameters**                                       | <ul><li>num - The number you want to round</li><li>numDecimalPlaces - How many numbers of decimal places (defaults to 0)</li></ul> |
| **Returns**                                          | <ul><li>A rounded number</li></ul> |

#### [safeFilename](#safefilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.safeFilename(value[, defaultValue]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a Safe Filename. |
| **Parameters**                                       | <ul><li>value - a string you want to make safe</li><li>defaultValue - the optional default filename to use if the value is not valid</li></ul> |
| **Returns**                                          | <ul><li>A string of the safe filename</li></ul> |
| **Notes**                                            | <ul><li>Returns "filename" is both <code>value</code> and <code>defaultValue</code> are <code>nil</code>.</li></ul> |

#### [shiftPressed](#shiftpressed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.shiftPressed() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Is the Shift Key being pressed? |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the shift key is being pressed, otherwise <code>false</code>.</li></ul> |

#### [spairs](#spairs)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.spairs(t, order) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | A customised version of pairs, called `spairs` because it iterates over the table in a sorted order. |
| **Parameters**                                       | <ul><li>t     - The table to process</li><li>order - The function of how to sort the table.</li></ul> |
| **Returns**                                          | <ul><li>A iterator function.</li></ul> |
| **Notes**                                            | <ul><li>Author: <a href="https://stackoverflow.com/a/15706820">Michal Kottman</a></li></ul> |

#### [split](#split)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.split(str, pat) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Splits a string with a pattern. |
| **Parameters**                                       | <ul><li>str - The string to split</li><li>pat - The pattern</li></ul> |
| **Returns**                                          | <ul><li>Table</li></ul> |

#### [splitOnColumn](#splitoncolumn)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.splitOnColumn() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Splits a string on a column. |
| **Parameters**                                       | <ul><li>Input</li></ul> |
| **Returns**                                          | <ul><li>String</li></ul> |

#### [startsWith](#startswith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.startsWith(value, startValue) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if a string starts with a value. |
| **Parameters**                                       | <ul><li>value - The value to check</li><li>startValue - The value to look for</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if value starts with the startValue, otherwise <code>false</code></li></ul> |

#### [stringMaxLength](#stringmaxlength)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.stringMaxLength(string, maxLength[, optionalEnd]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Trims a string based on a maximum length. |
| **Parameters**                                       | <ul><li>maxLength - The length of the string as a number</li><li>optionalEnd - A string that is applied to the end of the input string if the input string is larger than the maximum length.</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [stringToHexString](#stringtohexstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.stringToHexString(value) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Converts a string to a hex string. |
| **Parameters**                                       | <ul><li>value - The string to convert</li></ul> |
| **Returns**                                          | <ul><li>A hex string</li></ul> |

#### [tableContains](#tablecontains)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.tableContains(table, element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Does a element exist in a table? |
| **Parameters**                                       | <ul><li>table - the table you want to check</li><li>element - the element you want to check for</li></ul> |
| **Returns**                                          | <ul><li>Boolean</li></ul> |

#### [tableCount](#tablecount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.tableCount(table) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns how many items are in a table. |
| **Parameters**                                       | <ul><li>table - The table you want to count.</li></ul> |
| **Returns**                                          | <ul><li>The number of items in the table.</li></ul> |
| **Notes**                                            | <ul><li>If something other than a table is supplied, this function will return 0.</li></ul> |

#### [tableFilter](#tablefilter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.tableFilter(t, matchFn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Efficiently filters out all elements from the table `t` which to not match the `matchFn`. |
| **Parameters**                                       | <ul><li>t          - The <code>table</code> to filter.</li><li>matchFn    - A function which will receive the table, the current index, and the target index.</li></ul> |
| **Returns**                                          | <ul><li>The same table, updated.</li></ul> |

#### [tableMatch](#tablematch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.tableMatch(t1, t2[, ignoreMetatable]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Compares two tables. |
| **Parameters**                                       | <ul><li>t1 - The first table.</li><li>t2 - The second table.</li><li>ignoreMetatable - A boolean that determines whether or not we should ignore the metatable.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if <code>t1</code> and <code>t2</code> are identical, otherwise <code>false</code>.</li></ul> |

#### [toRegionalNumber](#toregionalnumber)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.toRegionalNumber(value) -> number | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Takes a string and converts it into a number, with the correct |
| **Parameters**                                       | <ul><li>value - The value you want to process as a string.</li></ul> |
| **Returns**                                          | <ul><li>The value as a number or <code>nil</code>.</li></ul> |

#### [toRegionalNumberString](#toregionalnumberstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.toRegionalNumberString(value) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Takes a number and converts it into a string, with the correct |
| **Parameters**                                       | <ul><li>value - The value you want to process as a number.</li></ul> |
| **Returns**                                          | <ul><li>The value as a number or <code>nil</code>.</li></ul> |

#### [trim](#trim)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.trim(string) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Trims the whitespaces from a string |
| **Parameters**                                       | <ul><li>string - the string you want to trim</li></ul> |
| **Returns**                                          | <ul><li>A trimmed string</li></ul> |

#### [unescape](#unescape)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.unescape(str) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes any URL encoding in the provided string. |
| **Parameters**                                       | <ul><li>str - the string to decode</li></ul> |
| **Returns**                                          | <ul><li>A string with all "+" characters converted to spaces and all percent encoded sequences converted to their ASCII equivalents.</li></ul> |

#### [upper](#upper)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.upper(str) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Converts the supplied string to uppercase. |
| **Parameters**                                       | <ul><li>str - The string you want to manipulate</li></ul> |
| **Returns**                                          | <ul><li>A string</li></ul> |

#### [urlQueryStringDecode](#urlquerystringdecode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.urlQueryStringDecode() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Decodes a URL Query String |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Decoded URL Query String as string</li></ul> |

#### [volumeFormat](#volumeformat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.volumeFormat(path) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gives you the file system volume format of a path. |
| **Parameters**                                       | <ul><li>path - the path you want to check as a string</li></ul> |
| **Returns**                                          | <ul><li>The <code>NSURLVolumeLocalizedFormatDescriptionKey</code> as a string, otherwise <code>nil</code>.</li></ul> |

#### [writeToFile](#writetofile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.writeToFile(path, data) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Write data to a file at a given path. |
| **Parameters**                                       | <ul><li>path - The path to the file you want to write to.</li><li>data - The data to write to the file.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Methods

#### [escapeTilda](#escapetilda)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.escapeTilda(input) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Escapes a tilda. |
| **Parameters**                                       | <ul><li>input - The string you want to escape.</li></ul> |
| **Returns**                                          | <ul><li>A new string</li></ul> |

#### [keyStroke](#keystroke)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.keyStroke(modifiers, character, app) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Generates and emits a single keystroke event pair for the supplied keyboard |
| **Parameters**                                       | <ul><li>modifiers - A table containing the keyboard modifiers to apply ("fn", "ctrl", "alt", "cmd" or "shift")</li><li>character - A string containing a character to be emitted</li><li>app - The optional <code>hs.application</code> you want to target</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [pressSystemKey](#presssystemkey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.tools.pressSystemKey(key) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Virtually presses a system key. |
| **Parameters**                                       | <ul><li>key - The key to use.</li></ul> |
| **Returns**                                          | <ul><li>Supported key values are:</li><li>SOUND_UP</li><li>SOUND_DOWN</li><li>MUTE</li><li>BRIGHTNESS_UP</li><li>BRIGHTNESS_DOWN</li><li>CONTRAST_UP</li><li>CONTRAST_DOWN</li><li>POWER</li><li>LAUNCH_PANEL</li><li>VIDMIRROR</li><li>PLAY</li><li>EJECT</li><li>NEXT</li><li>PREVIOUS</li><li>FAST</li><li>REWIND</li><li>ILLUMINATION_UP</li><li>ILLUMINATION_DOWN</li><li>ILLUMINATION_TOGGLE</li><li>CAPS_LOCK</li><li>HELP</li><li>NUM_LOCK</li></ul> |

