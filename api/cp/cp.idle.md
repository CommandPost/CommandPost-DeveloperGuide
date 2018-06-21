# [docs](index.md) » cp.idle
---

This library allows tasks to be queue for execution when the computer has
been idle for a specified amount of time. 'Idle' is defined as no keyboard
or mouse movement.

## API Overview
* Functions - API calls offered directly by the extension
 * [queue](#queue)

## API Documentation

### Functions

#### [queue](#queue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.idle.queue(idleSeconds, actionFn[, retryOnError]) -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds an action to the idle queue, which will be run after the the computer has been idle                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `idleSeconds`		- The number of seconds of idle time must have elapsed run the action</li><li markdown="1">* `actionFn`		- The function to execute</li><li markdown="1">* `retryOnError`	- Optional. If set to `true`, the action will try running again if there is an error.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* Nothing</li></ul>          |

