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
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a list of strings where each string is a specific data type stored in a datastore.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>As of the writing of this module, the following data types are defined and returned by this function:   * <code>WKWebsiteDataTypeDiskCache</code>                  - On-disk caches.   * <code>WKWebsiteDataTypeOfflineWebApplicationCache</code> - HTML offline web application caches.   * <code>WKWebsiteDataTypeMemoryCache</code>                - In-memory caches.   * <code>WKWebsiteDataTypeLocalStorage</code>               - HTML local storage.   * <code>WKWebsiteDataTypeCookies</code>                    - Cookies.   * <code>WKWebsiteDataTypeSessionStorage</code>             - HTML session storage.   * <code>WKWebsiteDataTypeIndexedDBDatabases</code>         - WebSQL databases.   * <code>WKWebsiteDataTypeWebSQLDatabases</code>            - IndexedDB databases.</li><br /></ul>                                             |

### Constructors

#### [default](#default)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore.default() -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns an object representing the default datastore for Hammerspoon `hs.webview` instances.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a datastoreObject</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>this is the datastore used unless otherwise specified when creating an <code>hs.webview</code> instance.</li><br /></ul>                                             |

#### [fromWebview](#fromwebview)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore.fromWebview(webview) -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns an object representing the datastore for the specified `hs.webview` instance.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>webview</code> - an <code>hs.webview</code> instance (webviewObject)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a datastoreObject</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>When running on a system with OS X 10.11 or later, this method will also be added to the metatable for <code>hs.webview</code> objects so that you can retrieve a webview's datastore with <code>hs.webview:datastore()</code>.</li><br /></ul>                                             |

#### [newPrivate](#newprivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore.newPrivate() -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns an object representing a newly created non-persistent (private) datastore for use with a Hammerspoon `hs.webview` instance.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a datastoreObject</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The datastore represented by this object will be initially empty.  You can use this function to create a non-persistent datastore that you wish to share among multiple <code>hs.webview</code> instances.  Once a datastore is created, you assign it to a <code>hs.webview</code> instance by including the <code>datastore</code> key in the <code>hs.webvew.new</code> constructor's preferences table and setting it equal to this key.  All webview instances created with this datastore object will share web caches, cookies, etc. but will still be isolated from the default datastore and it will be purged from memory when the webviews are deleted, or Hammerspoon is restarted.</li><br /></ul>                                             |

### Methods

#### [fetchRecords](#fetchrecords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore:fetchRecords([dataTypes], callback) -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Generates a list of the datastore records of the specified type, and invokes the callback function with the list.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>dataTypes</code> - an optional string or table specifying the data types to fetch from the datastore.  If this parameter is not specified, it defaults to the list returned by <a href="#websiteDataTypes">hs.webview.datastore.websiteDataTypes</a>. * <code>callback</code>  - a function which accepts as it's argument an array-table containing tables with the following key-value pairs:   * <code>displayName</code> - a string containing the site's display name.  Typically, the display name is the domain name with suffix taken from the resource’s security origin (website name).   * <code>dataTypes</code>   - a table containing strings representing the types of data stored for the website specified by <code>displayName</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the datastore object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>only those sites with one or more of the specified data types are returned * for the sites returned, only those data types that were present in the query will be included in the list, even if the site has data of another type in the datastore.</li><br /></ul>                                             |

#### [persistent](#persistent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore:persistent() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the datastore is persistent.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a boolean value indicating whether or not the datastore is persistent (true) or private (false)</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Note that this value is the inverse of <code>hs.webview:privateBrowsing()</code>, since private browsing uses a non-persistent datastore.</li><br /></ul>                                             |

#### [removeRecordsAfter](#removerecordsafter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore:removeRecordsAfter(date, dataTypes, [callback]) -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Removes the specified types of data from the datastore if the data was added or changed since the given date.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>date</code>         - an integer representing seconds since <code>1970-01-01 00:00:00 +0000</code> (e.g. <code>os.time()</code>), or a string containing a date in RFC3339 format (<code>YYYY-MM-DD[T]HH:MM:SS[Z]</code>). * <code>dataTypes</code>    - a string or array of strings specifying the types of data to remove from the datastore for the specified sites. * <code>callback</code>     - an optional function, which should expect no arguments, that will be called when the specified items have been removed from the datastore.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the datastore object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Yes, you read the description correctly -- removes data <em>newer</em> then the date specified.  I've not yet found a way to remove data <em>older</em> then the date specified (to expire old data, for example) but updates or suggestions are welcome in the Hammerspoon Google group or Github web site.</li><br /></ul>                                             |

#### [removeRecordsFor](#removerecordsfor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.datastore:removeRecordsFor(displayNames, dataTypes, [callback]) -> datastoreObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Remove data from the datastore of the specified type(s) for the specified site(s).                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>displayNames</code> - a string or array of strings specifying the display names (sites) to remove records for. * <code>dataTypes</code>    - a string or array of strings specifying the types of data to remove from the datastore for the specified sites. * <code>callback</code>     - an optional function, which should expect no arguments, that will be called when the specified items have been removed from the datastore.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the datastore object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>to specify that all data types that qualify should be removed, specify the function  <a href="#websiteDataTypes">hs.webview.datastore.websiteDataTypes()</a>. as the second argument.</li><br /></ul>                                             |

