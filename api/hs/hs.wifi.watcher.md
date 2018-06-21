# [docs](index.md) » hs.wifi.watcher
---

Watch for changes to the associated wifi network

## API Overview
* Constants - Useful values which cannot be changed
 * [eventTypes](#eventtypes)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [start](#start)
 * [stop](#stop)
 * [watchingFor](#watchingfor)

## API Documentation

### Constants

#### [eventTypes](#eventtypes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.watcher.eventTypes[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the possible event types that this watcher can monitor for.                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.watcher.new(fn) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new watcher for WiFi network events                                                                                         |
| **Parameters**                                       |  * fn - A function that will be called when a WiFi event that is being monitored occurs. The function should expect 2 or 4 arguments as described in the notes below.                                       |
| **Returns**                                          |  * A `hs.wifi.watcher` object                                                |
| **Notes**                                            |  * For backwards compatibility, only "SSIDChange" is watched for by default, so existing code can continue to ignore the callback function arguments unless you add or change events with the [hs.wifi.watcher:watchingFor](#watchingFor).                                                      |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.watcher:start() -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the SSID watcher                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `hs.wifi.watcher` object                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.watcher:stop() -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the SSID watcher                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `hs.wifi.watcher` object                                                |

#### [watchingFor](#watchingfor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.wifi.watcher:watchingFor([messages]) -> watcher | current-value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the specific types of wifi events to generate a callback for with this watcher.                                                                                         |
| **Parameters**                                       |  * `messages` - an optional table of or list of strings specifying the types of events this watcher should invoke a callback for.  You can specify multiple types of events to watch for. Defaults to `{ "SSIDChange" }`.                                       |
| **Returns**                                          |  * if a value is provided, returns the watcher object; otherwise returns the current values as a table of strings.                                                |
| **Notes**                                            |  * the possible values for this method are described in [hs.wifi.watcher.eventTypes](#eventTypes). * the special string "all" specifies that all event types should be watched for.                                                      |

