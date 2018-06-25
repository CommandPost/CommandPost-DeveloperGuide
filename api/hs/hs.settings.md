# [docs](index.md) » hs.settings
---

Serialize simple Lua variables across Hammerspoon launches
Settings must have a string key and must be made up of serializable Lua objects (string, number, boolean, nil, tables of such, etc.)

This module is based partially on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).


## API Overview
* Constants - Useful values which cannot be changed
 * [bundleID](#bundleid)
 * [dateFormat](#dateformat)
* Functions - API calls offered directly by the extension
 * [clear](#clear)
 * [get](#get)
 * [getKeys](#getkeys)
 * [set](#set)
 * [setData](#setdata)
 * [setDate](#setdate)
 * [watchKey](#watchkey)

## API Documentation

### Constants

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.settings.bundleID` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A string representing the ID of the bundle Hammerspoon's settings are stored in . You can use this with the command line tool `defaults` or other tools which allow access to the `User Defaults` of applications, to access these outside of Hammerspoon                                                                                         |

#### [dateFormat](#dateformat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.settings.dateFormat` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A string representing the expected format of date and time when presenting the date and time as a string to `hs.setDate()`.  e.g. `os.date(hs.settings.dateFormat)`                                                                                         |

### Functions

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.settings.clear(key) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Deletes a setting                                                                                         |
| **Parameters**                                       | <ul><br /><li>key - A string containing the name of a setting</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A boolean, true if the setting was deleted, otherwise false</li><br /></ul>                                           |

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.settings.get(key) -> string or boolean or number or nil or table or binary data` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Loads a setting                                                                                         |
| **Parameters**                                       | <ul><br /><li>key - A string containing the name of the setting</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The value of the setting</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This function can load all of the datatypes supported by <code>hs.settings.set()</code>, <code>hs.settings.setData()</code> and <code>hs.settings.setDate()</code></li><br /></ul>                                             |

#### [getKeys](#getkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.settings.getKeys() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets all of the previously stored setting names                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing all of the settings keys in Hammerspoon's settings</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Use <code>ipairs(hs.settings.getKeys())</code> to iterate over all available settings * Use <code>hs.settings.getKeys()["someKey"]</code> to test for the existance of a particular key</li><br /></ul>                                             |

#### [set](#set)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.settings.set(key[, val])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves a setting with common datatypes                                                                                         |
| **Parameters**                                       | <ul><br /><li>key - A string containing the name of the setting * val - An optional value for the setting. Valid datatypes are:   * string   * number   * boolean   * nil   * table (which may contain any of the same valid datatypes) * if no value is provided, it is assumed to be nil</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This function cannot set dates or raw data types, see <code>hs.settings.setDate()</code> and <code>hs.settings.setData()</code> * Assigning a nil value is equivalent to clearing the value with <code>hs.settings.clear</code></li><br /></ul>                                             |

#### [setData](#setdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.settings.setData(key, val)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves a setting with raw binary data                                                                                         |
| **Parameters**                                       | <ul><br /><li>key - A string containing the name of the setting * val - Some raw binary data</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [setDate](#setdate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.settings.setDate(key, val)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves a setting with a date                                                                                         |
| **Parameters**                                       | <ul><br /><li>key - A string containing the name of the setting * val - A number representing seconds since <code>1970-01-01 00:00:00 +0000</code> (e.g. <code>os.time()</code>), or a string containing a date in RFC3339 format (<code>YYYY-MM-DD[T]HH:MM:SS[Z]</code>)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>See <code>hs.settings.dateFormat</code> for a convenient representation of the RFC3339 format, to use with other time/date related functions</li><br /></ul>                                             |

#### [watchKey](#watchkey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.settings.watchKey(identifier, key, [fn | nil]) -> identifier | current value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get or set a watcher to invoke a callback when the specified settings key changes                                                                                         |
| **Parameters**                                       | <ul><br /><li>identifier - a required string used as an identifier for this callback * key        - the settings key to watch for changes to * fn         - the callback function to be invoked when the specified key changes.  If this is an explicit nil, removes the existing callback.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>if a callback is set or removed, returns the identifier; otherwise returns the current callback function or nil if no callback function is currently defined.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>the identifier is required so that multiple callbacks for the same key can be registered by separate modules; it's value doesn't affect what is being watched but does need to be unique between multiple watchers of the same key.</li><br /></ul>                                             |

