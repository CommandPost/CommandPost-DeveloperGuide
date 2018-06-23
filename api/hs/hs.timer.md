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
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>the time since the last system boot in nanoseconds</li></ul>            |
| **Notes**                                            | <ul><li>this value does not include time that the system has spent asleep</li></ul><ul><li>this value is used for the timestamps in system generated events.</li></ul>                 |

#### [days](#days)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.days(n) -> sec` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts days to seconds                                                                                         |
| **Parameters**                                       | <ul><li>n - A number of days</li></ul>   |
| **Returns**                                          | <ul><li>The number of seconds in n days</li></ul>            |

#### [hours](#hours)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.hours(n) -> seconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts hours to seconds                                                                                         |
| **Parameters**                                       | <ul><li>n - A number of hours</li></ul>   |
| **Returns**                                          | <ul><li>The number of seconds in n hours</li></ul>            |

#### [localTime](#localtime)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.localTime() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the number of seconds since local time midnight                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>the number of seconds</li></ul>            |

#### [minutes](#minutes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.minutes(n) -> seconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts minutes to seconds                                                                                         |
| **Parameters**                                       | <ul><li>n - A number of minutes</li></ul>   |
| **Returns**                                          | <ul><li>The number of seconds in n minutes</li></ul>            |

#### [seconds](#seconds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.seconds(timeOrDuration) -> seconds` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts a string with a time of day or a duration into number of seconds                                                                                         |
| **Parameters**                                       | <ul><li>timeOrDuration - a string that can have any of the following formats:</li></ul><ul><li>"HH:MM:SS" or "HH:MM" - represents a time of day (24-hour clock), returns the number of seconds since midnight</li></ul><ul><li>"DDdHHh", "HHhMMm", "MMmSSs", "DDd", "HHh", "MMm", "SSs", "NNNNms" - represents a duration in days, hours, minutes,</li></ul><pre><code> seconds and/or milliseconds</code></pre>   |
| **Returns**                                          | <ul><li>The number of seconds</li></ul>            |

#### [secondsSinceEpoch](#secondssinceepoch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.secondsSinceEpoch() -> sec` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the (fractional) number of seconds since the UNIX epoch (January 1, 1970)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The number of seconds since the epoch</li></ul>            |
| **Notes**                                            | <ul><li>This has much better precision than <code>os.time()</code>, which is limited to whole seconds.</li></ul>                 |

#### [usleep](#usleep)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.usleep(microsecs)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Blocks Lua execution for the specified time                                                                                         |
| **Parameters**                                       | <ul><li>microsecs - A number containing a time in microseconds to block for</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |
| **Notes**                                            | <ul><li>Use of this function is strongly discouraged, as it blocks all main-thread execution in Hammerspoon. This means no hotkeys or events will be processed in that time, no GUI updates will happen, and no Lua will execute. This is only provided as a last resort, or for extremely short sleeps. For all other purposes, you really should be splitting up your code into multiple functions and calling <code>hs.timer.doAfter()</code></li></ul>                 |

#### [weeks](#weeks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.weeks(n) -> sec` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts weeks to seconds                                                                                         |
| **Parameters**                                       | <ul><li>n - A number of weeks</li></ul>   |
| **Returns**                                          | <ul><li>The number of seconds in n weeks</li></ul>            |

### Constructors

#### [doAfter](#doafter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doAfter(sec, fn) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Calls a function after a delay                                                                                         |
| **Parameters**                                       | <ul><li>sec - A number of seconds to wait before calling the function</li></ul><ul><li>fn - A function to call</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.timer</code> object</li></ul>            |
| **Notes**                                            | <ul><li>There is no need to call <code>:start()</code> on the returned object, the timer will be already running.</li></ul><ul><li>The callback can be cancelled by calling the <code>:stop()</code> method on the returned object before <code>sec</code> seconds have passed.</li></ul>                 |

