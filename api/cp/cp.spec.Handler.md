# [docs](index.md) » cp.spec.Handler
---

Subclasses of this can customise how reports are handled.
All methods do nothing.

See [DefaultHandler](cp.spec.DefaultHandler.md).

## API Overview
* Functions - API calls offered directly by the extension
 * [default](#default)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Handler](#handler)
* Methods - API calls which can only be made on an object returned by a constructor
 * [aborted](#aborted)
 * [checkVerbose](#checkverbose)
 * [failed](#failed)
 * [filter](#filter)
 * [passed](#passed)
 * [start](#start)
 * [stop](#stop)
 * [summary](#summary)
 * [verbose](#verbose)
 * [waiting](#waiting)

## API Documentation

### Functions

#### [default](#default)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler.default([handler]) -> cp.spec.Handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets and sets the current default `Handler` implementation. |
| **Parameters**                                       | <ul><li>handler       - (optional) when provided, sets the default to the specified handler.</li></ul> |
| **Returns**                                          | <ul><li>The current <code>Handler</code> implementation.</li></ul> |

### Constructors

#### [Handler](#handler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler() -> cp.spec.Handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Handler` |

### Methods

#### [aborted](#aborted)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:aborted(run)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call to indicate the [run](cp.spec.Run.md) has had an abort. |
| **Parameters**                                       | <ul><li>run      - The test run.</li><li>msg       - The message.</li></ul> |

#### [checkVerbose](#checkverbose)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:checkVerbose(run) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates if either the handler or the individual [Run](cp.spec.Run.md) is |

#### [failed](#failed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:failed(run)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call to indicate the [run](cp.spec.Run.md) has failed. |
| **Parameters**                                       | <ul><li>run      - The test run.</li><li>msg       - The message.</li></ul> |

#### [filter](#filter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:filter(run, msg)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call to indicate the [run](cp.spec.Run.md) is running due to being filtered. |
| **Parameters**                                       | <ul><li>run      - The test run.</li><li>msg       - The message.</li></ul> |

#### [passed](#passed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:passed(run)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call to indicate the [run](cp.spec.Run.md) has passed. |
| **Parameters**                                       | <ul><li>run      - The test run.</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:start(run)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call to indicate the [run](cp.spec.Run.md) has started. |
| **Parameters**                                       | <ul><li>run      - The test run.</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:stop(run)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call to indicate the [run](cp.spec.Run.md) has completed. |
| **Parameters**                                       | <ul><li>run      - The test run.</li></ul> |

#### [summary](#summary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:summary(run, report)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call to indicate the [run](cp.spec.Run.md) has passed with the given [report](cp.spec.Report.md). |
| **Parameters**                                       | <ul><li>run          - The test run.</li><li>report        - The test reports.</li></ul> |

#### [verbose](#verbose)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:verbose([isVerbose]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicate that the handler is (or is not) verbose. |
| **Parameters**                                       | <ul><li>isVerbose     - (optional) If set to <code>false</code>, the handler will not be verbose. Defaults to <code>true</code>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Handler</code> instance, for chaining.</li></ul> |

#### [waiting](#waiting)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handler:waiting(run, timeout)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Call to indicate that the run is waiting asynchronously. |
| **Parameters**                                       | <ul><li>run      - The test run.</li><li>timeout  - The timeout, in seconds.</li></ul> |

