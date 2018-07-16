# [docs](index.md) » cp.rx.go.Statement.Modifier
---

A `Statement.Modifier` is an extension to a [Statement](cp.rx.go.Statement.md) that provides additional configuration details.
They are initiated via the [modifier](#modifier) method of a defined [Statement](cp.rx.go.Statement.md).

All `Statement.Modifier` instances will also have the methods defined by [Statement](cp.rx.go.Statement.md).

## Submodules
 * [cp.rx.go.Statement.Modifier.Definition](cp.rx.go.Statement.Modifier.Definition.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Methods - API calls which can only be made on an object returned by a constructor
 * [context](#context)
 * [toObservable](#toobservable)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.Modifier.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `Statement.Modifier`. |
| **Parameters**                                       | <ul><li>thing    - The thing to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the <code>thing</code> is a <code>Statement.Modifier</code>.</li></ul> |

### Methods

#### [context](#context)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.Modifier:context() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `context` table for the `Statement.Modifier`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>context</code> table.</li></ul> |

#### [toObservable](#toobservable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Statement.Modifier:toObservable() -> cp.rx.Observable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new `Observable` instance for the current configuration. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Observable</code> instance.</li></ul> |

