# [docs](index.md) » cp.rx.go.SubStatement
---

A `SubStatement` is an extension to a `Statement` that provides additional configuration details.
They are initiated via the [modifier](#modifier) method of a defined `Statement`.

## Submodules
 * [cp.rx.go.SubStatement.Definition](cp.rx.go.SubStatement.Definition.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Methods - API calls which can only be made on an object returned by a constructor
 * [context](#context)
 * [toObservable](#toobservable)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.SubStatement.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `SubStatement`. |
| **Parameters**                                       | <ul><li>thing    - The thing to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the <code>thing</code> is a <code>SubStatement</code>.</li></ul> |

### Methods

#### [context](#context)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.SubStatement:context() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `context` table for the `SubStatement`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>context</code> table.</li></ul> |

#### [toObservable](#toobservable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.SubStatement:toObservable() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new `Observable` instance for the current configuration. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code> instance.</li></ul> |

