# [docs](index.md) » hs.logger
---

Simple logger for debugging purposes

Note: "methods" in this module are actually "static" functions - see `hs.logger.new()`

## API Overview
* Variables - Configurable values
* [defaultLogLevel](#defaultLogLevel)
* Functions - API calls offered directly by the extension
* [history](#history)
* [historySize](#historySize)
* [new](#new)
* [printHistory](#printHistory)
* [setGlobalLogLevel](#setGlobalLogLevel)
* [setModulesLogLevel](#setModulesLogLevel)
* Fields - Variables which can only be access from an object returned by a constructor
* [level](#level)
* Methods - API calls which can only be made on an object returned by a constructor
* [d](#d)
* [df](#df)
* [e](#e)
* [ef](#ef)
* [f](#f)
* [getLogLevel](#getLogLevel)
* [i](#i)
* [setLogLevel](#setLogLevel)
* [v](#v)
* [vf](#vf)
* [w](#w)
* [wf](#wf)

## API Documentation

### Variables

#### [defaultLogLevel](#defaultLogLevel)
| Signature   | hs.logger.defaultLogLevel  |
| Type        | Variable |
| Description | Default log level for new logger instances. |
  The starting value is 'warning'; set this (to e.g. 'info') at the top of your `init.lua` to affect
    all logger instances created without specifying a `loglevel` parameter

### Functions

#### [history](#history)
| Signature   | hs.logger.history() -> list of log entries  |
| Type        | Function |
| Description | Returns the global log history |
| Parameters |  * None | | Returns |  * a list of (at most `hs.logger.historySize()`) log entries produced by all the logger instances, in chronological order;   each entry is a table with the following fields:   * time - timestamp in seconds since the epoch   * level - a number between 1 (error) and 5 (verbose)   * id - a string containing the id of the logger instance that produced this entry   * message - a string containing the logged message | 
#### [historySize](#historySize)
| Signature   | hs.logger.historySize([size]) -> number  |
| Type        | Function |
| Description | Sets or gets the global log history size |
| Parameters |  * size - (optional) the desired number of log entries to keep in the history;   if omitted, will return the current size; the starting value is 0 (disabled) | | Returns |  * the current or new history size | | Notes |  * if you change history size (other than from 0) after creating any logger instances, things will likely break | 
#### [new](#new)
| Signature   | hs.logger.new(id, loglevel) -> logger  |
| Type        | Function |
| Description | Creates a new logger instance |
  Example:
    ```lua
    local log = hs.logger.new('mymodule','debug')
    log.i('Initializing') -- will print "[mymodule] Initializing" to the console
    ```
| Parameters |  * id - a string identifier for the instance (usually the module name) * loglevel - (optional) can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose', or a corresponding number   between 0 and 5; uses `hs.logger.defaultLogLevel` if omitted | | Returns |  * the new logger instance | | Notes |  * the logger instance created by this method is not a regular object, but a plain table with "static" functions;   therefore, do not use the colon syntax for so-called "methods" in this module (as in `mylogger:setLogLevel(3)`);   you must instead use the regular dot syntax: `mylogger.setLogLevel(3)` | 
#### [printHistory](#printHistory)
| Signature   | hs.logger.printHistory([entries[, level[, filter[, caseSensitive]]]])  |
| Type        | Function |
| Description | Prints the global log history to the console |
| Parameters |  * entries - (optional) the maximum number of entries to print; if omitted, all entries in the history will be printed * level - (optional) the desired log level (see `hs.logger:setLogLevel()`); if omitted, defaults to `verbose` * filter - (optional) a string to filter the entries (by logger id or message) via `string.find` plain matching * caseSensitive - (optional) if true, filtering is case sensitive | | Returns |  * None | 
#### [setGlobalLogLevel](#setGlobalLogLevel)
| Signature   | hs.logger.setGlobalLogLevel(lvl)  |
| Type        | Function |
| Description | Sets the log level for all logger instances (including objects' loggers) |
| Parameters |  * lvl | | Returns |  * None | 
#### [setModulesLogLevel](#setModulesLogLevel)
| Signature   | hs.logger.setModulesLogLevel(lvl)  |
| Type        | Function |
| Description | Sets the log level for all currently loaded modules |
| Parameters |  * lvl | | Returns |  * None | | Notes |  * This function only affects *module*-level loggers, object instances with their own loggers (e.g. windowfilters) won't be affected;   you can use `hs.logger.setGlobalLogLevel()` for those | 
### Fields

#### [level](#level)
| Signature   | hs.logger.level  |
| Type        | Field |
| Description | The log level of the logger instance, as a number between 0 and 5 |

### Methods

#### [d](#d)
| Signature   | hs.logger:d(...)  |
| Type        | Method |
| Description | Logs debug info to the console |
| Parameters |  * ... - one or more message strings | | Returns |  * None | 
#### [df](#df)
| Signature   | hs.logger:df(fmt,...)  |
| Type        | Method |
| Description | Logs formatted debug info to the console |
| Parameters |  * fmt - formatting string as per string.format * ... - arguments to fmt | | Returns |  * None | 
#### [e](#e)
| Signature   | hs.logger:e(...)  |
| Type        | Method |
| Description | Logs an error to the console |
| Parameters |  * ... - one or more message strings | | Returns |  * None | 
#### [ef](#ef)
| Signature   | hs.logger:ef(fmt,...)  |
| Type        | Method |
| Description | Logs a formatted error to the console |
| Parameters |  * fmt - formatting string as per string.format * ... - arguments to fmt | | Returns |  * None | 
#### [f](#f)
| Signature   | hs.logger:f(fmt,...)  |
| Type        | Method |
| Description | Logs formatted info to the console |
| Parameters |  * fmt - formatting string as per string.format * ... - arguments to fmt | | Returns |  * None | 
#### [getLogLevel](#getLogLevel)
| Signature   | hs.logger:getLogLevel() -> number  |
| Type        | Method |
| Description | Gets the log level of the logger instance |
| Parameters |  * None | | Returns |  * The log level of this logger as a number between 0 and 5 | 
#### [i](#i)
| Signature   | hs.logger:i(...)  |
| Type        | Method |
| Description | Logs info to the console |
| Parameters |  * ... - one or more message strings | | Returns |  * None | 
#### [setLogLevel](#setLogLevel)
| Signature   | hs.logger:setLogLevel(loglevel)  |
| Type        | Method |
| Description | Sets the log level of the logger instance |
| Parameters |  * loglevel - can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose'; or a corresponding number between 0 and 5 | | Returns |  * None | 
#### [v](#v)
| Signature   | hs.logger:v(...)  |
| Type        | Method |
| Description | Logs verbose info to the console |
| Parameters |  * ... - one or more message strings | | Returns |  * None | 
#### [vf](#vf)
| Signature   | hs.logger:vf(fmt,...)  |
| Type        | Method |
| Description | Logs formatted verbose info to the console |
| Parameters |  * fmt - formatting string as per string.format * ... - arguments to fmt | | Returns |  * None | 
#### [w](#w)
| Signature   | hs.logger:w(...)  |
| Type        | Method |
| Description | Logs a warning to the console |
| Parameters |  * ... - one or more message strings | | Returns |  * None | 
#### [wf](#wf)
| Signature   | hs.logger:wf(fmt,...)  |
| Type        | Method |
| Description | Logs a formatted warning to the console |
| Parameters |  * fmt - formatting string as per string.format * ... - arguments to fmt | | Returns |  * None | 