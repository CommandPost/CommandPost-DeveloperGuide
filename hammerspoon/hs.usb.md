# [docs](index.md) » hs.usb
---

Inspect USB devices

## Submodules
 * [hs.usb.watcher](hs.usb.watcher.md)

## API Overview
* Functions - API calls offered directly by the extension
* [attachedDevices](#attachedDevices)

## API Documentation

### Functions

#### [attachedDevices](#attachedDevices)
| Signature   | hs.usb.attachedDevices() -> table or nil  |
| Type        | Function |
| Description | Gets details about currently attached USB devices |
| Parameters |  * None | | Returns |  * A table containing information about currently attached USB devices, or nil if an error occurred. The table contains a sub-table for each USB device, the keys of which are:  * productName - A string containing the name of the device  * vendorName - A string containing the name of the device vendor  * vendorID - A number containing the Vendor ID of the device  * productID - A number containing the Product ID of the device | 