# [docs](index.md) » hs.webview.datastore
---

Provides methods to list and purge the various types of data used by websites visited with `hs.webview`.

This module is only available under OS X 10.11 and later.

This module allows you to list and selectively purge the types of data stored locally for the websites visited with the `hs.webview` module.  It also adds support for non-persistent datastores to `hs.webview` (private browsing) and allows a non-persistent datastore to be shared among multiple instances of `hs.webview` objects.

The datastore for a webview contains various types of data including cookies, disk and memory caches, and persistent data such as WebSQL, IndexedDB databases, and local storage.  You can use methods in this module to selectively or completely purge the common datastore (used by all Hammerspoon `hs.webview` instances that do not use a non-persistent datastore).

## API Overview
* Functions - API calls offered directly by the extension
 * [websiteDataTypes](#websitedatatypes)
* Constructors - API calls which return an object, typically one that offers API methods
 * [default](#default)
 * [fromWebview](#fromwebview)
 * [newPrivate](#newprivate)
* Methods - API calls which can only be made on an object returned by a constructor
 * [fetchRecords](#fetchrecords)
 * [persistent](#persistent)
 * [removeRecordsAfter](#removerecordsafter)
 * [removeRecordsFor](#removerecordsfor)

## API Documentation

### Functions

#### [websiteDataTypes](#websitedatatypes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore.websiteDataTypes() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of the currently available data types within a datastore.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a list of strings where each string is a specific data type stored in a datastore.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">As of the writing of this module, the following data types are defined and returned by this function:</li><li markdown="1">  `WKWebsiteDataTypeDiskCache`                  - On-disk caches.</li><li markdown="1">  `WKWebsiteDataTypeOfflineWebApplicationCache` - HTML offline web application caches.</li><li markdown="1">  `WKWebsiteDataTypeMemoryCache`                - In-memory caches.</li><li markdown="1">  `WKWebsiteDataTypeLocalStorage`               - HTML local storage.</li><li markdown="1">  `WKWebsiteDataTypeCookies`                    - Cookies.</li><li markdown="1">  `WKWebsiteDataTypeSessionStorage`             - HTML session storage.</li><li markdown="1">  `WKWebsiteDataTypeIndexedDBDatabases`         - WebSQL databases.</li><li markdown="1">  `WKWebsiteDataTypeWebSQLDatabases`            - IndexedDB databases.</li></ul>                |

### Constructors

#### [default](#default)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore.default() -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns an object representing the default datastore for Hammerspoon `hs.webview` instances.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a datastoreObject</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">this is the datastore used unless otherwise specified when creating an `hs.webview` instance.</li></ul>                |

#### [fromWebview](#fromwebview)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore.fromWebview(webview) -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns an object representing the datastore for the specified `hs.webview` instance.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`webview` - an `hs.webview` instance (webviewObject)</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a datastoreObject</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">When running on a system with OS X 10.11 or later, this method will also be added to the metatable for `hs.webview` objects so that you can retrieve a webview's datastore with `hs.webview:datastore()`.</li></ul>                |

#### [newPrivate](#newprivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore.newPrivate() -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns an object representing a newly created non-persistent (private) datastore for use with a Hammerspoon `hs.webview` instance.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a datastoreObject</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The datastore represented by this object will be initially empty.  You can use this function to create a non-persistent datastore that you wish to share among multiple `hs.webview` instances.  Once a datastore is created, you assign it to a `hs.webview` instance by including the `datastore` key in the `hs.webvew.new` constructor's preferences table and setting it equal to this key.  All webview instances created with this datastore object will share web caches, cookies, etc. but will still be isolated from the default datastore and it will be purged from memory when the webviews are deleted, or Hammerspoon is restarted.</li></ul>                |

### Methods

#### [fetchRecords](#fetchrecords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore:fetchRecords([dataTypes], callback) -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Generates a list of the datastore records of the specified type, and invokes the callback function with the list.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`dataTypes` - an optional string or table specifying the data types to fetch from the datastore.  If this parameter is not specified, it defaults to the list returned by [hs.webview.datastore.websiteDataTypes](#websiteDataTypes).</li><li markdown="1">`callback`  - a function which accepts as it's argument an array-table containing tables with the following key-value pairs:</li><li markdown="1">  `displayName` - a string containing the site's display name.  Typically, the display name is the domain name with suffix taken from the resource’s security origin (website name).</li><li markdown="1">  `dataTypes`   - a table containing strings representing the types of data stored for the website specified by `displayName`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the datastore object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">only those sites with one or more of the specified data types are returned</li><li markdown="1">for the sites returned, only those data types that were present in the query will be included in the list, even if the site has data of another type in the datastore.</li></ul>                |

#### [persistent](#persistent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore:persistent() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the datastore is persistent.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a boolean value indicating whether or not the datastore is persistent (true) or private (false)</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Note that this value is the inverse of `hs.webview:privateBrowsing()`, since private browsing uses a non-persistent datastore.</li></ul>                |

#### [removeRecordsAfter](#removerecordsafter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore:removeRecordsAfter(date, dataTypes, [callback]) -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Removes the specified types of data from the datastore if the data was added or changed since the given date.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`date`         - an integer representing seconds since `1970-01-01 00:00:00 +0000` (e.g. `os.time()`), or a string containing a date in RFC3339 format (`YYYY-MM-DD[T]HH:MM:SS[Z]`).</li><li markdown="1">`dataTypes`    - a string or array of strings specifying the types of data to remove from the datastore for the specified sites.</li><li markdown="1">`callback`     - an optional function, which should expect no arguments, that will be called when the specified items have been removed from the datastore.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the datastore object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Yes, you read the description correctly -- removes data *newer* then the date specified.  I've not yet found a way to remove data *older* then the date specified (to expire old data, for example) but updates or suggestions are welcome in the Hammerspoon Google group or Github web site.</li></ul>                |

#### [removeRecordsFor](#removerecordsfor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore:removeRecordsFor(displayNames, dataTypes, [callback]) -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Remove data from the datastore of the specified type(s) for the specified site(s).                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`displayNames` - a string or array of strings specifying the display names (sites) to remove records for.</li><li markdown="1">`dataTypes`    - a string or array of strings specifying the types of data to remove from the datastore for the specified sites.</li><li markdown="1">`callback`     - an optional function, which should expect no arguments, that will be called when the specified items have been removed from the datastore.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the datastore object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">to specify that all data types that qualify should be removed, specify the function  [hs.webview.datastore.websiteDataTypes()](#websiteDataTypes). as the second argument.</li></ul>                |

