# [docs](index.md) » hs.urlevent
---

Allows CommandPost to respond to URLs
CommandPost is configured to react to URLs that start with `commandpost://` when they are opened by OS X.
This extension allows you to register callbacks for these URL events and their parameters, offering a flexible way to receive events from other applications.

You can also choose to make CommandPost the default for `http://` and `https://` URLs, which lets you route the URLs in your Lua code

Given a URL such as `commandpost://someEventToHandle?someParam=things&otherParam=stuff`, in the literal, RFC1808 sense of the URL, `someEventToHandle` is the hostname (or net_loc) of the URL, but given that these are not network resources, we consider `someEventToHandle` to be the name of the event. No path should be specified in the URL - it should consist purely of a hostname and, optionally, query parameters.

See also `hs.ipc` for a command line IPC mechanism that is likely more appropriate for shell scripts or command line use. Unlike `hs.ipc`, `hs.urlevent` is not able to return any data to its caller.

NOTE: If CommandPost is not running when a `commandpost://` URL is opened, CommandPost will be launched, but it will not react to the URL event. Nor will it react to any events until this extension is loaded and event callbacks have been bound.
NOTE: Any event which is received, for which no callback has been bound, will be logged to the CommandPost Console
NOTE: When you trigger a URL from another application, it is usually best to have the URL open in the background, if that option is available. Otherwise, OS X will activate CommandPost (i.e. give it focus), which makes URL events difficult to use for things like window management.

## API Overview
* Variables - Configurable values
 * [httpCallback](#httpcallback)
* Functions - API calls offered directly by the extension
 * [bind](#bind)
 * [getAllHandlersForScheme](#getallhandlersforscheme)
 * [getDefaultHandler](#getdefaulthandler)
 * [openURL](#openurl)
 * [openURLWithBundle](#openurlwithbundle)
 * [setDefaultHandler](#setdefaulthandler)
 * [setRestoreHandler](#setrestorehandler)

## API Documentation

### Variables

#### [httpCallback](#httpcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.urlevent.httpCallback` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A function that should handle http:// and https:// URL events |
| **Notes**                                            | <ul><li>The function should handle four arguments:</li><li>scheme - A string containing the URL scheme (i.e. "http")</li><li>host - A string containing the host requested (e.g. "www.commandpost.org")</li><li>params - A table containing the key/value pairs of all the URL parameters</li><li>fullURL - A string containing the full, original URL</li></ul> |

### Functions

#### [bind](#bind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.urlevent.bind(eventName, callback)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Registers a callback for a commandpost:// URL event |
| **Parameters**                                       | <ul><li>eventName - A string containing the name of an event</li><li>callback - A function that will be called when the specified event is received, or nil to remove an existing callback</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>The callback function should accept two parameters:</li><li>eventName - A string containing the name of the event</li><li>params - A table containing key/value string pairs containing any URL parameters that were specified in the URL</li><li>Given the URL <code>commandpost://doThingA?value=1</code> The event name is <code>doThingA</code> and the callback's <code>params</code> argument will be a table containing <code>{["value"] = "1"}</code></li></ul> |

#### [getAllHandlersForScheme](#getallhandlersforscheme)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.urlevent.getAllHandlersForScheme(scheme) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets all of the application bundle identifiers of applications able to handle a URL scheme |
| **Parameters**                                       | <ul><li>scheme - A string containing a URL scheme (e.g. 'http')</li></ul> |
| **Returns**                                          | <ul><li>A table containing the bundle identifiers of all applications that can handle the scheme</li></ul> |

#### [getDefaultHandler](#getdefaulthandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.urlevent.getDefaultHandler(scheme) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the application bundle identifier of the application currently registered to handle a URL scheme |
| **Parameters**                                       | <ul><li>scheme - A string containing a URL scheme (e.g. 'http')</li></ul> |
| **Returns**                                          | <ul><li>A string containing the bundle identifier of the current default application</li></ul> |

#### [openURL](#openurl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.urlevent.openURL(url)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Opens a URL with the default application |
| **Parameters**                                       | <ul><li>url - A string containing a URL, which must contain a scheme and '://'</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the URL was opened successfully, otherwise false</li></ul> |

#### [openURLWithBundle](#openurlwithbundle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.urlevent.openURLWithBundle(url, bundleID) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Opens a URL with a specified application |
| **Parameters**                                       | <ul><li>url - A string containing a URL</li><li>bundleID - A string containing an application bundle identifier (e.g. "com.apple.Safari")</li></ul> |
| **Returns**                                          | <ul><li>True if the application was launched successfully, otherwise false</li></ul> |

#### [setDefaultHandler](#setdefaulthandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.urlevent.setDefaultHandler(scheme[, bundleID])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets the default system handler for URLs of a given scheme |
| **Parameters**                                       | <ul><li>scheme - A string containing the URL scheme to change. This must be 'http' or 'https' (although entering either will change the handler for both)</li><li>bundleID - An optional string containing an application bundle identifier for the application to set as the default handler. Defaults to <code>org.latenitefilms.CommandPost</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>Changing the default handler for http/https URLs will display a system prompt asking the user to confirm the change</li></ul> |

#### [setRestoreHandler](#setrestorehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.urlevent.setRestoreHandler(scheme, bundleID)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stores a URL handler that will be restored when CommandPost or reloads its config |
| **Parameters**                                       | <ul><li>scheme - A string containing the URL scheme to change. This must be 'http' (although both http:// and https:// URLs will be affected)</li><li>bundleID - A string containing an application bundle identifier (e.g. 'com.apple.Safari') for the application to set as the default handler when CommandPost exits or reloads its config</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>You don't have to call this function if you want CommandPost to permanently be your default handler. Only use this if you want the handler to be automatically reverted to something else when CommandPost exits/reloads.</li></ul> |

