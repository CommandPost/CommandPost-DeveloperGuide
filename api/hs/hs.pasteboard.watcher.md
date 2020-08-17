# [docs](index.md) » hs.pasteboard.watcher
---

Watch for Pasteboard Changes.
macOS doesn't offer any API for getting Pasteboard notifications, so this extension uses polling to check for Pasteboard changes at a chosen interval (defaults to 0.25).

## API Overview
* Functions - API calls offered directly by the extension
 * [interval](#interval)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [running](#running)
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Functions

#### [interval](#interval)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pasteboard.watcher.interval([value]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets or sets the polling interval (i.e. the frequency the pasteboard watcher checks the pasteboard). |
| **Parameters**                                       | <ul><li>value - an optional number to set the polling interval to.</li></ul> |
| **Returns**                                          | <ul><li>The polling interval as a number.</li></ul> |
| **Notes**                                            | <ul><li>This only affects new watchers, not existing/running ones.</li><li>The default value is 0.25.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pasteboard.watcher.new(callbackFn[, name]) -> pasteboardWatcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates and starts a new `hs.pasteboard.watcher` object for watching for Pasteboard changes. |
| **Parameters**                                       | <ul><li>callbackFn - A function that will be called when the Pasteboard contents has changed. It should accept one parameter:</li><li>A string containing the pasteboard contents or <code>nil</code> if the contents is not a valid string.</li><li>name - An optional string containing the name of the pasteboard. Defaults to the system pasteboard.</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.pasteboard.watcher</code> object</li></ul> |
| **Notes**                                            | <ul><li>Internally this extension uses a single <code>NSTimer</code> to check for changes to the pasteboard count every half a second.</li><li>Example usage: <code>lua generalPBWatcher = hs.pasteboard.watcher.new(function(v) print(string.format("General Pasteboard Contents: %s", v)) end) specialPBWatcher = hs.pasteboard.watcher.new(function(v) print(string.format("Special Pasteboard Contents: %s", v)) end, "special") hs.pasteboard.writeObjects("This is on the general pasteboard.") hs.pasteboard.writeObjects("This is on the special pasteboard.", "special")</code></li></ul> |

### Methods

#### [running](#running)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pasteboard.watcher:running() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a boolean indicating whether or not the Pasteboard Watcher is currently running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean value indicating whether or not the timer is currently running.</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pasteboard.watcher:start() -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Starts an `hs.pasteboard.watcher` object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.pasteboard.watcher</code> object</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.pasteboard.watcher:stop() -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops an `hs.pasteboard.watcher` object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.pasteboard.watcher</code> object</li></ul> |

