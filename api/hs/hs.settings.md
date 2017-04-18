# [docs](index.md) » hs.settings
---

Serialize simple Lua variables across Hammerspoon launches
Settings must have a string key and must be made up of serializable Lua objects (string, number, boolean, nil, tables of such, etc.)

This module is based partially on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).


## API Overview
* Constants - Useful values which cannot be changed
 * [bundleID](#bundleID)
 * [dateFormat](#dateFormat)
* Functions - API calls offered directly by the extension
 * [clear](#clear)
 * [get](#get)
 * [getKeys](#getKeys)
 * [set](#set)
 * [setData](#setData)
 * [setDate](#setDate)

## API Documentation

### Constants

#### [bundleID](#bundleID)
| **Signature**                               | `hs.settings.bundleID`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Constant                                                                     |
| **Description**                             | A string representing the ID of the bundle Hammerspoon's settings are stored in . You can use this with the command line tool `defaults` or other tools which allow access to the `User Defaults` of applications, to access these outside of Hammerspoon                                                                     |

#### [dateFormat](#dateFormat)
| **Signature**                               | `hs.settings.dateFormat`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Constant                                                                     |
| **Description**                             | A string representing the expected format of date and time when presenting the date and time as a string to `hs.setDate()`.  e.g. `os.date(hs.settings.dateFormat)`                                                                     |

### Functions

#### [clear](#clear)
| **Signature**                               | `hs.settings.clear(key) -> bool`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Deletes a setting                                                                     |
| **Parameters**                              | <ul><li>key - A string containing the name of a setting</li></ul> |
| **Returns**                                 | <ul><li>A boolean, true if the setting was deleted, otherwise false</li></ul>          |

#### [get](#get)
| **Signature**                               | `hs.settings.get(key) -> string or boolean or number or nil or table or binary data`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Loads a setting                                                                     |
| **Parameters**                              | <ul><li>key - A string containing the name of the setting</li></ul> |
| **Returns**                                 | <ul><li>The value of the setting</li></ul>          |
| **Notes**                                   | <ul><li>This function can load all of the datatypes supported by `hs.settings.set()`, `hs.settings.setData()` and `hs.settings.setDate()`</li></ul>                |

#### [getKeys](#getKeys)
| **Signature**                               | `hs.settings.getKeys() -> table`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets all of the previously stored setting names                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing all of the settings keys in Hammerspoon's settings</li></ul>          |
| **Notes**                                   | <ul><li>Use `ipairs(hs.settings.getKeys())` to iterate over all available settings</li><li>Use `hs.settings.getKeys()["someKey"]` to test for the existance of a particular key</li></ul>                |

#### [set](#set)
| **Signature**                               | `hs.settings.set(key[, val])`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Saves a setting with common datatypes                                                                     |
| **Parameters**                              | <ul><li>key - A string containing the name of the setting</li><li>val - An optional value for the setting. Valid datatypes are:</li><li>  string</li><li>  number</li><li>  boolean</li><li>  nil</li><li>  table (which may contain any of the same valid datatypes)</li><li>if no value is provided, it is assumed to be nil</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>This function cannot set dates or raw data types, see `hs.settings.setDate()` and `hs.settings.setData()`</li><li>Assigning a nil value is equivalent to clearing the value with `hs.settings.clear`</li></ul>                |

#### [setData](#setData)
| **Signature**                               | `hs.settings.setData(key, val)`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Saves a setting with raw binary data                                                                     |
| **Parameters**                              | <ul><li>key - A string containing the name of the setting</li><li>val - Some raw binary data</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

#### [setDate](#setDate)
| **Signature**                               | `hs.settings.setDate(key, val)`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Saves a setting with a date                                                                     |
| **Parameters**                              | <ul><li>key - A string containing the name of the setting</li><li>val - A number representing seconds since `1970-01-01 00:00:00 +0000` (e.g. `os.time()`), or a string containing a date in RFC3339 format (`YYYY-MM-DD[T]HH:MM:SS[Z]`)</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>See `hs.settings.dateFormat` for a convenient representation of the RFC3339 format, to use with other time/date related functions</li></ul>                |

