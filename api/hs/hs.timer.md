# [docs](index.md) » hs.timer
---

Execute functions with various timing rules

## Submodules
 * [hs.timer.delayed](hs.timer.delayed.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [absolutetime](#absolutetime)
 * [days](#days)
 * [hours](#hours)
 * [localTime](#localtime)
 * [minutes](#minutes)
 * [seconds](#seconds)
 * [secondsSinceEpoch](#secondssinceepoch)
 * [usleep](#usleep)
 * [weeks](#weeks)
* Constructors - API calls which return an object, typically one that offers API methods
 * [doAfter](#doafter)
 * [doAt](#doat)
 * [doEvery](#doevery)
 * [doUntil](#dountil)
 * [doWhile](#dowhile)
 * [new](#new)
 * [waitUntil](#waituntil)
 * [waitWhile](#waitwhile)
* Methods - API calls which can only be made on an object returned by a constructor
 * [fire](#fire)
 * [nextTrigger](#nexttrigger)
 * [running](#running)
 * [setNextTrigger](#setnexttrigger)
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Functions

#### [absolutetime](#absolutetime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.absolutetime() -> nanoseconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the absolute time in nanoseconds since the last system boot.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the time since the last system boot in nanoseconds</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">this value does not include time that the system has spent asleep</li><li markdown="1">this value is used for the timestamps in system generated events.</li></ul>                |

#### [days](#days)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.days(n) -> sec` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts days to seconds                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">n - A number of days</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The number of seconds in n days</li></ul>          |

#### [hours](#hours)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.hours(n) -> seconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts hours to seconds                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">n - A number of hours</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The number of seconds in n hours</li></ul>          |

#### [localTime](#localtime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.localTime() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the number of seconds since local time midnight                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1"> None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1"> the number of seconds</li></ul>          |

#### [minutes](#minutes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.minutes(n) -> seconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts minutes to seconds                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">n - A number of minutes</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The number of seconds in n minutes</li></ul>          |

#### [seconds](#seconds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.seconds(timeOrDuration) -> seconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts a string with a time of day or a duration into number of seconds                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">timeOrDuration - a string that can have any of the following formats:</li><li markdown="1">  "HH:MM:SS" or "HH:MM" - represents a time of day (24-hour clock), returns the number of seconds since midnight</li><li markdown="1">  "DDdHHh", "HHhMMm", "MMmSSs", "DDd", "HHh", "MMm", "SSs", "NNNNms" - represents a duration in days, hours, minutes,</li><li markdown="1">     seconds and/or milliseconds</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The number of seconds</li></ul>          |

#### [secondsSinceEpoch](#secondssinceepoch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.secondsSinceEpoch() -> sec` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the (fractional) number of seconds since the UNIX epoch (January 1, 1970)                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The number of seconds since the epoch</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This has much better precision than `os.time()`, which is limited to whole seconds.</li></ul>                |

#### [usleep](#usleep)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.usleep(microsecs)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Blocks Lua execution for the specified time                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">microsecs - A number containing a time in microseconds to block for</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Use of this function is strongly discouraged, as it blocks all main-thread execution in Hammerspoon. This means no hotkeys or events will be processed in that time, no GUI updates will happen, and no Lua will execute. This is only provided as a last resort, or for extremely short sleeps. For all other purposes, you really should be splitting up your code into multiple functions and calling `hs.timer.doAfter()`</li></ul>                |

#### [weeks](#weeks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.weeks(n) -> sec` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts weeks to seconds                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">n - A number of weeks</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The number of seconds in n weeks</li></ul>          |

### Constructors

#### [doAfter](#doafter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doAfter(sec, fn) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Calls a function after a delay                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">sec - A number of seconds to wait before calling the function</li><li markdown="1">fn - A function to call</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `hs.timer` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">There is no need to call `:start()` on the returned object, the timer will be already running.</li><li markdown="1">The callback can be cancelled by calling the `:stop()` method on the returned object before `sec` seconds have passed.</li></ul>                |

#### [doAt](#doat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doAt(time[, repeatInterval], fn[, continueOnError]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `fn` at the given (local) `time` and then (optionally) repeat it every `interval`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">time - number of seconds after (local) midnight, or a string in the format "HH:MM" (24-hour local time), indicating</li><li markdown="1">   the desired trigger time</li><li markdown="1">repeatInterval - (optional) number of seconds between triggers, or a string in the format</li><li markdown="1">   "DDd", "DDdHHh", "HHhMMm", "HHh" or "MMm" indicating days, hours and/or minutes between triggers; if omitted</li><li markdown="1">   or `0` the timer will trigger only once</li><li markdown="1">fn - a function to call every time the timer triggers</li><li markdown="1">continueOnError - an optional boolean flag, defaulting to false, which indicates that the timer should not be automatically stopped if the callback function results in an error.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a timer object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The timer can trigger up to 1 second early or late</li><li markdown="1">The first trigger will be set to the earliest occurrence given the `repeatInterval`; if that's omitted,</li><li markdown="1">   and `time` is earlier than the current time, the timer will trigger the next day. If the repeated interval</li><li markdown="1">   results in exactly 24 hours you can schedule regular jobs that will run at the expected time independently</li><li markdown="1">   of when Hammerspoon was restarted/reloaded. E.g.:</li><li markdown="1">  If it's 19:00, `hs.timer.doAt("20:00",somefn)` will set the timer 1 hour from now</li><li markdown="1">  If it's 21:00, `hs.timer.doAt("20:00",somefn)` will set the timer 23 hours from now</li><li markdown="1">  If it's 21:00, `hs.timer.doAt("20:00","6h",somefn)` will set the timer 5 hours from now (at 02:00)</li><li markdown="1">  To run a job every hour on the hour from 8:00 to 20:00: `for h=8,20 do hs.timer.doAt(h..":00","1d",runJob) end`</li></ul>                |

#### [doEvery](#doevery)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doEvery(interval, fn) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Repeats fn every interval seconds.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">interval - A number of seconds between triggers</li><li markdown="1">fn - A function to call every time the timer triggers</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `hs.timer` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This function is a shorthand for `hs.timer.new(interval, fn):start()`</li></ul>                |

#### [doUntil](#dountil)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doUntil(predicateFn, actionFn[, checkInterval]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `actionFn` every `checkinterval` seconds until `predicateFn` returns true.  The timer is automatically stopped when `predicateFn` returns true.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">predicateFn - a function which determines when to stop calling `actionFn`.  This function takes no arguments, but should return true when it is time to stop calling `actionFn`.</li><li markdown="1">actionFn - a function which performs the desired action.  This function may take a single argument, the timer itself.</li><li markdown="1">checkInterval - an optional parameter indicating how often to repeat the `predicateFn` check. Defaults to 1 second.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a timer object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The timer is passed as an argument to `actionFn` so that it may stop the timer prematurely (i.e. before predicateFn returns true) if desired.</li><li markdown="1">See also `hs.timer.doWhile`, which is essentially the opposite of this function</li></ul>                |

#### [doWhile](#dowhile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doWhile(predicateFn, actionFn[, checkInterval]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `actionFn` every `checkinterval` seconds while `predicateFn` returns true.  The timer is automatically stopped when `predicateFn` returns false.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">predicateFn - a function which determines when to stop calling `actionFn`.  This function takes no arguments, but should return false when it is time to stop calling `actionFn`.</li><li markdown="1">actionFn - a function which performs the desired action.  This function may take a single argument, the timer itself.</li><li markdown="1">checkInterval - an optional parameter indicating how often to repeat the `predicateFn` check. Defaults to 1 second.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a timer object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The timer is passed as an argument to `actionFn` so that it may stop the timer prematurely (i.e. before predicateFn returns false) if desired.</li><li markdown="1">See also `hs.timer.doUntil`, which is essentially the opposite of this function</li></ul>                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.new(interval, fn [, continueOnError]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `hs.timer` object for repeating interval callbacks                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">interval - A number of seconds between firings of the timer</li><li markdown="1">fn - A function to call every time the timer fires</li><li markdown="1">continueOnError - An optional boolean, true if the timer should continue to be triggered after the callback function has produced an error, false if the timer should stop being triggered after the callback function has produced an error. Defaults to false.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An `hs.timer` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The returned object does not start its timer until its `:start()` method is called</li><li markdown="1">If `interval` is 0, the timer will not repeat (because if it did, it would be repeating as fast as your machine can manage, which seems generally unwise)</li><li markdown="1">For non-zero intervals, the lowest acceptable value for the interval is 0.00001s. Values >0 and <0.00001 will be coerced to 0.00001</li></ul>                |

#### [waitUntil](#waituntil)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.waitUntil(predicateFn, actionFn[, checkInterval]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `actionFn` when `predicateFn` returns true.  The timer is automatically stopped when `actionFn` is called.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">predicateFn - a function which determines when `actionFn` should be called.  This function takes no arguments, but should return true when it is time to call `actionFn`.</li><li markdown="1">actionFn - a function which performs the desired action.  This function may take a single argument, the timer itself.</li><li markdown="1">checkInterval - an optional parameter indicating how often to repeat the `predicateFn` check. Defaults to 1 second.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a timer object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The timer is stopped before `actionFn` is called, but the timer is passed as an argument to `actionFn` so that the actionFn may restart the timer to be called again the next time predicateFn returns true.</li><li markdown="1">See also `hs.timer.waitWhile`, which is essentially the opposite of this function</li></ul>                |

#### [waitWhile](#waitwhile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.waitWhile(predicateFn, actionFn[, checkInterval]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `actionFn` when `predicateFn` returns false.  The timer is automatically stopped when `actionFn` is called.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">predicateFn - a function which determines when `actionFn` should be called.  This function takes no arguments, but should return false when it is time to call `actionFn`.</li><li markdown="1">actionFn - a function which performs the desired action.  This function may take a single argument, the timer itself.</li><li markdown="1">checkInterval - an optional parameter indicating how often to repeat the `predicateFn` check. Defaults to 1 second.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">a timer object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The timer is stopped before `actionFn` is called, but the timer is passed as an argument to `actionFn` so that the actionFn may restart the timer to be called again the next time predicateFn returns false.</li><li markdown="1">See also `hs.timer.waitUntil`, which is essentially the opposite of this function</li></ul>                |

### Methods

#### [fire](#fire)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:fire() -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Immediately fires a timer                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `hs.timer` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This cannot be used on a timer which has already stopped running</li></ul>                |

#### [nextTrigger](#nexttrigger)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:nextTrigger() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the number of seconds until the timer will next trigger                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A number containing the number of seconds until the next firing</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The return value may be a negative integer in two circumstances:</li><li markdown="1"> Hammerspoon's runloop is backlogged and is catching up on missed timer triggers</li><li markdown="1"> The timer object is not currently running. In this case, the return value of this method is the number of seconds since the last firing (you can check if the timer is running or not, with `hs.timer:running()`</li></ul>                |

#### [running](#running)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:running() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a boolean indicating whether or not the timer is currently running.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A boolean value indicating whether or not the timer is currently running.</li></ul>          |

#### [setNextTrigger](#setnexttrigger)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:setNextTrigger(seconds) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the next trigger time of a timer                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">seconds - A number of seconds after which to trigger the timer</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `hs.timer` object, or nil if an error occurred</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">If the timer is not already running, this will start it</li></ul>                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:start() -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts an `hs.timer` object                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `hs.timer` object</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The timer will not call the callback immediately, the timer will wait until it fires</li><li markdown="1">If the callback function results in an error, the timer will be stopped to prevent repeated error notifications (see the `continueOnError` parameter to `hs.timer.new()` to override this)</li></ul>                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:stop() -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops an `hs.timer` object                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `hs.timer` object</li></ul>          |

