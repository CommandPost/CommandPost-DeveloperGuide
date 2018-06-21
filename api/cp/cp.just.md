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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.just.doUntil(actionFn[, timeout[, frequency]]) -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs an `action` function, looping until the result of the function evaluates to `true` (or a non-nil value).                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`actionFn`	- a fuction which is called on each loop. It should return a 'truthy' value.</li><li markdown="1">`timeout`	- (optional) the number of seconds after which we will give up. Defaults to 1 second.</li><li markdown="1">`frequency`	- (optional) the amount of time between checks. Defaults to 1 millisecond.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The last return value of the action function.</li></ul>          |

#### [doWhile](#dowhile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.just.doWhile(actionFn[, timeout[, frequency]]) -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs an 'action' function, looping while the result of the function evaluates to `true`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`actionFn`	- a fuction which is called on each loop. It should return a 'truthy' value.</li><li markdown="1">`timeout`	- (optional) the number of seconds after which we will give up. Defaults to 1 second.</li><li markdown="1">`frequency`	- (optional) the time between checks. Defaults to 1 millisecond.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The last return value of the action function.</li></ul>          |

#### [wait](#wait)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.just.wait(integer) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Pauses the application for the specified number of seconds.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">periodInSeconds - the number of seconds to pause for.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

