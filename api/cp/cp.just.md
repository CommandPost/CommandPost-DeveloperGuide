# [docs](index.md) » cp.just
---

This module provides functions to help with performing tasks which may be
delayed, up to a finite number of loops.

## API Overview
* Functions - API calls offered directly by the extension
 * [doUntil](#doUntil)
 * [doWhile](#doWhile)
 * [wait](#wait)

## API Documentation

### Functions

#### [doUntil](#doUntil)
| **Signature**                               | `cp.just.doUntil(actionFn, period, loops) -> result`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Performs an `action` function, looping until the result of the function evaluates to `true` (or a non-nil value).                                                                     |
| **Parameters**                              | <ul><li>`actionFn`	- a fuction which is called on each loop. It should return a 'truthy' value.</li><li>`timeout`	- (optional) the number of seconds after which we will give up. Defaults to 1 second.</li><li>`frequency`	- (optional) the number of loops to perform before giving up. Defaults to 1 millisecond.</li></ul> |
| **Returns**                                 | <ul><li>The last return value of the action function.</li></ul>          |

#### [doWhile](#doWhile)
| **Signature**                               | `cp.just.doWhile(actionFn, period, loops) -> UI`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Performs an 'action' function, looping while the result of the function evaluates to 'true'.                                                                     |
| **Parameters**                              | <ul><li>actionFn	- a fuction which is called on each loop. It should return a 'truthy' value.</li><li>`timeout`	- (optional) the number of seconds after which we will give up. Defaults to 1 second.</li><li>`frequency`	- (optional) the number of loops to perform before giving up. Defaults to 1 millisecond.</li></ul> |
| **Returns**                                 | <ul><li>The last return value of the action function.</li></ul>          |

#### [wait](#wait)
| **Signature**                               | `cp.just.wait(integer) -> nil`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Pauses the application for the specified number of seconds.                                                                     |
| **Parameters**                              | <ul><li>periodInSeconds - the number of seconds to pause for.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

