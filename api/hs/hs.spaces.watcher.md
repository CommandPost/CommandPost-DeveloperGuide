# [docs](index.md) » hs.spaces.watcher
---

Watches for the current Space being changed
NOTE: This extension determines the number of a Space, using OS X APIs that have been deprecated since 10.8 and will likely be removed in a future release. You should not depend on Space numbers being around forever!

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spaces.watcher.new(handler) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new watcher for Space change events                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">handler - A function to be called when the active Space changes. It should accept one argument, which will be the number of the new Space (or -1 if the number cannot be determined)</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `hs.spaces.watcher` object</li></ul>          |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spaces.watcher:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the Spaces watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The watcher object</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spaces.watcher:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the Spaces watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The watcher object</li></ul>          |

