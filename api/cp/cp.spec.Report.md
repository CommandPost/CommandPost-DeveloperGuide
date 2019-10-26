# [docs](index.md) » cp.spec.Report
---

The results of a test [run](cp.spec.Run.md).

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [Report](#report)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [aborts](#aborts)
 * [failures](#failures)
 * [passes](#passes)
 * [run](#run)
 * [startTime](#starttime)
 * [stopTime](#stoptime)
 * [totalTime](#totaltime)
* Methods - API calls which can only be made on an object returned by a constructor
 * [aborted](#aborted)
 * [add](#add)
 * [failed](#failed)
 * [passed](#passed)
 * [start](#start)
 * [stop](#stop)
 * [summary](#summary)
 * [waiting](#waiting)

## API Documentation

### Constructors

#### [Report](#report)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report(run) -> cp.spec.Report` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new test report. |

### Fields

#### [aborts](#aborts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report.aborts <number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The number of aborts in the run. |

#### [failures](#failures)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report.failures <number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The number of failures in the run. |

#### [passes](#passes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report.passes <number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The number of passes in the run. |

#### [run](#run)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report.run <cp.spec.Run>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [run](cp.spec.Run.md) the reports are for. |

#### [startTime](#starttime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report.startTime <number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The number of seconds since epoch when the test started, or `nil` if not started yet. |

#### [stopTime](#stoptime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report.stopTime <number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The number of seconds since epoch when the tests stopped, or `nil` if not stopped yet. |

#### [totalTime](#totaltime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report.totalTime <number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The number of seconds the run took (may be decimal), or `nil` if the test hasn't run. |

### Methods

#### [aborted](#aborted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report:aborted(message)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Records an abort, with the specified message. |
| **Parameters**                                       | <ul><li>message       - The related message to output.</li></ul> |

#### [add](#add)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report:add(otherReport) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds the passes/failures/aborts from the other report into this one. |
| **Parameters**                                       | <ul><li>otherReport   - The other report to add.</li></ul> |

#### [failed](#failed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report:failed(message)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Records a fail, with the specified message. |
| **Parameters**                                       | <ul><li>message       - The related message to output.</li></ul> |

#### [passed](#passed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report:passed([message])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Records a pass, with the specified message. |
| **Parameters**                                       | <ul><li>message       - an optional additional message to output.</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report:start() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Logs the start time. |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report:stop() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Logs the end time. |

#### [summary](#summary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report:summary()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Summarise the reports. |

#### [waiting](#waiting)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Report:waiting(timeout)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Records that a run is waiting for up to the specified amount of time. |
| **Parameters**                                       | <ul><li>timeout   - The timeout to wait for, in seconds.</li></ul> |

