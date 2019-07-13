# [docs](index.md) » hs.hid.led
---

HID LED interface for Hammerspoon, controls the state of keyboard LEDs

## API Overview
* Functions - API calls offered directly by the extension
 * [set](#set)

## API Documentation

### Functions

#### [set](#set)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hid.led.set(name, state) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Assigns HID LED to the desired state |
| **Parameters**                                       | <ul><li>name  - LED name: "caps", "scroll" or "num"</li><li>state - A boolean indicating desired state</li></ul> |
| **Returns**                                          | <ul><li>true if success, false if error</li></ul> |

