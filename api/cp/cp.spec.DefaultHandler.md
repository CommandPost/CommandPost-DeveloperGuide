# [docs](index.md) » cp.spec.DefaultHandler
---

Default implementation of [Handler](cp.spec.Handler.md), which
outputs via the standard `print` function.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [aborted](#aborted)
 * [failed](#failed)
 * [filter](#filter)
 * [printf](#printf)
 * [printSpacer](#printspacer)
 * [start](#start)
 * [stop](#stop)
 * [summary](#summary)
 * [waiting](#waiting)

## API Documentation

### Methods

#### [aborted](#aborted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.DefaultHandler:aborted(run, msg)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Prints an "[ABORT]" message. |
| **Parameters**                                       | <ul><li>run      - the <a href="cp.spec.Run.md">run</a></li><li>msg       - the message string.</li></ul> |

#### [failed](#failed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.DefaultHandler:failed(run, msg)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Prints a "[FAIL]" message. |
| **Parameters**                                       | <ul><li>run      - the <a href="cp.spec.Run.md">run</a></li><li>msg       - the message string.</li></ul> |

#### [filter](#filter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.DefaultHandler:filter(run, msg)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Prints a "[FILTER]" message. |
| **Parameters**                                       | <ul><li>run      - the <a href="cp.spec.Run.md">run</a></li><li>msg       - the message string.</li></ul> |

#### [printf](#printf)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.DefaultHandler:printf(test, ...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Prints a spacer (if not the first line), followed by the text, |
| **Parameters**                                       | <ul><li>text      - The message to print.</li><li>...       - The parameters to interpolate into the text message.</li></ul> |

#### [printSpacer](#printspacer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.DefaultHandler:printSpacer()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Prints a blank line if this is not the first time it has been called. |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.DefaultHandler:start(run, msg)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | If the handler or run is verbose, prints a "[PASS]" message. |
| **Parameters**                                       | <ul><li>run      - the <a href="cp.spec.Run.md">run</a></li><li>msg       - the message string.</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.DefaultHandler:stop(run)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | If the handler or run is verbose, prints a "[STOP]" message. |
| **Parameters**                                       | <ul><li>run      - the <a href="cp.spec.Run.md">run</a></li></ul> |

#### [summary](#summary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.DefaultHandler:summary(run, report)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | If the handler or run is verbose, prints a "[RESULT]" message. |
| **Parameters**                                       | <ul><li>run      - the <a href="cp.spec.Run.md">run</a></li><li>report    - the <a href="cp.spec.Report.md">report</a></li></ul> |

#### [waiting](#waiting)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.DefaultHandler:waiting(run, timeout)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Prints a "[WAIT]" message with the timeout value.. |

