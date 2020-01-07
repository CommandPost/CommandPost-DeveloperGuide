# [docs](index.md) » hs.math
---

Various helpful mathematical functions

## API Overview
* Functions - API calls offered directly by the extension
 * [randomFloat](#randomfloat)
 * [randomFromRange](#randomfromrange)

## API Documentation

### Functions

#### [randomFloat](#randomfloat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.math.randomFloat() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a random floating point number between 0 and 1 |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A random number between 0 and 1</li></ul> |

#### [randomFromRange](#randomfromrange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.math.randomFromRange(start, end) -> integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a random integer between the start and end paramters |
| **Parameters**                                       | <ul><li>start - A number to start the range, must be greater than or equal to zero</li><li>end - A number to end the range, must be greater than zero and greater than <code>start</code></li></ul> |
| **Returns**                                          | <ul><li>A randomly chosen integer between <code>start</code> and <code>end</code></li></ul> |

