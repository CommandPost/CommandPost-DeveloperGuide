# [docs](index.md) » hs.usb
---

Inspect USB devices

## Submodules
 * [hs.usb.watcher](hs.usb.watcher.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [attachedDevices](#attacheddevices)

## API Documentation

### Functions

#### [attachedDevices](#attacheddevices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.usb.attachedDevices() -> table or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets details about currently attached USB devices |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing information about currently attached USB devices, or nil if an error occurred. The table contains a sub-table for each USB device, the keys of which are:</li><li>productName - A string containing the name of the device</li><li>vendorName - A string containing the name of the device vendor</li><li>vendorID - A number containing the Vendor ID of the device</li><li>productID - A number containing the Product ID of the device</li></ul> |

