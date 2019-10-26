# [docs](index.md) » cp.spec.Specification
---

A Specification is a list of [definitions](cp.spec.Definition.md) which
will be run in sequence, and the results are collated. It is often created via
the [describe](cp.spec.md#describe) function.

Example usage:
```
local spec = require "cp.spec"
local describe, it = spec.describe, spec.it

return describe "a specification" {
    it "performs an assertion"
    :doing(function()
        assert(true, "should not fail")
    end),
}
```

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Specification](#specification)
* Methods - API calls which can only be made on an object returned by a constructor
 * [onAfterEach](#onaftereach)
 * [onBeforeEach](#onbeforeeach)
 * [run](#run)
 * [with](#with)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Specification.is(instance) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `instance` is an instance of `Specification`. |
| **Returns**                                          | <ul><li><code>true</code> if it's a <code>Specification</code> instance.</li></ul> |

### Constructors

#### [Specification](#specification)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Specification(name) -> cp.spec.Specification` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new test suite. |

### Methods

#### [onAfterEach](#onaftereach)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Specification:onAfterEach(afterEachFn) -> cp.spec.Specification` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies a function to execute after each of the contained specifications is run. |
| **Parameters**                                       | <ul><li>afterEachFn - The function to run after each child runs.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>cp.spec.Specification</code> instance.</li></ul> |

#### [onBeforeEach](#onbeforeeach)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Specification:onBeforeEach(beforeEachFn) -> cp.spec.Specification` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies a function to execute before each of the contained specifications is run. |
| **Parameters**                                       | <ul><li>beforeEachFn - The function to run before each child runs.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>cp.spec.Specification</code> instance.</li></ul> |

#### [run](#run)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Specification:run() -> cp.spec.Run` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Runs the specification, returning the [Run](cp.spec.Run.md) instance, already running. |
| **Returns**                                          | <ul><li>The <a href="cp.spec.Run.md">Run</a> instance.</li></ul> |

#### [with](#with)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Specification:with(...) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds the provided [definitions](cp.spec.Definition.md) to the suite. |
| **Parameters**                                       | <ul><li>...           - the <a href="cp.spec.Definition.md">definitions</a> to add.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Specification</code> instance, with the definitions added.</li></ul> |

