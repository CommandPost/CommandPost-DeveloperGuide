# [docs](index.md) » cp.rx.Observable
---

Observables push values to [Observers](cp.rx.Observer.md).

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [create](#create)
 * [defer](#defer)
 * [empty](#empty)
 * [firstEmitting](#firstemitting)
 * [fromCoroutine](#fromcoroutine)
 * [fromFileByLine](#fromfilebyline)
 * [fromRange](#fromrange)
 * [fromTable](#fromtable)
 * [never](#never)
 * [of](#of)
 * [replicate](#replicate)
 * [throw](#throw)
 * [zip](#zip)
* Methods - API calls which can only be made on an object returned by a constructor
 * [all](#all)
 * [average](#average)
 * [buffer](#buffer)
 * [catch](#catch)
 * [combineLatest](#combinelatest)
 * [compact](#compact)
 * [concat](#concat)
 * [contains](#contains)
 * [count](#count)
 * [debounce](#debounce)
 * [defaultIfEmpty](#defaultifempty)
 * [delay](#delay)
 * [distinct](#distinct)
 * [distinctUntilChanged](#distinctuntilchanged)
 * [dump](#dump)
 * [elementAt](#elementat)
 * [filter](#filter)
 * [finalize](#finalize)
 * [find](#find)
 * [first](#first)
 * [flatMap](#flatmap)
 * [flatMapLatest](#flatmaplatest)
 * [flatten](#flatten)
 * [ignoreElements](#ignoreelements)
 * [last](#last)
 * [map](#map)
 * [max](#max)
 * [merge](#merge)
 * [min](#min)
 * [next](#next)
 * [partition](#partition)
 * [pluck](#pluck)
 * [reduce](#reduce)
 * [reject](#reject)
 * [retry](#retry)
 * [retryWithDelay](#retrywithdelay)
 * [sample](#sample)
 * [scan](#scan)
 * [skip](#skip)
 * [skipLast](#skiplast)
 * [skipUntil](#skipuntil)
 * [skipWhile](#skipwhile)
 * [startWith](#startwith)
 * [subscribe](#subscribe)
 * [sum](#sum)
 * [switch](#switch)
 * [switchIfEmpty](#switchifempty)
 * [take](#take)
 * [takeLast](#takelast)
 * [takeUntil](#takeuntil)
 * [takeWhile](#takewhile)
 * [tap](#tap)
 * [timeout](#timeout)
 * [unpack](#unpack)
 * [unwrap](#unwrap)
 * [with](#with)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the thing is an instance of [Observable](cp.rx.Observable.md). |
| **Parameters**                                       | <ul><li>thing   - The thing to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the thing is an <code>Observable</code>.</li></ul> |

### Constructors

#### [create](#create)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.create(onSubscription) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Observable. |
| **Parameters**                                       | <ul><li>onSubscription  - The reference function that produces values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [defer](#defer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.defer(fn) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an `Observable` that executes the `function` to create a new `Observable` each time an [Observer](cp.rx.Observer.md) subscribes. |
| **Parameters**                                       | <ul><li>fn    - A function that returns an <code>Observable</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [empty](#empty)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.empty() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns an Observable that immediately completes without producing a value. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [firstEmitting](#firstemitting)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.firstEmitting(...) -> cp.rx.Observer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Given a set of Observables, produces values from only the first one to produce a value or complete. |
| **Parameters**                                       | <ul><li>...   - list of <a href="cp.rx.Observable.md">Observables</a></li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [fromCoroutine](#fromcoroutine)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.fromCoroutine(fn, scheduler) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an Observable that produces values when the specified coroutine yields. |
| **Parameters**                                       | <ul><li>fn - A <code>coroutine</code> or <code>function</code> to use to generate values.  Note that if a coroutine is used, the values it yields will be shared by all subscribed <a href="cp.rx.Observer.md">Observers</a> (influenced by the <a href="cp.rx.Scheduler.md">Scheduler</a>), whereas a new coroutine will be created for each Observer when a <code>function</code> is used.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [fromFileByLine](#fromfilebyline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.fromFileByLine(filename) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an Observable that produces values from a file, line by line. |
| **Parameters**                                       | <ul><li>filename    - The name of the file used to create the Observable.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [fromRange](#fromrange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.fromRange(initial[, limit[, step]]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an Observable that produces a range of values in a manner similar to a Lua `for` loop. |
| **Parameters**                                       | <ul><li>initial   - The first value of the range, or the upper limit if no other arguments are specified.</li><li>limit     - The second value of the range. Defaults to no limit.</li><li>step      - An amount to increment the value by each iteration. Defaults to <code>1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [fromTable](#fromtable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.fromTable(t, iterator, keys) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an `Observable` that produces values from a table. |
| **Parameters**                                       | <ul><li>t         - The <code>table</code> used to create the <code>Observable</code>.</li><li>iterator  - An iterator used to iterate the table, e.g. <code>pairs</code> or <code>ipairs</code>. Defaults to <code>pairs</code>.</li><li>keys      - If <code>true</code>, also emit the keys of the table. Defaults to <code>false</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [never](#never)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.never() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns an Observable that never produces values and never completes. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [of](#of)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.of(...) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an Observable that produces a set of values. |
| **Parameters**                                       | <ul><li>...     - The list of values to send as individual <code>onNext</code> values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [replicate](#replicate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.replicate(value[, count]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates an `Observable` that repeats a value a specified number of times. |
| **Parameters**                                       | <ul><li>value     - The value to repeat.</li><li>count     - The number of times to repeat the value.  If left unspecified, the value                       is repeated an infinite number of times.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [throw](#throw)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.throw(message, ...) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns an Observable that immediately produces an error. |
| **Parameters**                                       | <ul><li>message   - The message to send.</li><li>...       - The additional values to apply to the message, using <code>string.format</code> syntax.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [zip](#zip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable.zip(...) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns an `Observable` that merges the values produced by the source `Observables` by grouping them |
| **Parameters**                                       | <ul><li>...       - The <code>Observables</code> to zip.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

### Methods

#### [all](#all)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:all(predicate) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Determine whether all items emitted by an Observable meet some criteria. |
| **Parameters**                                       | <ul><li>predicate - The predicate used to evaluate objects. Defaults to the <code>identity</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Observable</code>.</li></ul> |

#### [average](#average)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:average() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an Observable that produces the average of all values produced by the original. |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [buffer](#buffer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:buffer(size) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an Observable that buffers values from the original and produces them as multiple values. |
| **Parameters**                                       | <ul><li>size    - The size of the buffer.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [catch](#catch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:catch(handler) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an Observable that intercepts any errors from the previous and replace them with values |
| **Parameters**                                       | <ul><li>handler - An <code>Observable</code> or a <code>function</code> that returns an <code>Observable</code> to            replace the source <code>Observable</code> in the event of an error.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [combineLatest](#combinelatest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:combineLatest(...) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that runs a combinator function on the most recent values from a set |
| **Parameters**                                       | <ul><li>...         - One or more <code>Observables</code> to combine.</li><li>combinator  - A <code>function</code> that combines the latest result from each <code>Observable</code> and                             returns a single value.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [compact](#compact)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:compact() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the values of the first with falsy values removed. |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [concat](#concat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:concat(...) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the values produced by all the specified `Observables` in |
| **Parameters**                                       | <ul><li>...     - The list of <code>Observables</code> to concatenate.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [contains](#contains)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:contains(value) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces a single `boolean` value representing whether or not the |
| **Parameters**                                       | <ul><li>value       - The value to search for.  <code>==</code> is used for equality testing.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [count](#count)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:count([predicate]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that produces a single value representing the number of values produced |
| **Parameters**                                       | <ul><li>predicate   - The predicate <code>function</code> used to match values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [debounce](#debounce)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:debounce(time[, scheduler]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that mirrors the source `Observable`, except that it drops items emitted by the source |
| **Parameters**                                       | <ul><li>time        - The number of milliseconds.</li><li>scheduler   - The scheduler. Uses the <a href="cp.rx.util#defaultScheduler">defaultScheduler</a> by default.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [defaultIfEmpty](#defaultifempty)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:defaultIfEmpty(...)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces a default set of items if the source `Observable` produces |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [delay](#delay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:delay(time, scheduler) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the values of the original delayed by a time period. |
| **Parameters**                                       | <ul><li>time      - An amount in milliseconds to delay by, or a <code>function</code> which returns              this value.</li><li>scheduler - The <a href="cp.rx.Scheduler.md">Scheduler</a> to run the <code>Observable</code> on.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [distinct](#distinct)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:distinct() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the values from the original with duplicates removed. |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [distinctUntilChanged](#distinctuntilchanged)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:distinctUntilChanged([comparator]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that only produces values from the original if they are different from |
| **Parameters**                                       | <ul><li>comparator    - A <code>function</code> used to compare 2 values. If unspecified, <code>==</code> is used.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code></li></ul> |

#### [dump](#dump)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:dump(name, formatter)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Subscribes to this Observable and prints values it produces. |
| **Parameters**                                       | <ul><li>name      - Prefixes the printed messages with a name.</li><li>formatter - A function that formats one or more values to be printed. Defaults to <code>tostring</code>.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.Reference.md">Reference</a> for the subscription.</li></ul> |

#### [elementAt](#elementat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:elementAt(index) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that produces the `n`th element produced by the source `Observable`. |
| **Parameters**                                       | <ul><li>index     - The index of the item, with an index of <code>1</code> representing the first.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [filter](#filter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:filter(predicate) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that only produces values of the first that satisfy a predicate. |
| **Parameters**                                       | <ul><li>predicate - The predicate <code>function</code> used to filter values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [finalize](#finalize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:finalize(handler) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that mirrors the source `Observable`, but will call a specified `function` |
| **Parameters**                                       | <ul><li>handler   - The handler <code>function</code> to call when <code>onError</code>/<code>onCompleted</code> occurs.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:find(predicate) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the first value of the original that satisfies a |
| **Parameters**                                       | <ul><li>predicate   - The predicate <code>function</code> used to find a value.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [first](#first)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:first() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that only produces the first result of the original. |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [flatMap](#flatmap)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:flatMap(callback) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that transform the items emitted by an `Observable` into `Observables`, |
| **Parameters**                                       | <ul><li>callback - The <code>function</code> to transform values from the original <code>Observable</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [flatMapLatest](#flatmaplatest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:flatMapLatest([callback]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that uses a callback to create `Observables` from the values produced by |
| **Parameters**                                       | <p>@arg {function=identity} callback - The function used to convert values to Observables. Defaults to the <a href="cp.rx.util#identity">identity</a> function.</p> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [flatten](#flatten)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:flatten()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that subscribes to the `Observables` produced by the original and |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [ignoreElements](#ignoreelements)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:ignoreElements() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that terminates when the source terminates but does not produce any |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [last](#last)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:last() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that only produces the last result of the original. |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [map](#map)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:map(callback) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the values of the original transformed by a `function`. |
| **Parameters**                                       | <ul><li>callback    - The <code>function</code> to transform values from the original <code>Observable</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [max](#max)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:max() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the maximum value produced by the original. |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [merge](#merge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:merge(...) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the values produced by all the specified `Observables` in |
| **Parameters**                                       | <ul><li>...       - One or more <code>Observables</code> to merge.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [min](#min)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:min() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the minimum value produced by the original. |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:next() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces at most the first result from the original and then completes. |

#### [partition](#partition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:partition(predicate) -> cp.rx.Observable, cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns two `Observables`: one that produces values for which the predicate returns truthy for, |
| **Parameters**                                       | <ul><li>predicate   - The predicate <code>function</code> used to partition the values.</li></ul> |
| **Returns**                                          | <ul><li>The 'truthy' <code>Observable</code>.</li><li>The 'falsy' <code>Observable</code>.</li></ul> |

#### [pluck](#pluck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:pluck(...) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces values computed by extracting the given keys from the |
| **Parameters**                                       | <ul><li>...       - The key to extract from the <code>table</code>. Multiple keys can be specified to              recursively pluck values from nested tables.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [reduce](#reduce)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:reduce(accumulator[, seed]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces a single value computed by accumulating the results of |
| **Parameters**                                       | <ul><li>accumulator - Accumulates the values of the original <code>Observable</code>. Will be passed                the return value of the last call as the first argument and the                current values as the rest of the arguments.</li><li>seed        - A value to pass to the accumulator the first time it is run.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [reject](#reject)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:reject(predicate) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces values from the original which do not satisfy a predicate. |
| **Parameters**                                       | <ul><li>predicate     - The predicate <code>function</code> used to reject values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [retry](#retry)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:retry([count]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that restarts in the event of an error. |
| **Parameters**                                       | <ul><li>count     - The maximum number of times to retry.  If left unspecified, an infinite              number of retries will be attempted.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [retryWithDelay](#retrywithdelay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:retryWithDelay(count[, delay[, scheduler]]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that restarts in the event of an error. |
| **Parameters**                                       | <ul><li>count     - The maximum number of times to retry.  If left unspecified, an infinite              number of retries will be attempted.</li><li>delay     - The <code>function</code> returning or a <code>number</code> representing the delay in milliseconds or a <code>function</code>. If left unspecified, defaults to 1000 ms (1 second).</li><li>scheduler - The <a href="cp.rx.Scheduler.md">Scheduler</a> to use.              If not specified, it will use the [defaultScheduler](cp.rx.util#defaultScheduler].</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [sample](#sample)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:sample(sampler) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces its most recent value every time the specified observable |
| **Parameters**                                       | <ul><li>sampler     - The <code>Observable</code> that is used to sample values from this <code>Observable</code>.</li></ul> |

#### [scan](#scan)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:scan(accumulator, seed) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces values computed by accumulating the results of running a |
| **Parameters**                                       | <ul><li>accumulator     - Accumulates the values of the original <code>Observable</code>. Will be passed                    the return value of the last call as the first argument and the                    current values as the rest of the arguments.  Each value returned                    from this <code>function</code> will be emitted by the <code>Observable</code>.</li><li>seed            - A value to pass to the accumulator the first time it is run.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [skip](#skip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:skip([n]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that skips over a specified number of values produced by the original |
| **Parameters**                                       | <ul><li>n       - The number of values to ignore. Defaults to <code>1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code></li></ul> |

#### [skipLast](#skiplast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:skipLast(count) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that omits a specified number of values from the end of the original `Observable`. |
| **Parameters**                                       | <ul><li>count     - The number of items to omit from the end.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [skipUntil](#skipuntil)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:skipUntil(other) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that skips over values produced by the original until the specified |
| **Parameters**                                       | <ul><li>other     - The <code>Observable</code> that triggers the production of values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [skipWhile](#skipwhile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:skipWhile(predicate) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that skips elements until the predicate returns `falsy` for one of them. |
| **Parameters**                                       | <ul><li>predicate     - The predicate <code>function</code> used to continue skipping values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [startWith](#startwith)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:startWith(...) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces the specified values followed by all elements produced by |
| **Parameters**                                       | <ul><li>values    - The values to produce before the Observable begins producing values normally.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [subscribe](#subscribe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:subscribe(observer | onNext[, onError[, onCompleted]]) -> cp.rx.Reference` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shorthand for creating an [Observer](cp.rx.Observer.md) and passing it to this Observable's [subscription](#subscri) function. |
| **Parameters**                                       | <ul><li>observer | onNext     - Either an <a href="cp.rx.Observer.md">Observer</a> or a <code>function</code> to be called when the Observable produces a value.</li><li>onError               - A <code>function</code> to be called when the Observable terminates due to an error.</li><li>onCompleted           - A 'function` to be called when the Observable completes normally.</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.Reference.md">Reference</a> which can be used to cancel the subscription.</li></ul> |

#### [sum](#sum)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:sum() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that produces a single value representing the sum of the values produced |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [switch](#switch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:switch() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Given an `Observable` that produces `Observables`, returns an `Observable` that produces the values |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [switchIfEmpty](#switchifempty)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:switchIfEmpty(alternate) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Switch to an alternate `Observable` if this one sends an `onCompleted` without any `onNext`s. |
| **Parameters**                                       | <ul><li>alternate  - An <code>Observable</code> to switch to if this does not send any <code>onNext</code> values before the <code>onCompleted</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [take](#take)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:take([n]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that only produces the first n results of the original. |
| **Parameters**                                       | <ul><li>n       - The number of elements to produce before completing. Defaults to <code>1</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [takeLast](#takelast)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:takeLast(count) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that produces a specified number of elements from the end of a source |
| **Parameters**                                       | <ul><li>count   - The number of elements to produce.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [takeUntil](#takeuntil)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:takeUntil(other) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that completes when the specified `Observable` fires. |
| **Parameters**                                       | <ul><li>other     - The <code>Observable</code> that triggers completion of the original.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [takeWhile](#takewhile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:takeWhile(predicate) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Observable` that produces elements until the predicate returns `falsy`. |
| **Parameters**                                       | <ul><li>predicate       - The predicate <code>function</code> used to continue production of values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [tap](#tap)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:tap(onNext[, onError[, onCompleted]]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Runs a `function` each time this `Observable` has activity. Similar to [subscribe](#subscribe) but does not |
| **Parameters**                                       | <ul><li>onNext        - Run when the <code>Observable</code> produces values.</li><li>onError       - Run when the <code>Observable</code> encounters a problem.</li><li>onCompleted   - Run when the <code>Observable</code> completes.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [timeout](#timeout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:timeout(timeInMs, next[, scheduler]) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that will emit an error if the specified time is exceded since the most recent `next` value. |
| **Parameters**                                       | <ul><li>timeInMs          - The time in milliseconds to wait before an error is emitted.</li><li>next              - If a <code>string</code>, it will be sent as an error. If an <code>Observable</code>, switch to that <code>Observable</code> instead of sending an error.</li><li>scheduler         - The scheduler to use. Uses the <a href="cp.rx.util#defaultSubscriber">defaultScheduler</a> if not provided.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [unpack](#unpack)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:unpack() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that unpacks the `tables` produced by the original. |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [unwrap](#unwrap)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:unwrap() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that takes any values produced by the original that consist of multiple |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

#### [with](#with)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.Observable:with(...) -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an `Observable` that produces values from the original along with the most recently |
| **Parameters**                                       | <ul><li>...       - The <code>Observables</code> to include the most recent values from.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code>.</li></ul> |

