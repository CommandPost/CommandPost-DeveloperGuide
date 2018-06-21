# [docs](index.md) » hs.osascript
---

Execute Open Scripting Architecture (OSA) code - AppleScript and JavaScript


## API Overview
* Functions - API calls offered directly by the extension
 * [_osascript](#_osascript)
 * [applescript](#applescript)
 * [applescriptFromFile](#applescriptfromfile)
 * [javascript](#javascript)
 * [javascriptFromFile](#javascriptfromfile)

## API Documentation

### Functions

#### [_osascript](#_osascript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.osascript._osascript(source, language) -> bool, object, descriptor` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Runs osascript code                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">source - Some osascript code to execute</li><li markdown="1">language - A string containing the OSA language, either 'AppleScript' or 'JavaScript'. Defaults to AppleScript if invalid language</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean value indicating whether the code succeeded or not</li><li markdown="1">An object containing the parsed output that can be any type, or nil if unsuccessful</li><li markdown="1">A string containing the raw output of the code and/or its errors</li></ul>          |

#### [applescript](#applescript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.osascript.applescript(source) -> bool, object, descriptor` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Runs AppleScript code                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">source - A string containing some AppleScript code to execute</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean value indicating whether the code succeeded or not</li><li markdown="1">An object containing the parsed output that can be any type, or nil if unsuccessful</li><li markdown="1">If the code succeeded, the raw output of the code string. If the code failed, a table containing an error dictionary</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Use hs.osascript._osascript(source, "AppleScript") if you always want the result as a string, even when a failure occurs</li></ul>                |

#### [applescriptFromFile](#applescriptfromfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.osascript.applescriptFromFile(fileName) -> bool, object, descriptor` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Runs AppleScript code from a source file.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">fileName - A string containing the file name of an AppleScript file to execute.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean value indicating whether the code succeeded or not</li><li markdown="1">An object containing the parsed output that can be any type, or nil if unsuccessful</li><li markdown="1">If the code succeeded, the raw output of the code string. If the code failed, a table containing an error dictionary</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This function uses hs.osascript.applescript for execution.</li><li markdown="1">Use hs.osascript._osascript(source, "AppleScript") if you always want the result as a string, even when a failure occurs. However, this function can only take a string, and not a file name.</li></ul>                |

#### [javascript](#javascript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.osascript.javascript(source) -> bool, object, descriptor` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Runs JavaScript code                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">source - A string containing some JavaScript code to execute</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean value indicating whether the code succeeded or not</li><li markdown="1">An object containing the parsed output that can be any type, or nil if unsuccessful</li><li markdown="1">If the code succeeded, the raw output of the code string. If the code failed, a table containing an error dictionary</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Use hs.osascript._osascript(source, "JavaScript") if you always want the result as a string, even when a failure occurs</li></ul>                |

#### [javascriptFromFile](#javascriptfromfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.osascript.javascriptFromFile(fileName) -> bool, object, descriptor` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Runs JavaScript code from a source file.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">fileName - A string containing the file name of an JavaScript file to execute.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean value indicating whether the code succeeded or not</li><li markdown="1">An object containing the parsed output that can be any type, or nil if unsuccessful</li><li markdown="1">If the code succeeded, the raw output of the code string. If the code failed, a table containing an error dictionary</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This function uses hs.osascript.javascript for execution.</li><li markdown="1">Use hs.osascript._osascript(source, "JavaScript") if you always want the result as a string, even when a failure occurs. However, this function can only take a string, and not a file name.</li></ul>                |