#### [doAt](#doat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doAt(time[, repeatInterval], fn[, continueOnError]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `fn` at the given (local) `time` and then (optionally) repeat it every `interval`.                                                                                         |
| **Parameters**                                       | <ul><li>time - number of seconds after (local) midnight, or a string in the format "HH:MM" (24-hour local time), indicating</li></ul><p>the desired trigger time</p><ul><li>repeatInterval - (optional) number of seconds between triggers, or a string in the format</li></ul><p>"DDd", "DDdHHh", "HHhMMm", "HHh" or "MMm" indicating days, hours and/or minutes between triggers; if omitted</p><p>or <code>0</code> the timer will trigger only once</p><ul><li>fn - a function to call every time the timer triggers</li></ul><ul><li>continueOnError - an optional boolean flag, defaulting to false, which indicates that the timer should not be automatically stopped if the callback function results in an error.</li></ul>   |
| **Returns**                                          | <ul><li>a timer object</li></ul>            |
| **Notes**                                            | <ul><li>The timer can trigger up to 1 second early or late</li></ul><ul><li>The first trigger will be set to the earliest occurrence given the <code>repeatInterval</code>; if that's omitted,</li></ul><p>and <code>time</code> is earlier than the current time, the timer will trigger the next day. If the repeated interval</p><p>results in exactly 24 hours you can schedule regular jobs that will run at the expected time independently</p><p>of when Hammerspoon was restarted/reloaded. E.g.:</p><ul><li>If it's 19:00, <code>hs.timer.doAt("20:00",somefn)</code> will set the timer 1 hour from now</li></ul><ul><li>If it's 21:00, <code>hs.timer.doAt("20:00",somefn)</code> will set the timer 23 hours from now</li></ul><ul><li>If it's 21:00, <code>hs.timer.doAt("20:00","6h",somefn)</code> will set the timer 5 hours from now (at 02:00)</li></ul><ul><li>To run a job every hour on the hour from 8:00 to 20:00: <code>for h=8,20 do hs.timer.doAt(h..":00","1d",runJob) end</code></li></ul>                 |

#### [doEvery](#doevery)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doEvery(interval, fn) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Repeats fn every interval seconds.                                                                                         |
| **Parameters**                                       | <ul><li>interval - A number of seconds between triggers</li></ul><ul><li>fn - A function to call every time the timer triggers</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.timer</code> object</li></ul>            |
| **Notes**                                            | <ul><li>This function is a shorthand for <code>hs.timer.new(interval, fn):start()</code></li></ul>                 |

#### [doUntil](#dountil)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doUntil(predicateFn, actionFn[, checkInterval]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `actionFn` every `checkinterval` seconds until `predicateFn` returns true.  The timer is automatically stopped when `predicateFn` returns true.                                                                                         |
| **Parameters**                                       | <ul><li>predicateFn - a function which determines when to stop calling <code>actionFn</code>.  This function takes no arguments, but should return true when it is time to stop calling <code>actionFn</code>.</li></ul><ul><li>actionFn - a function which performs the desired action.  This function may take a single argument, the timer itself.</li></ul><ul><li>checkInterval - an optional parameter indicating how often to repeat the <code>predicateFn</code> check. Defaults to 1 second.</li></ul>   |
| **Returns**                                          | <ul><li>a timer object</li></ul>            |
| **Notes**                                            | <ul><li>The timer is passed as an argument to <code>actionFn</code> so that it may stop the timer prematurely (i.e. before predicateFn returns true) if desired.</li></ul><ul><li>See also <code>hs.timer.doWhile</code>, which is essentially the opposite of this function</li></ul>                 |

