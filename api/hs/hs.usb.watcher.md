# [docs](index.md) » hs.usb.watcher
---

Watch for USB device connection/disconnection events

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.usb.watcher.new(fn) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new watcher for USB device events                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">fn - A function that will be called when a USB device is inserted or removed. The function should accept a single parameter, which is a table containing the following keys:</li><li markdown="1"> eventType - A string containing either "added" or "removed" depending on whether the USB device was connected or disconnected</li><li markdown="1"> productName - A string containing the name of the device</li><li markdown="1"> vendorName - A string containing the name of the device vendor</li><li markdown="1"> vendorID - A number containing the Vendor ID of the device</li><li markdown="1"> productID - A number containing the Product ID of the device</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `hs.usb.watcher` object</li></ul>          |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.usb.watcher:start() -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the USB watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `hs.usb.watcher` object</li></ul>          |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.usb.watcher:stop() -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the USB watcher                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `hs.usb.watcher` object</li></ul>          |

