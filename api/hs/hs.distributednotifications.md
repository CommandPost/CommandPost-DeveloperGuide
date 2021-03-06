# [docs](index.md) » hs.distributednotifications
---

Interact with NSDistributedNotificationCenter
There are many notifications posted by parts of OS X, and third party apps, which may be interesting to react to using this module.

You can discover the notifications that are being posted on your system with some code like this:
```
foo = hs.distributednotifications.new(function(name, object, userInfo) print(string.format("name: %s\nobject: %s\nuserInfo: %s\n", name, object, hs.inspect(userInfo))) end)
foo:start()
```

Note that distributed notifications are expensive - they involve lots of IPC. Also note that they are not guaranteed to be delivered, particularly if the system is very busy.

## API Overview
* Functions - API calls offered directly by the extension
 * [post](#post)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Functions

#### [post](#post)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.distributednotifications.post(name[, sender[, userInfo]])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends a distributed notification |
| **Parameters**                                       | <ul><li>name - A string containing the name of the notification</li><li>sender - An optional string containing the name of the sender of the notification (in the form <code>com.domain.application.foo</code>). Defaults to nil.</li><li>userInfo - An optional table containing additional information to post with the notification. Defaults to nil.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.distributednotifications.new(callback[, name[, object]]) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new NSDistributedNotificationCenter watcher |
| **Parameters**                                       | <ul><li>callback - A function to be called when a matching notification arrives. The function should accept one argument:</li><li>notificationName - A string containing the name of the notification</li><li>name - An optional string containing the name of notifications to watch for. A value of <code>nil</code> will cause all notifications to be watched on macOS versions earlier than Catalina. Defaults to <code>nil</code>.</li><li>object - An optional string containing the name of sending objects to watch for. A value of <code>nil</code> will cause all sending objects to be watched. Defaults to <code>nil</code>.</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.distributednotifications</code> object</li></ul> |
| **Notes**                                            | <ul><li>On Catalina and above, it is no longer possible to observe all notifications - the <code>name</code> parameter is effectively now required. See https://mjtsai.com/blog/2019/10/04/nsdistributednotificationcenter-no-longer-supports-nil-names</li></ul> |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.distributednotifications:start() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Starts a NSDistributedNotificationCenter watcher |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.distributednotifications</code> object</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.distributednotifications:stop() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops a NSDistributedNotificationCenter watcher |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.distributednotifications</code> object</li></ul> |

