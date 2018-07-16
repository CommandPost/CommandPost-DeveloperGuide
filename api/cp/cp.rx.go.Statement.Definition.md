# [docs](index.md) » cp.rx.go.Statement.Definition
---

A [Statement](cp.rx.go.Statement.md) is defined before being executable.
A definition is initiated with the [Statement:modifier(...)](cp.rx.go.Statement.md#modifer) method.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Methods - API calls which can only be made on an object returned by a constructor
 * [define](#define)
 * [onInit](#oninit)
 * [onObservable](#onobservable)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.Definition.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is an instance of `Statement.Definition`. |
| **Parameters**                                       | <ul><li>thing    - The thing to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the thing is a <code>Statement.Definition</code>.</li></ul> |

### Methods

#### [define](#define)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.Definition:define() -> Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Completes the definition of the [Statement](cp.rx.go.Statement.md). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The new <a href="cp.rx.go.Statement.md">Statement</a>.</li></ul> |

#### [onInit](#oninit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.Definition:onInit(initFn) -> Statement.Definition` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Defines the function which will be called to initialise the context. |
| **Parameters**                                       | <ul><li>initFn       - The init function.</li></ul> |
| **Returns**                                          | <ul><li>The Statement Definition</li></ul> |

#### [onObservable](#onobservable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.Definition:onObservable(observableFn) -> Statement.Definition` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Defines the function which will be called to create the [Observable](cp.rx.Observable.md) |
| **Parameters**                                       | <ul><li>observableFn     - The observable creator function.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement.Definition</code></li></ul> |

