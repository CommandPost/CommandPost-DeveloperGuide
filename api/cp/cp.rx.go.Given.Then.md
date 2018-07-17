# [docs](index.md) » cp.rx.go.Given.Then
---

A [Statement.Modifier](cp.rx.go.Statement.Modifier.md) of [Given](cp.rx.go.Given.md)
that defines what happens after the `Given` values resolve.

For example:

```lua
Given(anObservable):Then(function(value) return value:doSomething() end)
```

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [Then](#then)

## API Documentation

### Methods

#### [Then](#then)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Given.Then:Then(...) -> Given.Then` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Allows another set of `resolvables` to be processed after a `Then` has resolved. |
| **Parameters**                                       | <ul><li>...      - The list of <code>resolvable</code> values to process.</li></ul> |
| **Returns**                                          | <ul><li>Another <a href="cp.rx.go.Given.Then.md">Given.Then</a> instance.</li></ul> |

