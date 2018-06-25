# [docs](index.md) » hs.fnutils
---

Functional programming utility functions

## API Overview
* Functions - API calls offered directly by the extension
 * [concat](#concat)
 * [contains](#contains)
 * [copy](#copy)
 * [each](#each)
 * [every](#every)
 * [filter](#filter)
 * [find](#find)
 * [ieach](#ieach)
 * [ifilter](#ifilter)
 * [imap](#imap)
 * [indexOf](#indexof)
 * [map](#map)
 * [mapCat](#mapcat)
 * [reduce](#reduce)
 * [some](#some)
 * [split](#split)
* Constructors - API calls which return an object, typically one that offers API methods
 * [cycle](#cycle)
 * [partial](#partial)
 * [sequence](#sequence)
 * [sortByKeys](#sortbykeys)
 * [sortByKeyValues](#sortbykeyvalues)

## API Documentation

### Functions

#### [concat](#concat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.concat(table1, table2)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Join two tables together                                                                                         |
| **Parameters**                                       | <ul><br /><li>table1 - A table containing some sort of data * table2 - A table containing some sort of data</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>table1, with all of table2's elements added to the end of it</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>table2 cannot be a sparse table, see <a href="http://www.luafaq.org/gotchas.html#T6.4">http://www.luafaq.org/gotchas.html#T6.4</a></li><br /></ul>                                             |

#### [contains](#contains)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.contains(table, element) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Determine if a table contains a given object                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table containing some sort of data * element - An object to search the table for</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A boolean, true if the element could be found in the table, otherwise false</li><br /></ul>                                           |

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.copy(table) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Copy a table using `pairs()`                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table containing some sort of data</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A new table containing the same data as the input table</li><br /></ul>                                           |

#### [each](#each)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.each(table, fn)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Execute a function across a table (in arbitrary order), and discard the results                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table; it can have both a list (or array) part and a hash (or dict) part * fn - A function that accepts a single parameter (a table element)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [every](#every)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.every(table, fn) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns true if the application of fn on every entry in table is true.                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table containing some sort of data * fn - A function that accepts a single parameter and returns a "true" value (any value except the boolean <code>false</code> or nil) if the parameter was accepted, or a "false" value (the boolean false or nil) if the parameter was rejected.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>True if the application of fn on every element of the table is true * False if the function returns <code>false</code> for any element of the table.  Note that testing stops when the first false return is detected.</li><br /></ul>                                           |

#### [filter](#filter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.filter(table, fn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Filter a table by running a predicate function on its elements (in arbitrary order)                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table; it can have both a list (or array) part and a hash (or dict) part * fn - A function that accepts a single parameter (a table element) and returns a boolean   value: true if the parameter should be kept, false if it should be discarded</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing the elements of the table for which fn(element) returns true</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If <code>table</code> is a pure array table (list-like) without "holes", use <code>hs.fnutils.ifilter()</code> if you need guaranteed in-order processing and for better performance.</li><br /></ul>                                             |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.find(table, fn) -> element` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Execute a function across a table and return the first element where that function returns true                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table containing some sort of data * fn - A function that takes one parameter and returns a boolean value</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The element of the supplied table that first caused fn to return true</li><br /></ul>                                           |

#### [ieach](#ieach)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.ieach(list, fn)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Execute a function across a list-like table in order, and discard the results                                                                                         |
| **Parameters**                                       | <ul><br /><li>list - A list-like table, i.e. one whose keys are sequential integers starting from 1 * fn - A function that accepts a single parameter (a table element)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [ifilter](#ifilter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.ifilter(list, fn) -> list` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Filter a list-like table by running a predicate function on its elements in order                                                                                         |
| **Parameters**                                       | <ul><br /><li>list - A list-like table, i.e. one whose keys are sequential integers starting from 1 * fn - A function that accepts a single parameter (a table element) and returns a boolean   value: true if the parameter should be kept, false if it should be discarded</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A list-like table containing the elements of the table for which fn(element) returns true</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If <code>list</code> has "holes", all elements after the first hole will be lost, as the table is iterated over with <code>ipairs</code>;   use <code>hs.fnutils.map()</code> if your table has holes</li><br /></ul>                                             |

#### [imap](#imap)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.imap(list, fn) -> list` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Execute a function across a list-like table in order, and collect the results                                                                                         |
| **Parameters**                                       | <ul><br /><li>list - A list-like table, i.e. one whose keys are sequential integers starting from 1 * fn - A function that accepts a single parameter (a table element). The values returned from this function   will be collected into the result list; when <code>nil</code> is returned the relevant element is discarded - the   result list won't have any "holes".</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A list-like table containing the results of calling the function on every element in the table</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If <code>list</code> has "holes", all elements after the first hole will be lost, as the table is iterated over with <code>ipairs</code>;   use <code>hs.fnutils.map()</code> if your table has holes</li><br /></ul>                                             |

#### [indexOf](#indexof)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.indexOf(table, element) -> number or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Determine the location in a table of a given object                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table containing some sort of data * element - An object to search the table for</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A number containing the index of the element in the table, or nil if it could not be found</li><br /></ul>                                           |

#### [map](#map)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.map(table, fn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Execute a function across a table (in arbitrary order) and collect the results                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table; it can have both a list (or array) part and a hash (or dict) part * fn - A function that accepts a single parameter (a table element). For the hash part, the values returned from this function (if non-nil) will be assigned to the same key in the result list. For the array part, this function behaves like <code>hs.fnutils.imap()</code> (i.e. <code>nil</code> results are discarded); however all keys, including integer keys after a "hole" in <code>table</code>, will be iterated over.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing the results of calling the function on every element in the table</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If <code>table</code> is a pure array table (list-like) without "holes", use <code>hs.fnutils.imap()</code> if you need guaranteed in-order processing and for better performance.</li><br /></ul>                                             |

#### [mapCat](#mapcat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.mapCat(table, fn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Execute, across a table, a function that outputs tables, and concatenate all of those tables together                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table containing some sort of data * fn - A function that takes a single parameter and returns a table</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table containing the concatenated results of calling fn(element) for every element in the supplied table</li><br /></ul>                                           |

#### [reduce](#reduce)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.reduce(table, fn) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Reduce a table to a single element, using a function                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table containing some sort of data * fn - A function that takes two parameters, which will be elements of the supplied table. It should choose one of these elements and return it</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The element of the supplied table that was chosen by the iterative reducer function</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>table cannot be a sparse table, see <a href="http://www.luafaq.org/gotchas.html#T6.4">http://www.luafaq.org/gotchas.html#T6.4</a> * The first iteration of the reducer will call fn with the first and second elements of the table. The second iteration will call fn with the result of the first iteration, and the third element. This repeats until there is only one element left</li><br /></ul>                                             |

#### [some](#some)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.some(table, fn) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns true if the application of fn on entries in table are true for at least one of the members.                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table containing some sort of data * fn - A function that accepts a single parameter and returns a "true" value (any value except the boolean <code>false</code> or nil) if the parameter was accepted, or a "false" value (the boolean false or nil) if the parameter was rejected.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>True if the application of fn on any element of the table is true.  Note that testing stops when the first true return is detected. * False if the function returns <code>false</code> for all elements of the table.</li><br /></ul>                                           |

#### [split](#split)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.split(sString, sSeparator [, nMax] [, bPlain]) -> { array }` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Convert string to an array of strings, breaking at the specified separator.                                                                                         |
| **Parameters**                                       | <ul><br /><li>sString    -- the string to split into substrings * sSeparator -- the separator.  If <code>bPlain</code> is false or not provided, this is treated as a Lua pattern. * nMax       -- optional parameter specifying the maximum number (or all if <code>nMax</code> is nil) of substrings to split from <code>sString</code>. * bPlain     -- optional boolean parameter, defaulting to false, specifying if <code>sSeparator</code> should be treated as plain text (true) or a Lua pattern (false)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An array of substrings.  The last element of the array will be the remaining portion of <code>sString</code> that remains after <code>nMax</code> (or all, if <code>nMax</code> is not provided or is nil) substrings have been identified.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Similar to "split" in Perl or "string.split" in Python. * Optional parameters <code>nMax</code> and <code>bPlain</code> are identified by their type -- if parameter 3 or 4 is a number or nil, it will be considered a value for <code>nMax</code>; if parameter 3 or 4 is a boolean value, it will be considered a value for <code>bPlain</code>. * Lua patterns are more flexible for pattern matching, but can also be slower if the split point is simple. See §6.4.1 of the <em>Lua_Reference_Manual</em> at http://www.lua.org/manual/5.3/manual.html#6.4.1 for more information on Lua patterns.</li><br /></ul>                                             |

### Constructors

#### [cycle](#cycle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.cycle(table) -> fn()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a function that repeatedly iterates a table                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - A table containing some sort of data</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A function that, when called repeatedly, will return all of the elements of the supplied table, repeating indefinitely</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>table cannot be a sparse table, see <a href="http://www.luafaq.org/gotchas.html#T6.4">http://www.luafaq.org/gotchas.html#T6.4</a> * An example usage:    <code>lua    f = cycle({4, 5, 6})    {f(), f(), f(), f(), f(), f(), f()} == {4, 5, 6, 4, 5, 6, 4}</code></li><br /></ul>                                             |

#### [partial](#partial)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.partial(fn, ...) -> fn'` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns a new function which takes the provided arguments and pre-applies them as the initial arguments to the provided function.  When the new function is later invoked with additional arguments, they are appended to the end of the initial list given and the complete list of arguments is finally passed into the provided function and its result returned.                                                                                         |
| **Parameters**                                       | <ul><br /><li>fn - The function which will act on all of the arguments provided now and when the result is invoked later. * ... - The initial arguments to pre-apply to the resulting new function.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A function</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This is best understood with an example which you can test in the Hammerspoon console:</li><br /></ul>                                             |

#### [sequence](#sequence)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.sequence(...) -> fn` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a function that will collect the result of a series of functions into a table                                                                                         |
| **Parameters**                                       | <ul><br /><li>... - A number of functions, passed as different arguments. They should accept zero parameters, and return something</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A function that, when called, will call all of the functions passed to this constructor. The output of these functions will be collected together and returned.</li><br /></ul>                                           |

#### [sortByKeys](#sortbykeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.sortByKeys(table[ , function]) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Iterator for retrieving elements from a table of key-value pairs in the order of the keys.                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - the table of key-value pairs to be iterated through * fn - an optional function which will be passed to <code>table.sort</code> to determine how the keys are sorted.  If it is not present, then keys will be sorted numerically/alphabetically.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>function to be used as an iterator</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Similar to Perl's <code>sort(keys %hash)</code> * Iterators are used in looping constructs like <code>for</code>:   * <code>for i,v in hs.fnutils.sortByKeys(t[, f]) do ... end</code> * A sort function should accept two arguments and return true if the first argument should appear before the second, or false otherwise.   * e.g. <code>function(m,n) return not (m &lt; n) end</code> would result in reverse alphabetic order.   * See <em>Programming_In_Lua,_3rd_ed</em>, page 52 for a more complete discussion.   * The default sort is to compare keys directly, if they are of the same type, or as their tostring() versions, if the key types differ:     * function(m,n) if type(m) ~= type(n) then return tostring(m) &lt; tostring(n) else return m &lt; n end</li><br /></ul>                                             |

#### [sortByKeyValues](#sortbykeyvalues)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fnutils.sortByKeyValues(table[ , function]) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Iterator for retrieving elements from a table of key-value pairs in the order of the values.                                                                                         |
| **Parameters**                                       | <ul><br /><li>table - the table of key-value pairs to be iterated through * fn - an optional function which will be passed to <code>table.sort</code> to determine how the values are sorted.  If it is not present, then values will be sorted numerically/alphabetically.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>function to be used as an iterator</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Similar to Perl's <code>sort { $hash{$a} &lt;=&gt; $hash{$b} } keys %hash</code> * Iterators are used in looping constructs like <code>for</code>:   * <code>for i,v in hs.fnutils.sortByKeyValues(t[, f]) do ... end</code> * A sort function should accept two arguments and return true if the first argument should appear before the second, or false otherwise.   * e.g. <code>function(m,n) return not (m &lt; n) end</code> would result in reverse alphabetic order.   * See <em>Programming_In_Lua,_3rd_ed</em>, page 52 for a more complete discussion.   * The default sort is to compare values directly, if they are of the same type, or as their tostring() versions, if the value types differ:     * function(m,n) if type(m) ~= type(n) then return tostring(m) &lt; tostring(n) else return m &lt; n end</li><br /></ul>                                             |

