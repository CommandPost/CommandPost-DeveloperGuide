# [docs](index.md) » cp.spec.Run.This
---

A token passed to test functions to allow them to indicate if a test [run](cp.spec.Run.md)
will complete asynchronously.

## API Overview
* Constants - Useful values which cannot be changed
 * [state](#state)
* Functions - API calls offered directly by the extension
 * [defaultTimeout](#defaulttimeout)
* Constructors - API calls which return an object, typically one that offers API methods
 * [This](#this)
* Methods - API calls which can only be made on an object returned by a constructor
 * [abort](#abort)
 * [cleanup](#cleanup)
 * [done](#done)
 * [expectAbort](#expectabort)
 * [expectFail](#expectfail)
 * [fail](#fail)
 * [isActive](#isactive)
 * [isDone](#isdone)
 * [isWaiting](#iswaiting)
 * [log](#log)
 * [prepare](#prepare)
 * [run](#run)
 * [toObserver](#toobserver)
 * [wait](#wait)

## API Documentation

### Constants

#### [state](#state)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This.state` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A collection of states that a `Run.This` can be in. |
| **Notes**                                            | <ul><li>States include:</li><li>running     - The Run is currently running and will terminate at the end of the function (synchrnonous).</li><li>waiting     - The Run is waiting, and will terminate when <a href="#done">done()</a> is called. (asynchronous).</li><li>done        - The Run is done.</li></ul> |

### Functions

#### [defaultTimeout](#defaulttimeout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This.defaultTimeout([timeout]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets and/or sets the default timeout for asynchronous tests. |
| **Parameters**                                       | <ul><li>timeout       - (optional) the new timeout, in seconds.</li></ul> |
| **Returns**                                          | <ul><li>The current default timeout, in seconds.</li></ul> |

### Constructors

#### [This](#this)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This(run, actionFn, index) -> cp.spec.Run.This` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Run.This` instance for a [Run](cp.spec.Run.md). |
| **Parameters**                                       | <ul><li>run       - The <a href="cp.spec.Run.md">Run</a>.</li><li>actionFn  - The action function to execute.</li><li>index     - The index of the action in the current phase.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Run.This</code>.</li></ul> |

### Methods

#### [abort](#abort)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:abort([message])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates the stage has aborted. |
| **Parameters**                                       | <ul><li>message   - The optional message to output.</li></ul> |

#### [cleanup](#cleanup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:cleanup()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Cleans up This after a step. |

#### [done](#done)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:done()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates that the test is completed. |

#### [expectAbort](#expectabort)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:expectAbort([messagePattern]) -> Run.This` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates that this spec is expecting an abort/`error` to occur. |
| **Parameters**                                       | <ul><li>messagePattern - The pattern to check the fail message against. If not provided, any message will match.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Run.This</code> instance.</li></ul> |

#### [expectFail](#expectfail)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:expectFail([messagePattern]) -> Run.This` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates that this spec is expecting an assert/fail to occur. |
| **Parameters**                                       | <ul><li>messagePattern - The pattern to check the fail message against. If not provided, any message will match.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Run.This</code> instance.</li></ul> |

#### [fail](#fail)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:fail([message])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates the run has failed. |
| **Parameters**                                       | <ul><li>message   - The optional message to output.</li></ul> |

#### [isActive](#isactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:isActive() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the this is in an active state - either `running` or `waiting`. |
| **Returns**                                          | <ul><li><code>true</code> if isActive.</li></ul> |

#### [isDone](#isdone)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:isDone() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns `true` if this is done. |

#### [isWaiting](#iswaiting)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:isWaiting() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the [Run](cp.spec.Run.md) is waiting for this execution to complete via the |
| **Returns**                                          | <ul><li><code>true</code> if the waiting.</li></ul> |

#### [log](#log)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:log(message[, ...])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | When the current [Run](cp.spec.Run.md) is in [debug](#debug) mode, output the message to the console. |
| **Parameters**                                       | <ul><li>message   - the text message to output.</li><li>...       - optional parameters, to be injected into the message, ala <code>string.format</code>.</li></ul> |

#### [prepare](#prepare)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:prepare()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Prepares this to run. |

#### [run](#run)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:run() -> cp.spec.Run` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the current [Run](cp.spec.Run.md) |

#### [toObserver](#toobserver)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:toObserver([onNext[, onError[, onCompleted]]) -> cp.rx.Observer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates an [Observer](cp.rx.Observer.md). If the `onNext`/`onError`/`onCompleted` functions are |
| **Parameters**                                       | <ul><li>onNext - The <code>next</code> handler.</li><li>onError - The <code>error</code> handler.</li><li>onCompleted - The <code>completed</code> handler.</li></ul> |

#### [wait](#wait)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.This:wait([timeout])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates that the test is continuing asynchronously, and will |
| **Parameters**                                       | <ul><li>timeout       - (optional) The number of seconds to wait before timing out.</li></ul> |
| **Notes**                                            | <ul><li>If not provided, <a href="cp.spec.Run.This.md#defaultTimeout">Run.This.defaultTimeout()</a> is used.</li></ul> |

