# [docs](index.md) » cp.just
---

This module provides functions to help with performing tasks which may be
delayed, up to a finite number of loops.

## API Overview
* Functions - API calls offered directly by the extension
 * [doUntil](#dountil)
 * [doWhile](#dowhile)
 * [wait](#wait)

## API Documentation

### Functions

#### [doUntil](#dountil)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.just.doUntil(actionFn, period, loops) -> result` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs an `action` function, looping until the result of the function evaluates to `true` (or a non-nil value).                                                                                         |
| **Parameters**                                       | <ul><li>`actionFn`	- a fuction which is called on each loop. It should return a 'truthy' value.</li><li>`timeout`	- (optional) the number of seconds after which we will give up. Defaults to 1 second.</li><li>`frequency`	- (optional) the number of loops to perform before giving up. Defaults to 1 millisecond.</li></ul> |
| **Returns**                                          | <ul><li>The last return value of the action function.</li></ul>          |

#### [doWhile](#dowhile)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.just.doWhile(actionFn, period, loops) -> UI` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs an 'action' function, looping while the result of the function evaluates to 'true'.                                                                                         |
| **Parameters**                                       | <ul><li>actionFn	- a fuction which is called on each loop. It should return a 'truthy' value.</li><li>`timeout`	- (optional) the number of seconds after which we will give up. Defaults to 1 second.</li><li>`frequency`	- (optional) the number of loops to perform before giving up. Defaults to 1 millisecond.</li></ul> |
| **Returns**                                          | <ul><li>The last return value of the action function.</li></ul>          |

#### [wait](#wait)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`cp.just.wait(integer) -> nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Pauses the application for the specified number of seconds.                                                                                         |
| **Parameters**                                       | <ul><li>periodInSeconds - the number of seconds to pause for.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

