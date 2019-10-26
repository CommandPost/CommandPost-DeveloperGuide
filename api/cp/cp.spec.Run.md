# [docs](index.md) » cp.spec.Run
---

An individual run of a test [Definition](cp.spec.Definition.md) or [Specification](cp.spec.Specification.md).

## Submodules
 * [cp.spec.Run.This](cp.spec.Run.This.md)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [Run](#run)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [phase](#phase)
 * [report](#report)
 * [result](#result)
 * [shared](#shared)
 * [source](#source)
* Methods - API calls which can only be made on an object returned by a constructor
 * [debug](#debug)
 * [expectAbort](#expectabort)
 * [expectFail](#expectfail)
 * [isDebugging](#isdebugging)
 * [isExpectingAbort](#isexpectingabort)
 * [isExpectingFail](#isexpectingfail)
 * [log](#log)
 * [onBefore](#onbefore)
 * [onBfter](#onbfter)
 * [onRunning](#onrunning)
 * [parent](#parent)
 * [verbose](#verbose)

## API Documentation

### Constructors

#### [Run](#run)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run(name) -> cp.spec.Run` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new test run. |
| **Parameters**                                       | <ul><li>name          - The name of the run.</li><li>source        - The object (typically a <a href="cp.spec.Definition.md">Definition</a>) that initiated the run.</li></ul> |

### Fields

#### [phase](#phase)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.phase <cp.spec.Run.phase>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current [phase](#phase) of the run. |

#### [report](#report)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.report <cp.spec.Report>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The reports of the run. |

#### [result](#result)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.result <cp.spec.Run.result>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current result. Defaults to `Run.result.passing`. |

#### [shared](#shared)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.shared <table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The set of data shared by all phases of the Run. Data from parent Runs will also be available. |

#### [source](#source)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run.source` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The object that initiated the run. Typically a [Definition](cp.spec.Definition.md). |

### Methods

#### [debug](#debug)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:debug() -> cp.spec.Run` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Enables debugging on this `Run`. Any calls to [#log] will be output to the console. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Run</code> instance.</li></ul> |

#### [expectAbort](#expectabort)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:expectAbort([messagePattern]) -> Run` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates that this spec is expecting an abort/`error` to occur. |
| **Parameters**                                       | <ul><li>messagePattern - The pattern to check the fail message against. If not provided, any message will match.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Run</code> instance.</li></ul> |

#### [expectFail](#expectfail)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:expectFail([messagePattern]) -> Run` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates that this spec is expecting an assert/fail to occur. |
| **Parameters**                                       | <ul><li>messagePattern - The pattern to check the fail message against. If not provided, any message will match.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Run</code> instance.</li></ul> |

#### [isDebugging](#isdebugging)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:isDebugging() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if `debug` has been enabled on this or any parent `Run`. |

#### [isExpectingAbort](#isexpectingabort)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:isExpectingAbort() -> boolean, string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the run is expecting a abort/error to occur. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>boolean - <code>true</code>, if a fail is expected.</li><li>string - the message pattern, if specified.</li></ul> |

#### [isExpectingFail](#isexpectingfail)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:isExpectingFail() -> boolean, string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the run is expecting a fail to occur. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>boolean - <code>true</code>, if a fail is expected.</li><li>string - the message pattern, if specified.</li></ul> |

#### [log](#log)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:log(message[, ...])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | When the current [Run](cp.spec.Run.md) is in [debug](#debug) mode, output the message to the console. |
| **Parameters**                                       | <ul><li>message   - the text message to output.</li><li>...       - optional parameters, to be injected into the message, ala <code>string.format</code>.</li></ul> |

#### [onBefore](#onbefore)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:onBefore(actionFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a callback function to run prior to executing the actual test. |
| **Parameters**                                       | <ul><li>actionFn      - The function to run, passed this <code>Run.This</code> as the first parameter.</li></ul> |

#### [onBfter](#onbfter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:onBfter(actionFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a callback function to run after to executing the actual test, pass or fail. |
| **Parameters**                                       | <ul><li>actionFn      - The function to run, passed this <code>Run</code> as the first parameter.</li></ul> |

#### [onRunning](#onrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:onRunning(actionFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds a callback function to run during the test. |
| **Parameters**                                       | <ul><li>runningFn     - The function to run, passed <a href="cp.spec.Run.This.md">Run.This</a> as the first parameter.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:parent([parent]) -> cp.spec.Run` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets and/or sets the parent `Run` for this run. |
| **Parameters**                                       | <ul><li>parent        - (optional) If set, will set the parent <code>Run</code>.</li></ul> |
| **Returns**                                          | <ul><li>The current parent <code>Run</code>.</li></ul> |
| **Notes**                                            | <ul><li>If a <code>parent</code> is provided and there is already another Run set as a parent, an error is thrown.</li></ul> |

#### [verbose](#verbose)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Run:verbose([isVerbose]) -> boolean | self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Either sets the `verbose` value and returns itself for further chaining, or returns |
| **Parameters**                                       | <ul><li>isVerbose     - (optional) if <code>true</code> or <code>false</code> will update the verbose status and return this <code>Run</code>.</li></ul> |
| **Returns**                                          | <ul><li>The current <code>verbose</code> status, or this <code>Run</code> if <code>isVerbose</code> is provided.</li></ul> |

