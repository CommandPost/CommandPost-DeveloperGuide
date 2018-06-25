# [docs](index.md) » hs.hid
---

HID interface for Hammerspoon, controls and queries caps lock state

Portions sourced from (https://discussions.apple.com/thread/7094207).

## API Overview
* Functions - API calls offered directly by the extension
 * [get](#get)
 * [set](#set)
 * [toggle](#toggle)

## API Documentation

### Functions

#### [get](#get)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hid.capslock.get() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks the state of the caps lock via HID                                                                                         |
| **Returns**                                          | <ul><br /><li>true if on, false if off</li><br /></ul>                                           |

#### [set](#set)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hid.capslock.set(state) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Assigns capslock to the desired state                                                                                         |
| **Parameters**                                       | <ul><br /><li>state - A boolean indicating desired state</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>true if on, false if off</li><br /></ul>                                           |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hid.capslock.toggle() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles the state of caps lock via HID                                                                                         |
| **Returns**                                          | <ul><br /><li>true if on, false if off</li><br /></ul>                                           |

