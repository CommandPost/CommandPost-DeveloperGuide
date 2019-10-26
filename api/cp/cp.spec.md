# [docs](index.md) » cp.spec
---

An synchronous/asynchronous test library for Lua.

This library uses a syntax similar to Ruby RSpec or Mocha.js.

## Simple Synchronous Test

To create a test, create a new file ending with `_spec.lua`. For example, `simple_spec.lua`:

```lua
local spec          = require "cp.spec"
local it            = spec.it

return it "always passes"
:doing(function()
    assert(true, "This always passes")
end)
```

It can be run from the Debug Console like so:

```
cp.spec "simple" ()
```

It will report something like this:

```
2019-10-06 18:13:28: [RESULT] it always passes: passed: 1; failed: 0; aborted: 0; time: 0.0022s
```

## Simple Synchronous Failure

If a test fails, it gives a report of where it failed, and if provided, the related message:

```lua
local spec          = require "cp.spec"
local it            = spec.it

return it "always fails"
:doing(function()
    assert(false, "This always fails")
end)
```

This will result in something like this:

```
2019-10-06 21:54:16:   [FAIL] it always fails: [.../simple_spec.lua:6] This always fails
2019-10-06 21:54:16:
2019-10-06 21:54:16: [RESULT] it always fails: passed: 0; failed: 1; aborted: 0; time: 0.0370s
```

You can then check the line that failed and resolve the issue.

## Simple Asynchronous Test

Performing an asynchronous test is only a little more complicated.
We'll modify our `simple_spec.lua` to use of the [Run.This](cp.spec.Run.This.md) instance available to every test:

```lua
local spec          = require "cp.spec"
local it            = spec.it
local timer         = require "hs.timer"

return it "always passes"
:doing(function(this)
    this:wait(5)
    assert(true, "This happens immediately")
    timer.doAfter(2, function()
        assert(true, "This happens after 2 seconds.")
        this:done()
    end)
end)
```

Other than using `hs.timer` to actually make this asynchronous, the key additions here are:
 * `this:wait(5)`: Tells the test that it is asynchronous, and to wait 5 seconds before timing out.
 * `this:done()`: Called inside the asynchronous function to indicate that it's complete.

Asycnchronous (and synchronous) tests can also be terminated by a failed `assert`, an `error` or a call to [this:fail(...)](cp.spec.Run.This.md#fail)
or [this:abort(...)](cp.spec.Run.This.md#abort)

## Multiple tests

Most things you're testing will require more than a single test. For this,
We use [Specification](cp.spec.Specification.md), most simply via the [describe](#describe) function:

```lua
local spec          = require "cp.spec"
local describe, it  = spec.describe, spec.it

local function sum(a,b)
    return a + b
end

return describe "sum" {
    it "results in 3 when you add 1 and 2"
    :doing(function()
        assert(sum(1, 2) == 3)
    end),
    it "results in 0 when you add 1 and -1"
    :doing(function()
        assert(sum(1, -1) == 0)
    end),
}
```

This will now run two tests, and report something like this:

```
2019-10-06 21:40:00: [RESULT] sum: passed: 2; failed: 0; aborted: 0; time: 0.0027s
```

## Data-driven Testing

When testing a feature, there are often multiple variations you want to test,
and repeating individual tests can get tedious.

This is a great place to use the [where](cp.spec.Scenario.md#where) feature.
Our previous test can become something like this:

```lua
return describe "sum" {
    it "results in ${result} when you add ${a} and ${b}"
    :doing(function(this)
        assert(sum(this.a, this.b) == this.result)
    end)
    :where {
        { "a",  "b",    "result"},
        { 1,    2,      3 },
        { 1,    -1,     0 },
    },
}
```

Other variations can be added easily by adding more rows.

## Running Multiple Specs

As shown above, you can run a single spec like so:

```lua
cp.spec "path.to.spec" ()
```

You can also run that spec an all other specs under the same path by adding `".*"` to the end.

```lua
cp.spec "path.to.spec.*" ()
```

Or run every spec in your system like so:

```lua
cp.spec "*" ()
```

## Submodules
 * [cp.spec.DefaultHandler](cp.spec.DefaultHandler.md)
 * [cp.spec.Definition](cp.spec.Definition.md)
 * [cp.spec.Error](cp.spec.Error.md)
 * [cp.spec.Handler](cp.spec.Handler.md)
 * [cp.spec.Message](cp.spec.Message.md)
 * [cp.spec.Report](cp.spec.Report.md)
 * [cp.spec.Run](cp.spec.Run.md)
 * [cp.spec.Scenario](cp.spec.Scenario.md)
 * [cp.spec.Specification](cp.spec.Specification.md)
 * [cp.spec.TestCase](cp.spec.TestCase.md)
 * [cp.spec.Where](cp.spec.Where.md)
 * [cp.spec.expect](cp.spec.expect.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [describe](#describe)
 * [find](#find)
 * [is](#is)
 * [it](#it)
 * [setSearchPath](#setsearchpath)
 * [spec](#spec)
 * [test](#test)

## API Documentation

### Functions

#### [describe](#describe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.describe(name) -> function(definitions) -> cp.spec.Specification` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a `function` which will accept a list of test [definitions](cp.spec.Definition.md), |
| **Parameters**                                       | <ul><li>name      - The name of the test suite.</li></ul> |
| **Returns**                                          | <ul><li>A <code>function</code> that must be called with the set of <a href="cp.spec.Definition.md">definitions</a> or <a href="cp.spec.Specification.md">suites</a> to run.</li></ul> |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.find(idPattern) -> cp.spec.Definition` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Attempts to find specs that match the provided ID pattern. |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Handled.is(other) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `other` is an instance of the `Handled` class. |

#### [it](#it)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.it(name[, ...]) -> cp.spec.Scenario` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns an [Scenario](cp.spec.Scenario.md) with the specified name and optional `doingFn` function. |
| **Parameters**                                       | <ul><li>name      - The name of the scenario.</li><li>doingFn   - (optional) The <code>function</code> to call when doing the operation. Will be passed the <a href="cp.spec.Run.This.md">Run.This</a>    instance for the definition.</li></ul> |
| **Notes**                                            | <ul><li>See <a href="cp.spec.Scenario.md#doing">doing</a> for more details regarding the function.</li></ul> |

#### [setSearchPath](#setsearchpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.setSearchPath(path)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets the path that will be used to search for `spec` files with the `spec "my.extension"` call. |
| **Parameters**                                       | <ul><li>path - The path to search for <code>spec</code> files. Set to <code>nil</code> to only search the default package path.</li></ul> |

#### [spec](#spec)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec(id) -> cp.spec.Definition` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This will search the package path (and [specPath](#setSpecPath), if set) for `_spec.lua` files. |
| **Parameters**                                       | <ul><li>id - the path ID for the spec. Eg. "cp.app"</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.spec.Definition.md">Definition</a>, or throws an error.</li></ul> |

#### [test](#test)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.test(id) -> cp.spec.Definition` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Attempts to load a [cp.test](cp.test.md) with the specified ID, converting |
| **Parameters**                                       | <ul><li>id - The <code>cp.test</code> ID (eg. <code>"cp.app"</code>).</li></ul> |
| **Returns**                                          | <ul><li>The <code>Definition</code> or throws an error if it can't be found.</li></ul> |

