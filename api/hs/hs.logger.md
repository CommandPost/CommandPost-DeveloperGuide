# [docs](index.md) » hs.logger
---

Simple logger for debugging purposes

Note: "methods" in this module are actually "static" functions - see `hs.logger.new()`

## API Overview
* Variables - Configurable values
 * [defaultLogLevel](#defaultloglevel)
* Functions - API calls offered directly by the extension
 * [history](#history)
 * [historySize](#historysize)
 * [new](#new)
 * [printHistory](#printhistory)
 * [setGlobalLogLevel](#setgloballoglevel)
 * [setModulesLogLevel](#setmodulesloglevel)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [level](#level)
* Methods - API calls which can only be made on an object returned by a constructor
 * [d](#d)
 * [df](#df)
 * [e](#e)
 * [ef](#ef)
 * [f](#f)
 * [getLogLevel](#getloglevel)
 * [i](#i)
 * [setLogLevel](#setloglevel)
 * [v](#v)
 * [vf](#vf)
 * [w](#w)
 * [wf](#wf)

## API Documentation

### Variables

#### [defaultLogLevel](#defaultloglevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger.defaultLogLevel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Default log level for new logger instances.                                                                                         |

### Functions

#### [history](#history)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger.history() -> list of log entries` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the global log history                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a list of (at most `hs.logger.historySize()`) log entries produced by all the logger instances, in chronological order;</li><li>   each entry is a table with the following fields:</li><li>  time - timestamp in seconds since the epoch</li><li>  level - a number between 1 (error) and 5 (verbose)</li><li>  id - a string containing the id of the logger instance that produced this entry</li><li>  message - a string containing the logged message</li></ul>          |

#### [historySize](#historysize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger.historySize([size]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets or gets the global log history size                                                                                         |
| **Parameters**                                       | <ul><li>size - (optional) the desired number of log entries to keep in the history;</li><li>   if omitted, will return the current size; the starting value is 0 (disabled)</li></ul> |
| **Returns**                                          | <ul><li>the current or new history size</li></ul>          |
| **Notes**                                            | <ul><li>if you change history size (other than from 0) after creating any logger instances, things will likely break</li></ul>                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger.new(id, loglevel) -> logger` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new logger instance                                                                                         |
| **Parameters**                                       | <ul><li>id - a string identifier for the instance (usually the module name)</li><li>loglevel - (optional) can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose', or a corresponding number</li><li>   between 0 and 5; uses `hs.logger.defaultLogLevel` if omitted</li></ul> |
| **Returns**                                          | <ul><li>the new logger instance</li></ul>          |
| **Notes**                                            | <ul><li>the logger instance created by this method is not a regular object, but a plain table with "static" functions;</li><li>   therefore, do not use the colon syntax for so-called "methods" in this module (as in `mylogger:setLogLevel(3)`);</li><li>   you must instead use the regular dot syntax: `mylogger.setLogLevel(3)`</li></ul>                |

#### [printHistory](#printhistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger.printHistory([entries[, level[, filter[, caseSensitive]]]])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Prints the global log history to the console                                                                                         |
| **Parameters**                                       | <ul><li>entries - (optional) the maximum number of entries to print; if omitted, all entries in the history will be printed</li><li>level - (optional) the desired log level (see `hs.logger:setLogLevel()`); if omitted, defaults to `verbose`</li><li>filter - (optional) a string to filter the entries (by logger id or message) via `string.find` plain matching</li><li>caseSensitive - (optional) if true, filtering is case sensitive</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setGlobalLogLevel](#setgloballoglevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger.setGlobalLogLevel(lvl)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the log level for all logger instances (including objects' loggers)                                                                                         |
| **Parameters**                                       | <ul><li>lvl</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setModulesLogLevel](#setmodulesloglevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger.setModulesLogLevel(lvl)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the log level for all currently loaded modules                                                                                         |
| **Parameters**                                       | <ul><li>lvl</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>This function only affects *module*-level loggers, object instances with their own loggers (e.g. windowfilters) won't be affected;</li><li>   you can use `hs.logger.setGlobalLogLevel()` for those</li></ul>                |

### Fields

#### [level](#level)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger.level` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The log level of the logger instance, as a number between 0 and 5                                                                                         |

### Methods

#### [d](#d)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:d(...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs debug info to the console                                                                                         |
| **Parameters**                                       | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [df](#df)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:df(fmt,...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs formatted debug info to the console                                                                                         |
| **Parameters**                                       | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [e](#e)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:e(...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs an error to the console                                                                                         |
| **Parameters**                                       | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [ef](#ef)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:ef(fmt,...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs a formatted error to the console                                                                                         |
| **Parameters**                                       | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [f](#f)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:f(fmt,...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs formatted info to the console                                                                                         |
| **Parameters**                                       | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [getLogLevel](#getloglevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:getLogLevel() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the log level of the logger instance                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The log level of this logger as a number between 0 and 5</li></ul>          |

#### [i](#i)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:i(...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs info to the console                                                                                         |
| **Parameters**                                       | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setLogLevel](#setloglevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:setLogLevel(loglevel)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the log level of the logger instance                                                                                         |
| **Parameters**                                       | <ul><li>loglevel - can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose'; or a corresponding number between 0 and 5</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [v](#v)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:v(...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs verbose info to the console                                                                                         |
| **Parameters**                                       | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [vf](#vf)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:vf(fmt,...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs formatted verbose info to the console                                                                                         |
| **Parameters**                                       | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [w](#w)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:w(...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs a warning to the console                                                                                         |
| **Parameters**                                       | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [wf](#wf)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.logger:wf(fmt,...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Logs a formatted warning to the console                                                                                         |
| **Parameters**                                       | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

