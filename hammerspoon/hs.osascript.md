# [docs](index.md) » hs.osascript
---

Execute Open Scripting Architecture (OSA) code - AppleScript and JavaScript


## API Overview
* Functions - API calls offered directly by the extension
* [_osascript](#_osascript)
* [applescript](#applescript)
* [javascript](#javascript)

## API Documentation

### Functions

#### [_osascript](#_osascript)
| Signature   | hs.osascript._osascript(source, language) -> bool, object, descriptor  |
| Type        | Function |
| Description | Runs osascript code |
| Parameters |  * source - Some osascript code to execute * language - A string containing the OSA language, either 'AppleScript' or 'JavaScript'. Defaults to AppleScript if invalid language | | Returns |  * A boolean value indicating whether the code succeeded or not * An object containing the parsed output that can be any type, or nil if unsuccessful * A string containing the raw output of the code and/or its errors | 
#### [applescript](#applescript)
| Signature   | hs.osascript.applescript(source) -> bool, object, descriptor  |
| Type        | Function |
| Description | Runs AppleScript code |
| Parameters |  * source - A string containing some AppleScript code to execute | | Returns |  * A boolean value indicating whether the code succeeded or not * An object containing the parsed output that can be any type, or nil if unsuccessful * If the code succeeded, the raw output of the code string. If the code failed, a table containing an error dictionary | | Notes |  * Use hs.osascript._osascript(source, "AppleScript") if you always want the result as a string, even when a failure occurs | 
#### [javascript](#javascript)
| Signature   | hs.osascript.javascript(source) -> bool, object, descriptor  |
| Type        | Function |
| Description | Runs JavaScript code |
| Parameters |  * source - A string containing some JavaScript code to execute | | Returns |  * A boolean value indicating whether the code succeeded or not * An object containing the parsed output that can be any type, or nil if unsuccessful * If the code succeeded, the raw output of the code string. If the code failed, a table containing an error dictionary | | Notes |  * Use hs.osascript._osascript(source, "JavaScript") if you always want the result as a string, even when a failure occurs | 