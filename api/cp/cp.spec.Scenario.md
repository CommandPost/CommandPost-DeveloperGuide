# [docs](index.md) » cp.spec.Scenario
---

A [Definition](cp.spec.Definition.md) which describes a specific scenario.

A `Scenario` is most typically created via the [it](cp.spec.md#it) function, like so:

```lua
local spec          = require "cp.spec"
local describe, it  = spec.describe, spec.it

local Rainbow       = require "my.rainbow"

return describe "a rainbow" {
    it "has seven colors"
    :doing(function()
        local rainbow = Rainbow()
        assert(#rainbow:colors() == 7, "the rainbow has seven colors")
    end)
}
```

Scenarios can be run asynchronously via the [Run.This](cp.spec.Run.This.md) instance passed to the `doing` function.
To indicate a scenario is asynchronous, call [`this:wait()`](cp.spec.Run.This.md#wait), then call
[`this:done()`](cp.spec.Run.This.md#done), to indicate it has completed. Any `assert` call which fails will
result in the run failing, and stop at that point.

For example:

```lua
return describe "a rainbow" {
    it "has a pot of gold at the end"
    :doing(function(this)
        this:wait()
        local rainbow = Rainbow()
        rainbow:goToEnd(function(whatIsThere)
            assert(whatIsThere:isInstanceOf(PotOfGold))
            this:done()
        end)
    end)
}
```

Definitions can also be data-driven, via the [where](#where) method:

```lua
return describe "a rainbow" {
    it "has ${color} at index ${index}"
    :doing(function(this)
        local rainbow = Rainbow()
        assert(rainbow[this.index] == this.color)
    end)
    :where {
        { "index",  "color"     },
        { 1,        "red"       },
        { 2,        "orange"    },
        { 3,        "yellow"    },
        { 4,        "blue"      },
        { 5,        "green"     },
        { 6,        "indigo"    },
        { 7,        "violet"    },
    },
}
```

This will do a run for each variation and interpolate the value into the run name for each.

**Note:** "where" parameters will not override built-in functions and fields in the [this](cp.spec.Run.This.md)
instance (such as "async" or "done") so ensure that you pick names that don't clash.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [Scenario](#scenario)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doing](#doing)
 * [run](#run)
 * [where](#where)

## API Documentation

### Constructors

#### [Scenario](#scenario)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Scenario(name[, testFn]) -> cp.spec.Scenario` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Scenario` with the specified name. |
| **Parameters**                                       | <ul><li>name          - The name of the scenario.</li><li>testFn     - (optional) The <code>function</code> which performs the test for in the scenario.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Scenario</code>.</li></ul> |
| **Notes**                                            | <ul><li>If the <code>testFn</code> is not provided here, it must be done via the <a href="#doing">doing</a> method prior to running,  an <code>error</code> will occur.</li></ul> |

### Methods

#### [doing](#doing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Scenario:doing(actionFn) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the `function` for the definition. |
| **Parameters**                                       | <ul><li>testFn     - The function that will do the test.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Definition</code>.</li></ul> |

#### [run](#run)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Scenario:run(...) -> cp.spec.Run` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Runs the scenario. |
| **Parameters**                                       | <ul><li>...   - The list of filters. The first one will be compared to this scenario to determine it should be run.</li></ul> |

#### [where](#where)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Scenario:where(data) -> cp.spec.Where` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies a `table` of data that will be iterated through as multiple [Runs](cp.spec.Run.md), one row at a time. |
| **Parameters**                                       | <ul><li>data      - The data table.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.spec.Where.md">Where</a>.</li></ul> |

