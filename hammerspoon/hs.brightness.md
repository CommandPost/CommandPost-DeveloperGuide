# [docs](index.md) » hs.brightness
---

Inspect/manipulate display brightness

Home: https://github.com/asmagill/mjolnir_asm.sys

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Functions - API calls offered directly by the extension
 * [ambient](#ambient)
 * [get](#get)
 * [set](#set)

## API Documentation

### Functions

| #### [ambient](#ambient)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.brightness.ambient() -> number                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the current ambient brightness                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * A number containing the current ambient brightness, measured in lux. If an error occurred, the number will be -1                  |
| **Notes**                                   |  * Even though external Apple displays include an ambient light sensor, their data is typically not available, so this function will likely only be useful to MacBook users * The raw sensor data is converted to lux via an algorithm used by Mozilla Firefox and is not guaranteed to give an accurate lux value                        |

| #### [get](#get)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.brightness.get() -> number                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Returns the current brightness of the display                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * A number containing the brightness of the display, between 0 and 100                  |

| #### [set](#set)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.brightness.set(brightness) -> boolean                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Sets the display brightness                                                           |
| **Parameters**                              |  * brightness - A number between 0 and 100         |
| **Returns**                                 |  * True if the brightness was set, false if not                  |

