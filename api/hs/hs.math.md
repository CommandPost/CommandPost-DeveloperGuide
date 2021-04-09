# [docs](index.md) » hs.math
---

Various helpful mathematical functions

This module includes, and is a superset of the built-in Lua `math` library so it is safe to do something like the following in your own code and still have access to both libraries:

    local math = require("hs.math")
    local n = math.sin(math.minFloat) -- works even though they're both from different libraries

The documentation for the math library can be found at http://www.lua.org/manual/5.3/ or from the Hammerspoon console via the help command: `help.lua.math`. This includes the following functions and variables:

  * hs.math.abs        - help available via `help.lua.math.abs`
  * hs.math.acos       - help available via `help.lua.math.acos`
  * hs.math.asin       - help available via `help.lua.math.asin`
  * hs.math.atan       - help available via `help.lua.math.atan`
  * hs.math.ceil       - help available via `help.lua.math.ceil`
  * hs.math.cos        - help available via `help.lua.math.cos`
  * hs.math.deg        - help available via `help.lua.math.deg`
  * hs.math.exp        - help available via `help.lua.math.exp`
  * hs.math.floor      - help available via `help.lua.math.floor`
  * hs.math.fmod       - help available via `help.lua.math.fmod`
  * hs.math.huge       - help available via `help.lua.math.huge`
  * hs.math.log        - help available via `help.lua.math.log`
  * hs.math.max        - help available via `help.lua.math.max`
  * hs.math.maxinteger - help available via `help.lua.math.maxinteger`
  * hs.math.min        - help available via `help.lua.math.min`
  * hs.math.mininteger - help available via `help.lua.math.mininteger`
  * hs.math.modf       - help available via `help.lua.math.modf`
  * hs.math.pi         - help available via `help.lua.math.pi`
  * hs.math.rad        - help available via `help.lua.math.rad`
  * hs.math.random     - help available via `help.lua.math.random`
  * hs.math.randomseed - help available via `help.lua.math.randomseed`
  * hs.math.sin        - help available via `help.lua.math.sin`
  * hs.math.sqrt       - help available via `help.lua.math.sqrt`
  * hs.math.tan        - help available via `help.lua.math.tan`
  * hs.math.tointeger  - help available via `help.lua.math.tointeger`
  * hs.math.type       - help available via `help.lua.math.type`
  * hs.math.ult        - help available via `help.lua.math.ult`

Additional functions and values that are specific to Hammerspoon which provide expanded math support are documented here.

## API Overview
* Constants - Useful values which cannot be changed
 * [minFloat](#minfloat)
* Functions - API calls offered directly by the extension
 * [isFinite](#isfinite)
 * [isInfinite](#isinfinite)
 * [isNaN](#isnan)
 * [randomFloat](#randomfloat)
 * [randomFromRange](#randomfromrange)

## API Documentation

### Constants

#### [minFloat](#minfloat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.math.minFloat` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Smallest positive floating point number representable in Hammerspoon |
| **Notes**                                            | <ul><li>Because specifying a delay of 0 to <code>hs.timer.doAfter</code> results in the event not triggering, use this value to indicate that the action should occur as soon as possible after the current code block has completed execution.</li></ul> |

### Functions

#### [isFinite](#isfinite)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.math.isFinite(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns whether or not the value is a finite number |
| **Parameters**                                       | <ul><li><code>value</code> - the value to be tested</li></ul> |
| **Returns**                                          | <ul><li>true if the value is a finite number, or false otherwise</li></ul> |
| **Notes**                                            | <ul><li>This function returns true if the value is a number and both <a href="#isNaN">hs.math.isNaN</a> and <a href="#isInfinite">hs.math.isInfinite</a> return false.</li></ul> |

#### [isInfinite](#isinfinite)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.math.isInfinite(value) -> 1, -1, false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns whether or not the value is the mathematical equivalent of either positive or negative "Infinity" |
| **Parameters**                                       | <ul><li><code>value</code> - the value to be tested</li></ul> |
| **Returns**                                          | <ul><li>1 if the value is equivalent to positive infinity, -1 if the value is equivalent to negative infinity, or false otherwise.</li></ul> |
| **Notes**                                            | <ul><li>This function specifically checks if the <code>value</code> is equivalent to positive or negative infinity --- it does not do type checking. If <code>value</code> is not a numeric value (e.g. a string), it <em>cannot</em> be equivalent to positive or negative infinity and will return false.</li><li>Because lua treats any value other than <code>nil</code> and <code>false</code> as <code>true</code>, the return value of this function can be safely used in conditionals when you don't care about the sign of the infinite value.</li></ul> |

#### [isNaN](#isnan)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.math.isNaN(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns whether or not the value is the mathematical equivalent of "Not-A-Number" |
| **Parameters**                                       | <ul><li><code>value</code> - the value to be tested</li></ul> |
| **Returns**                                          | <ul><li>true if <code>value</code> is equal to the mathematical "value" of NaN, or false otherwise</li></ul> |
| **Notes**                                            | <ul><li>Mathematical <code>NaN</code> represents an impossible value, usually the result of a calculation, yet is still considered within the domain of mathematics. The most common case is the result of <code>n / 0</code> as division by 0 is considered undefined or "impossible".</li><li>This function specifically checks if the <code>value</code> is <code>NaN</code> --- it does not do type checking. If <code>value</code> is not a numeric value (e.g. a string), it <em>cannot</em> be equivalent to <code>NaN</code> and this function will return false.</li></ul> |

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

