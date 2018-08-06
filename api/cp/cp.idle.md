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
| **Type**                                             | Function |
| **Description**                                      | Adds an action to the idle queue, which will be run after the the computer has been idle |
| **Parameters**                                       | <ul><li><code>idleSeconds</code>     - The number of seconds of idle time must have elapsed run the action</li><li><code>actionFn</code>        - The function to execute</li><li><code>retryOnError</code>    - Optional. If set to <code>true</code>, the action will try running again if there is an error.</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

