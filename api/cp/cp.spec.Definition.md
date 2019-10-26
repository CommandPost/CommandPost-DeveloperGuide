# [docs](index.md) » cp.spec.Definition
---

A [Definition](cp.spec.Definition.md) is a superclass for a "runnable" specification.
It doesn't do anything itself, but provides a common ancestor for all implementation
classes like [Specification](cp.spec.Specification.md) and [Scenario](cp.spec.Scenario.md).

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Definition](#definition)
* Methods - API calls which can only be made on an object returned by a constructor
 * [run](#run)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Definition.is(instance) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Called as a method, this will check if the provided object is an instance of this class. |
| **Parameters**                                       | <ul><li>instance - The instance to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the instance is an instance of this class.</li></ul> |

### Constructors

#### [Definition](#definition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Definition(name[, doing]) -> cp.spec.Definition` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new test definition. |
| **Parameters**                                       | <ul><li>name      - The name</li></ul> |

### Methods

#### [run](#run)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Definition:run([...]) -> cp.spec.Run` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Runs the definition with the specified filter `string`, `function` or `table` of `string`s and `function`s. |
| **Parameters**                                       | <ul><li>...    - (optional) The list of filters to apply to any child definitions.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.spec.Run.md">Run</a>.</li></ul> |