#### [doWhile](#dowhile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.doWhile(predicateFn, actionFn[, checkInterval]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `actionFn` every `checkinterval` seconds while `predicateFn` returns true.  The timer is automatically stopped when `predicateFn` returns false.                                                                                         |
| **Parameters**                                       | <ul><li>predicateFn - a function which determines when to stop calling <code>actionFn</code>.  This function takes no arguments, but should return false when it is time to stop calling <code>actionFn</code>.</li></ul><ul><li>actionFn - a function which performs the desired action.  This function may take a single argument, the timer itself.</li></ul><ul><li>checkInterval - an optional parameter indicating how often to repeat the <code>predicateFn</code> check. Defaults to 1 second.</li></ul>   |
| **Returns**                                          | <ul><li>a timer object</li></ul>            |
| **Notes**                                            | <ul><li>The timer is passed as an argument to <code>actionFn</code> so that it may stop the timer prematurely (i.e. before predicateFn returns false) if desired.</li></ul><ul><li>See also <code>hs.timer.doUntil</code>, which is essentially the opposite of this function</li></ul>                 |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.new(interval, fn [, continueOnError]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `hs.timer` object for repeating interval callbacks                                                                                         |
| **Parameters**                                       | <ul><li>interval - A number of seconds between firings of the timer</li></ul><ul><li>fn - A function to call every time the timer fires</li></ul><ul><li>continueOnError - An optional boolean, true if the timer should continue to be triggered after the callback function has produced an error, false if the timer should stop being triggered after the callback function has produced an error. Defaults to false.</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.timer</code> object</li></ul>            |
| **Notes**                                            | <ul><li>The returned object does not start its timer until its <code>:start()</code> method is called</li></ul><ul><li>If <code>interval</code> is 0, the timer will not repeat (because if it did, it would be repeating as fast as your machine can manage, which seems generally unwise)</li></ul><ul><li>For non-zero intervals, the lowest acceptable value for the interval is 0.00001s. Values &gt;0 and &lt;0.00001 will be coerced to 0.00001</li></ul>                 |

#### [waitUntil](#waituntil)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.waitUntil(predicateFn, actionFn[, checkInterval]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `actionFn` when `predicateFn` returns true.  The timer is automatically stopped when `actionFn` is called.                                                                                         |
| **Parameters**                                       | <ul><li>predicateFn - a function which determines when <code>actionFn</code> should be called.  This function takes no arguments, but should return true when it is time to call <code>actionFn</code>.</li></ul><ul><li>actionFn - a function which performs the desired action.  This function may take a single argument, the timer itself.</li></ul><ul><li>checkInterval - an optional parameter indicating how often to repeat the <code>predicateFn</code> check. Defaults to 1 second.</li></ul>   |
| **Returns**                                          | <ul><li>a timer object</li></ul>            |
| **Notes**                                            | <ul><li>The timer is stopped before <code>actionFn</code> is called, but the timer is passed as an argument to <code>actionFn</code> so that the actionFn may restart the timer to be called again the next time predicateFn returns true.</li></ul><ul><li>See also <code>hs.timer.waitWhile</code>, which is essentially the opposite of this function</li></ul>                 |

#### [waitWhile](#waitwhile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer.waitWhile(predicateFn, actionFn[, checkInterval]) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates and starts a timer which will perform `actionFn` when `predicateFn` returns false.  The timer is automatically stopped when `actionFn` is called.                                                                                         |
| **Parameters**                                       | <ul><li>predicateFn - a function which determines when <code>actionFn</code> should be called.  This function takes no arguments, but should return false when it is time to call <code>actionFn</code>.</li></ul><ul><li>actionFn - a function which performs the desired action.  This function may take a single argument, the timer itself.</li></ul><ul><li>checkInterval - an optional parameter indicating how often to repeat the <code>predicateFn</code> check. Defaults to 1 second.</li></ul>   |
| **Returns**                                          | <ul><li>a timer object</li></ul>            |
| **Notes**                                            | <ul><li>The timer is stopped before <code>actionFn</code> is called, but the timer is passed as an argument to <code>actionFn</code> so that the actionFn may restart the timer to be called again the next time predicateFn returns false.</li></ul><ul><li>See also <code>hs.timer.waitUntil</code>, which is essentially the opposite of this function</li></ul>                 |

### Methods

#### [fire](#fire)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:fire() -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Immediately fires a timer                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.timer</code> object</li></ul>            |
| **Notes**                                            | <ul><li>This cannot be used on a timer which has already stopped running</li></ul>                 |

#### [nextTrigger](#nexttrigger)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:nextTrigger() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the number of seconds until the timer will next trigger                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the number of seconds until the next firing</li></ul>            |
| **Notes**                                            | <ul><li>The return value may be a negative integer in two circumstances:</li></ul><ul><li>Hammerspoon's runloop is backlogged and is catching up on missed timer triggers</li></ul><ul><li>The timer object is not currently running. In this case, the return value of this method is the number of seconds since the last firing (you can check if the timer is running or not, with <code>hs.timer:running()</code></li></ul>                 |

#### [running](#running)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:running() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a boolean indicating whether or not the timer is currently running.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A boolean value indicating whether or not the timer is currently running.</li></ul>            |

#### [setNextTrigger](#setnexttrigger)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:setNextTrigger(seconds) -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the next trigger time of a timer                                                                                         |
| **Parameters**                                       | <ul><li>seconds - A number of seconds after which to trigger the timer</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.timer</code> object, or nil if an error occurred</li></ul>            |
| **Notes**                                            | <ul><li>If the timer is not already running, this will start it</li></ul>                 |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:start() -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts an `hs.timer` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.timer</code> object</li></ul>            |
| **Notes**                                            | <ul><li>The timer will not call the callback immediately, the timer will wait until it fires</li></ul><ul><li>If the callback function results in an error, the timer will be stopped to prevent repeated error notifications (see the <code>continueOnError</code> parameter to <code>hs.timer.new()</code> to override this)</li></ul>                 |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.timer:stop() -> timer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops an `hs.timer` object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>hs.timer</code> object</li></ul>            |

